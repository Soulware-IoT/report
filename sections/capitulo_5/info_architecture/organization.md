La organización de la información en Cocina360 se ha estructurado para facilitar la gestión independiente de los flujos de datos a través de una arquitectura predominantemente **jerárquica**. Este enfoque asegura que el usuario pueda saltar entre los pilares del negocio manteniendo siempre la claridad sobre el contexto operativo.

**JERARQUÍA VISUAL Y NAVEGACIÓN LATERAL**

Se adopta un modelo de navegación basado en una **barra lateral (Sidenav)** persistente, inspirada en la interfaz de Jira. Este sistema garantiza que las tres áreas principales de la solución sean accesibles de forma directa, permitiendo una navegación fluida sin importar la profundidad de la vista actual.

La estructura de la navegación lateral refleja la división fundamental del sistema:
- **IoT Devices:** Gestión directa de hardware, sensores y actuadores.
- **Control Processes:** Administración de reglas de negocio y formatos de registro.
- **Organization:** Configuración de la identidad del restaurante, ubicación y personal.

**SISTEMAS DE ORGANIZACIÓN POR TEMAS**

El contenido se agrupa bajo un esquema de categorización por **temas (Topics)**, lo que permite separar las preocupaciones técnicas de las administrativas de forma tajante:
- **IoT:** Agrupación dedicada a la telemetría, estados de conexión y alertas de hardware.
- **Control Processes:** Agrupación orientada a la disciplina operativa y los logs históricos de cumplimiento.
- **Organization:** Agrupación centrada en la gestión de la startup y la administración de roles (*Lieutenant*, *Assignee*).

**ORGANIZACIÓN VISUAL MEDIANTE TARJETAS (CARDS)**

Dentro de cada bloque operativo, la información se organiza mediante **listas verticales de tarjetas (Cards)**. Esta elección de diseño responde a la necesidad de mantener una interfaz adaptable y eficiente:
- Las tarjetas actúan como unidades de información que presentan datos de forma jerárquica interna (Estado -> Identificador -> Valor).
- Este modelo permite realizar una supervisión pasiva rápida de las listas, permitiendo identificar anomalías de un solo vistazo.

**ORGANIZACIÓN SECUENCIAL**

Para procesos críticos que requieren una captura de datos precisa, como la vinculación de dispositivos o la creación de políticas, se utiliza una **organización secuencial**. Este modelo guía al usuario a través de pasos lógicos, reduciendo la posibilidad de errores durante la configuración inicial.
