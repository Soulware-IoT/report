Para la verificación de las funcionalidades desarrolladas en este sprint, el equipo adoptó el enfoque **Behavior-Driven Development (BDD)**, utilizando el lenguaje **Gherkin** para la especificación de escenarios ejecutables. Las pruebas se organizan en tres niveles: pruebas unitarias sobre servicios y componentes individuales, pruebas de integración sobre los endpoints del Backend y el Edge Gateway, y acceptance tests vinculados directamente a cada User Story comprometida en el sprint. Este enfoque permite alinear las pruebas con los criterios de aceptación definidos desde el inicio, facilitando la comunicación entre el equipo técnico y los stakeholders.

---

**Registro de lecturas desde el Edge Gateway**

```gherkin
Feature: Ingesta de lecturas IoT desde el Edge Gateway

  Background:
    Given el Edge Gateway tiene una API Key válida registrada en el sistema
    And existe al menos un IoT Device asociado a la organización

  Scenario: Registro exitoso de lecturas desde el Edge Gateway
    Given el Edge Gateway envía una solicitud POST a /edge/readings
    And el header X-Edge-Api-Key contiene una clave válida
    And el body incluye una lectura del dispositivo "COCINA-ABC123" con temperatura 25°C, gas 400 ppm y severidad "SAFE"
    Then el sistema responde con HTTP 202 Accepted
    And la lectura es persistida en la base de datos asociada al dispositivo

  Scenario: Rechazo por API Key inválida
    Given el Edge Gateway envía una solicitud POST a /edge/readings
    And el header X-Edge-Api-Key contiene una clave incorrecta
    Then el sistema responde con HTTP 401 Unauthorized
    And no se persiste ninguna lectura

  Scenario: Rechazo por batch vacío
    Given el Edge Gateway envía una solicitud POST a /edge/readings con una lista de lecturas vacía
    Then el sistema responde con HTTP 400 Bad Request
    And no se persiste ninguna lectura

  Scenario: Rechazo por dispositivo no perteneciente a la organización
    Given el Edge Gateway está autenticado correctamente
    And el body contiene el código de un dispositivo que pertenece a otra organización
    Then el sistema responde con HTTP 404 Not Found
    And no se persiste ninguna lectura
```

---

**Detección y propagación de lecturas críticas**

```gherkin
Feature: Detección de lecturas críticas y generación de alertas

  Background:
    Given el sistema tiene configurado el módulo de seguridad IoT
    And el dispositivo "COCINA-3F9A2B7C" está provisionado y vinculado a una organización

  Scenario: Lectura con severidad CRITICAL dispara evento de alerta
    Given el Edge Gateway envía una lectura con temperatura 60°C y gas 3500 ppm con severidad "CRITICAL"
    When el servicio procesa el comando RecordReadings
    Then se persisten las lecturas en la base de datos
    And se publica el evento CriticalReadingDetected con el ID del dispositivo y los valores de la lectura
    And el listener de alertas recibe el evento en menos de 5 segundos

  Scenario: Lectura con severidad SAFE no dispara evento de alerta
    Given el Edge Gateway envía una lectura con temperatura 25°C y gas 400 ppm con severidad "SAFE"
    When el servicio procesa el comando RecordReadings
    Then se persiste la lectura en la base de datos
    And no se publica ningún evento CriticalReadingDetected

  Scenario: Rechazo de lectura por código de dispositivo desconocido
    Given el Edge Gateway envía una lectura con código de dispositivo "COCINA-UNKNOWN"
    When el servicio intenta procesar el comando RecordReadings
    Then el sistema lanza IoTDeviceNotFoundException
    And no se persiste ninguna lectura
```

---

**Aplicación Mobile — Monitoreo de sensores**

```gherkin
Feature: Visualización de lecturas IoT en la aplicación mobile

  Background:
    Given el usuario autenticado tiene dispositivos IoT registrados en su organización

  Scenario: Visualización del estado actual de los sensores
    Given el usuario abre la pantalla de monitoreo en la app mobile
    When los datos de los sensores se cargan correctamente
    Then el sistema muestra la temperatura y nivel de gas de cada dispositivo
    And cada sensor muestra un indicador de severidad (SAFE, WARNING, CRITICAL)

  Scenario: Recepción de alerta por lectura crítica
    Given un dispositivo IoT registra una lectura con severidad "CRITICAL"
    When el usuario tiene la app mobile abierta o en segundo plano
    Then la app muestra una notificación de alerta con el nombre del dispositivo y los valores detectados

  Scenario: Visualización de historial de lecturas
    Given el usuario selecciona un dispositivo de la lista
    When accede a la sección de historial
    Then el sistema muestra las últimas lecturas ordenadas por fecha descendente
    And cada registro incluye temperatura, gas, severidad y timestamp
```

---

**Sistema Embebido (IoT Device)**

```gherkin
Feature: Captura y envío de telemetría desde el dispositivo embebido

  Background:
    Given el firmware del IoT Device está correctamente inicializado
    And el dispositivo tiene conectividad con el Edge Gateway

  Scenario: Envío periódico de lecturas al Edge Gateway
    Given el IoT Device captura datos de temperatura y gas cada 30 segundos
    When el intervalo de muestreo se cumple
    Then el dispositivo empaqueta los datos en el formato esperado por el Edge Gateway
    And los envía mediante el protocolo configurado

  Scenario: Retención de lecturas ante pérdida de conectividad
    Given el IoT Device pierde la conexión con el Edge Gateway
    When se capturan nuevas lecturas durante la interrupción
    Then el dispositivo almacena las lecturas en su buffer local
    And las reenvía al restablecer la conexión

  Scenario: Indicador visual de severidad en el dispositivo
    Given una lectura supera el umbral de temperatura configurado
    Then el dispositivo activa el indicador luminoso correspondiente a la severidad detectada
```

---

**Pruebas Unitarias**

A continuación se detallan las pruebas unitarias e integradas implementadas sobre los servicios del Backend durante este sprint.

<table>
    <thead>
        <tr>
            <th><strong>ID</strong></th>
            <th><strong>Componente / Clase</strong></th>
            <th><strong>Descripción de la prueba</strong></th>
            <th><strong>Resultado esperado</strong></th>
            <th><strong>Estado</strong></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>UT-01</td>
            <td>ReadingCommandService</td>
            <td>Registrar lecturas mixtas (SAFE y CRITICAL) y publicar solo el evento de la lectura crítica</td>
            <td>Se persisten 2 lecturas; se publica 1 evento CriticalReadingDetected con el deviceId y temperatura correctos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-02</td>
            <td>ReadingCommandService</td>
            <td>Rechazar comando con código de dispositivo desconocido</td>
            <td>Lanza IoTDeviceNotFoundException; no se invoca readingRepository.save()</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-03</td>
            <td>ReadingCommandService</td>
            <td>Rechazar lectura de dispositivo perteneciente a otra organización</td>
            <td>Lanza IoTDeviceNotFoundException; no se persiste ninguna lectura</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-04</td>
            <td>ReadingEventDeliveryTest</td>
            <td>Verificar que una lectura CRITICAL llega al ApplicationModuleListener a través del registro de publicación de Spring Modulith</td>
            <td>El listener CriticalReadingAlertListener recibe el evento CriticalReadingDetected en menos de 5 segundos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-05</td>
            <td>ReadingRepositoryAdapter</td>
            <td>Persistir una lectura en MongoDB y recuperarla por su ID</td>
            <td>La lectura recuperada tiene el mismo ID, deviceId, temperatura, gas y severidad que la guardada</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-06</td>
            <td>ReadingRepositoryAdapter</td>
            <td>Filtrar lecturas por deviceId devuelve solo las del dispositivo indicado</td>
            <td>Con 3 lecturas (2 del device A, 1 del device B), findByDeviceId(A) retorna exactamente 2 registros</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-07</td>
            <td>ReadingRepositoryAdapter</td>
            <td>Eliminar una lectura persistida</td>
            <td>Tras delete(), findById() retorna Optional.empty()</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-08</td>
            <td>EdgeReadingsController</td>
            <td>Aceptar batch de lecturas desde un Edge Gateway autenticado</td>
            <td>HTTP 202 Accepted; el comando RecordReadingsCommand se dispatcha con el organizationId y deviceCode correctos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-09</td>
            <td>EdgeReadingsController</td>
            <td>Rechazar solicitud con API Key inválida</td>
            <td>HTTP 401 Unauthorized; ReadingCommandService.handle() no es invocado</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-10</td>
            <td>EdgeReadingsController</td>
            <td>Retornar 404 cuando el dispositivo no pertenece a la organización del Edge</td>
            <td>HTTP 404 Not Found; la excepción IoTDeviceNotFoundException se mapea correctamente</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-11</td>
            <td>EdgeReadingsController</td>
            <td>Rechazar batch vacío</td>
            <td>HTTP 400 Bad Request; ReadingCommandService.handle() no es invocado</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-12</td>
            <td>ApiGatewayRouteConfig</td>
            <td>Enrutar solicitudes al microservicio correspondiente según el path</td>
            <td>Las rutas /security/**, /restaurant/** y /intern-control/** son dirigidas a sus backends respectivos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-13</td>
            <td>MobileReadingsViewModel</td>
            <td>Mapear lecturas de la API al estado de la vista con severidad correcta</td>
            <td>Una lectura CRITICAL se refleja con el indicador rojo en la UI; una SAFE con indicador verde</td>
            <td>Pass</td>
        </tr>
    </tbody>
</table>

---

**Acceptance Tests**

Los siguientes acceptance tests fueron validados contra los criterios de aceptación de cada User Story comprometida en el sprint.

<table>
    <thead>
        <tr>
            <th><strong>US ID</strong></th>
            <th><strong>Título</strong></th>
            <th><strong>Criterio de aceptación verificado</strong></th>
            <th><strong>Resultado</strong></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>US-01</td>
            <td>Registrar lecturas IoT desde el Edge Gateway</td>
            <td>El Edge Gateway puede enviar un batch de lecturas autenticado y el sistema las persiste con HTTP 202</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-02</td>
            <td>Autenticar Edge Gateway por API Key</td>
            <td>Una clave inválida retorna HTTP 401 y no persiste ninguna lectura</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-03</td>
            <td>Detectar lecturas críticas y generar alertas</td>
            <td>Una lectura con severidad CRITICAL publica el evento CriticalReadingDetected y el listener lo procesa en menos de 5 segundos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-04</td>
            <td>Monitorear sensores desde la aplicación mobile</td>
            <td>El usuario puede ver temperatura, nivel de gas y severidad de cada dispositivo en tiempo real desde la app</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>US-05</td>
            <td>Recibir notificaciones de alerta en la app mobile</td>
            <td>Una lectura crítica genera una notificación push visible en el dispositivo móvil del usuario</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>US-06</td>
            <td>Enviar telemetría desde el dispositivo embebido</td>
            <td>El firmware captura y envía lecturas periódicamente al Edge Gateway con el formato correcto</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-07</td>
            <td>Retener lecturas ante pérdida de conectividad</td>
            <td>El IoT Device almacena lecturas en buffer local y las reenvía al recuperar la conexión</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>US-08</td>
            <td>Enrutamiento centralizado por API Gateway</td>
            <td>Todas las solicitudes de clientes son enrutadas correctamente al microservicio destino sin pérdida de datos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-09</td>
            <td>Preprocesar datos en la aplicación edge</td>
            <td>La aplicación edge filtra y normaliza las lecturas antes de reenviarlas al backend, reduciendo el volumen de datos transmitidos</td>
            <td>In-Process</td>
        </tr>
    </tbody>
</table>
