Para la verificación de las funcionalidades desarrolladas en este sprint, el equipo adoptó el enfoque **Behavior-Driven Development (BDD)**, utilizando el lenguaje **Gherkin** para la especificación de escenarios ejecutables. Las pruebas se organizan en tres niveles: pruebas unitarias sobre servicios y componentes individuales, pruebas de integración sobre los endpoints del Backend, y acceptance tests vinculados directamente a cada User Story comprometida en el sprint. Este enfoque permite alinear las pruebas con los criterios de aceptación definidos desde el inicio, facilitando la comunicación entre el equipo técnico y los stakeholders.

---

**Autenticación con Google (US-37, US-38)**

```gherkin
Feature: Autenticación de usuarios mediante Google OAuth 2.0

  Background:
    Given el sistema tiene configurado el proveedor OAuth de Google
    And la base de datos de usuarios está disponible

  Scenario: Registro exitoso con cuenta de Google
    Given un visitante no registrado accede a la pantalla de registro
    When selecciona la opción "Registrarse con Google"
    And autoriza el acceso desde la ventana de Google
    Then el sistema crea una cuenta asociada al correo de Google
    And el usuario es redirigido al dashboard principal
    And se muestra el mensaje "Bienvenido a Cocina360"

  Scenario: Registro con cuenta de Google ya registrada
    Given un usuario con cuenta de Google ya existente intenta registrarse
    When selecciona la opción "Registrarse con Google"
    And autoriza el acceso desde la ventana de Google
    Then el sistema detecta que el correo ya está registrado
    And redirige al usuario al flujo de inicio de sesión
    And se muestra el mensaje "Ya tienes una cuenta. Inicia sesión."

  Scenario: Inicio de sesión exitoso con cuenta de Google
    Given un usuario registrado accede a la pantalla de inicio de sesión
    When selecciona la opción "Iniciar sesión con Google"
    And autoriza el acceso desde la ventana de Google
    Then el sistema valida el token OAuth recibido
    And genera un token de sesión para el usuario
    And el usuario es redirigido al dashboard principal

  Scenario: Inicio de sesión con cuenta de Google no registrada
    Given un visitante no registrado accede a la pantalla de inicio de sesión
    When selecciona la opción "Iniciar sesión con Google"
    And autoriza el acceso desde la ventana de Google
    Then el sistema detecta que el correo no tiene cuenta asociada
    And muestra el mensaje "No encontramos una cuenta con ese correo. ¿Deseas registrarte?"
```

---

**Gestión de Organizaciones (US-9)**

```gherkin
Feature: Creación de organización por parte del dueño de restaurante

  Background:
    Given el usuario autenticado tiene rol "Dueño de restaurante"
    And no tiene ninguna organización registrada

  Scenario: Creación de organización con datos válidos
    Given el usuario accede al formulario de creación de organización
    When ingresa el nombre "Restaurante El Fogón"
    And ingresa el RUC "20512345678"
    And presiona el botón "Crear organización"
    Then el sistema registra la organización exitosamente
    And redirige al usuario al panel de su organización
    And se muestra el mensaje "Organización creada correctamente"

  Scenario: Intento de creación con nombre vacío
    Given el usuario accede al formulario de creación de organización
    When deja el campo nombre en blanco
    And presiona el botón "Crear organización"
    Then el sistema muestra el error "El nombre de la organización es requerido"
    And no se registra ninguna organización

  Scenario: Intento de creación con RUC inválido
    Given el usuario accede al formulario de creación de organización
    When ingresa el nombre "Restaurante El Fogón"
    And ingresa el RUC "12345"
    And presiona el botón "Crear organización"
    Then el sistema muestra el error "El RUC debe tener 11 dígitos"
    And no se registra ninguna organización
```

---

**Procesos de Control Interno (US-5, US-30, US-22, US-20)**

```gherkin
Feature: Gestión de procesos de control interno

  Background:
    Given el usuario autenticado pertenece a una organización registrada
    And accede al módulo de "Procesos de control interno"

  Scenario: Creación de proceso con datos válidos
    Given el usuario abre el formulario de nuevo proceso
    When ingresa el nombre "Control de temperatura de cocina fría"
    And selecciona la categoría "Temperatura"
    And presiona "Guardar"
    Then el sistema registra el proceso exitosamente
    And el proceso aparece en el listado con estado "Activo"

  Scenario: Listado de procesos existentes
    Given la organización tiene 3 procesos registrados
    When el usuario accede a la vista de listado
    Then el sistema muestra los 3 procesos con nombre, categoría y estado
    And los procesos están ordenados por fecha de creación descendente

  Scenario: Listado sin procesos registrados
    Given la organización no tiene procesos registrados
    When el usuario accede a la vista de listado
    Then el sistema muestra el mensaje "Aún no tienes procesos registrados"

  Scenario: Renombrado exitoso de un proceso
    Given existe el proceso "Control de temperatura cocina fría" en el listado
    When el usuario selecciona la opción "Renombrar" sobre dicho proceso
    And escribe el nuevo nombre "Control térmico cocina fría"
    And confirma el cambio
    Then el proceso se actualiza con el nuevo nombre en el listado
    And se muestra el mensaje "Proceso renombrado correctamente"

  Scenario: Suspensión de un proceso activo
    Given existe el proceso "Control térmico cocina fría" con estado "Activo"
    When el usuario selecciona la opción "Suspender" sobre dicho proceso
    And confirma la acción en el modal de verificación
    Then el proceso cambia su estado a "Suspendido"
    And se muestra el mensaje "El proceso ha sido suspendido"

  Scenario: Reactivación de un proceso suspendido
    Given existe el proceso "Control térmico cocina fría" con estado "Suspendido"
    When el usuario selecciona la opción "Reactivar" sobre dicho proceso
    Then el proceso cambia su estado a "Activo"
    And se muestra el mensaje "El proceso ha sido reactivado"
```

---

**Visualización de Suscripciones (US-45)**

```gherkin
Feature: Visualización de suscripciones activas del usuario

  Background:
    Given el usuario autenticado tiene al menos una suscripción activa

  Scenario: Visualización de suscripciones activas
    Given el usuario navega a la sección "Suscripciones"
    When la página carga correctamente
    Then el sistema muestra las suscripciones con nombre del plan, fecha de inicio y fecha de vencimiento
    And cada suscripción muestra su estado actual ("Activa" o "Vencida")

  Scenario: Visualización sin suscripciones
    Given el usuario no tiene suscripciones registradas
    When navega a la sección "Suscripciones"
    Then el sistema muestra el mensaje "No tienes suscripciones activas. Elige un plan para comenzar."
```

---

**Pruebas Unitarias**

A continuación se detallan las pruebas unitarias implementadas sobre los servicios del Backend y los componentes del SPA durante este sprint.

<table>
    <thead>
        <tr>
            <th><strong>ID</strong></th>
            <th><strong>Componente / Servicio</strong></th>
            <th><strong>Descripción de la prueba</strong></th>
            <th><strong>Resultado esperado</strong></th>
            <th><strong>Estado</strong></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>UT-01</td>
            <td>AuthService</td>
            <td>Validar que el token OAuth de Google es verificado correctamente</td>
            <td>Retorna el payload del usuario si el token es válido</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-02</td>
            <td>AuthService</td>
            <td>Retornar error cuando el token OAuth es inválido o expirado</td>
            <td>Lanza excepción UnauthorizedException</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-03</td>
            <td>OrganizationService</td>
            <td>Crear organización con datos válidos</td>
            <td>Retorna el objeto organización creado con ID asignado</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-04</td>
            <td>OrganizationService</td>
            <td>Lanzar error al crear organización con RUC duplicado</td>
            <td>Lanza excepción ConflictException</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-05</td>
            <td>ProcessService</td>
            <td>Crear proceso de control interno con campos completos</td>
            <td>Retorna proceso con estado "Activo" y fecha de creación</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-06</td>
            <td>ProcessService</td>
            <td>Listar procesos filtrando por organización</td>
            <td>Retorna únicamente los procesos pertenecientes a la organización indicada</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-07</td>
            <td>ProcessService</td>
            <td>Renombrar proceso existente</td>
            <td>Retorna proceso actualizado con el nuevo nombre</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-08</td>
            <td>ProcessService</td>
            <td>Suspender proceso con estado "Activo"</td>
            <td>Retorna proceso con estado "Suspendido"</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-09</td>
            <td>ProcessService</td>
            <td>Lanzar error al intentar suspender un proceso ya suspendido</td>
            <td>Lanza excepción BadRequestException</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-10</td>
            <td>SubscriptionService</td>
            <td>Listar suscripciones activas del usuario autenticado</td>
            <td>Retorna lista con suscripciones cuyo estado es "Activa"</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-11</td>
            <td>HeroComponent (SPA)</td>
            <td>Renderizar correctamente el título y el CTA del Hero</td>
            <td>El componente muestra el headline y el botón de llamada a acción</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>UT-12</td>
            <td>FeaturesComponent (SPA)</td>
            <td>Renderizar la lista de características con sus íconos</td>
            <td>Se renderizan N tarjetas iguales al número de features configurados</td>
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
            <td>US-39</td>
            <td>Hero section</td>
            <td>La sección Hero es visible en la landing y contiene headline, subtítulo y CTA funcional</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-40</td>
            <td>Features</td>
            <td>La sección Features muestra al menos 3 características del producto con ícono y descripción</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-37</td>
            <td>Registrarme con Google</td>
            <td>Un nuevo usuario puede crear cuenta utilizando su identidad de Google sin formulario adicional</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-38</td>
            <td>Iniciar sesión con Google</td>
            <td>Un usuario registrado puede autenticarse con Google y acceder al dashboard en menos de 5 segundos</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-9</td>
            <td>Crear organización</td>
            <td>El dueño puede registrar su restaurante como organización y acceder a su panel de gestión</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-5</td>
            <td>Crear procesos de control interno</td>
            <td>El usuario puede registrar un proceso con nombre y categoría; el proceso aparece en el listado con estado "Activo"</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-30</td>
            <td>Listar procesos de control interno</td>
            <td>El usuario visualiza todos sus procesos con nombre, categoría, estado y fecha de creación</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-22</td>
            <td>Renombrar procesos de control interno</td>
            <td>El usuario puede cambiar el nombre de un proceso y el cambio se refleja inmediatamente en el listado</td>
            <td>Pass</td>
        </tr>
        <tr>
            <td>US-20</td>
            <td>Suspensión de procesos de control interno</td>
            <td>El usuario puede suspender un proceso activo; el estado cambia a "Suspendido" con confirmación visual</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>US-45</td>
            <td>Visualizar suscripciones</td>
            <td>El usuario puede ver sus suscripciones activas con plan, fechas y estado desde su perfil</td>
            <td>In-Process</td>
        </tr>
    </tbody>
</table>