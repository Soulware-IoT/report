- **Restaurante (Restaurant):** Negocio gastronómico que opera una cocina y ocupa realizar procesos de control y gestión de riesgos

- **Organización (Organization):** Unidad administrativa digital que representa al restaurante dentro del sistema y agrupa usuarios, procesos, registros y dispositivos IoT.

- **Dueño (Owner):** Usuario principal con control total sobre la organizacion: configura permisos, crea procesos, registra dispositivos y define politicas de riesgo y accion.

- **Usuario (User):** Persona autenticada que accede al sistema web o movil para ejecutar acciones permitidas por su rol y permisos.

- **Administrador (Admin):** Usuario con privilegios de gestion autorizados por el dueño para administrar usuarios, permisos y configuraciones operativas del sistema.

- **Teniente (Lieutenant):** Usuario supervisor que puede tener permiso de administracion de usuarios o solo supervision de procesos, segun configuracion del dueño.

- **Encargado / Chef (Manager / Chef):** Usuario responsable de ejecutar y registrar procesos y sus politicas.

- **Rol (Role):** Categoria funcional asignada a un usuario que define los permisos que.

- **Permiso (Permission):** Regla especifica que habilita o restringe acciones concretas de un usuario sobre modulos, procesos, registros o dispositivos.

- **Politica de permisos (Permission policy):** Configuracion que determina como se delegan capacidades administrativas, de supervision y de registro entre usuarios de la organizacion.

- **Proceso de control (Control process):** Conjunto de formatos de registro.

- **Formato de registro (Record template):** Formato tipo tabla de que sirve de plantilla a llenar para los realizar procesos de control

- **Campo (field):** Campo de los cuales esta conformado el formato de registro o plantilla

- **Registro (record):** Entradas que se llenan en la plantilla del formato de registro

- **Dispositivo IoT (IoT device):** Equipo conectado al sistema que reporta eventos o estado de seguridad del restaurante (sensor, camara o actuador).

- **Sensor de humo (Smoke sensor):** Dispositivo IoT que detecta presencia de humo y genera alertas para activar protocolos de respuesta.

- **Sensor de calor (Heat sensor):** Dispositivo IoT que detecta incrementos anormales de temperatura y notifica posibles condiciones de incendio.

- **Camara de videovigilancia (Surveillance camera):** Dispositivo IoT que transmite video en tiempo real para observacion y validacion visual de incidentes.

- **Actuador IoT (IoT actuator):** Dispositivo controlable de forma remota por la plataforma (por ejemplo, alarma o aspersor).

- **Monitoreo en tiempo real (Real-time monitoring):** Visualizacion continua del estado, telemetria y alertas de dispositivos IoT en web y aplicacion movil.

- **Alerta de riesgo (Risk alert):** Notificacion generada por reglas o eventos de IoT cuando se detecta una condicion peligrosa o fuera de umbral.

- **Riesgo (Risk):** Condicion potencial de dano para personas, infraestructura u operacion (humo, fuego, sobrecalentamiento u otras amenazas).

- **Politica de riesgo (Risk policy):** Regla configurable que define umbrales, severidad, canales de notificacion y acciones automaticas/manuales ante incidentes.

- **Sistema de seguridad (Security system):** Modulo que integra monitoreo IoT, deteccion de eventos y capacidades de accion para prevencion y mitigacion de incidentes.

- **Llamada de emergencia (Emergency call):** Flujo guiado de la aplicacion movil que inicia contacto con emergencias mostrando datos de ubicacion para reducir errores humanos.

- **Incidente (Incident):** Evento confirmado o sospechoso de riesgo que requiere seguimiento operativo, posible activacion de actuadores y registro de evidencia.
