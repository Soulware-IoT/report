El sistema de búsqueda de Cocina360 se define bajo un enfoque de **conveniencia y simplicidad**, priorizando soluciones técnicas de fácil implementación que aporten un valor inmediato al usuario. El objetivo principal es evitar que el personal se sienta abrumado ante el crecimiento del número de dispositivos o registros históricos.

**SISTEMA DE BÚSQUEDA DINÁMICA**

Cada uno de los módulos operativos (IoT Devices y Control Processes) integra una **barra de búsqueda local** situada en la cabecera de la lista de tarjetas.
- **Búsqueda por Atributos:** El usuario puede localizar elementos escribiendo términos clave como el alias del dispositivo (ej: "Parrilla 1"), el tipo de sensor (ej: "Gas") o el identificador del proceso.
- **Respuesta en Tiempo Real:** Para asegurar la conveniencia, el sistema realiza un filtrado dinámico que actualiza la lista de tarjetas conforme se ingresan caracteres, eliminando la necesidad de recargar la página o presionar botones adicionales de "Buscar".

**SISTEMA DE FILTRADO POR ESTADOS**

Se implementan **filtros rápidos de conveniencia** basados en la paleta semántica del sistema, diseñados para ser accionados con un solo clic:
- **Filtro de Urgencia:** Un control tipo "Toggle" que permite visualizar exclusivamente los elementos en estado de **Review** (Anomalías). Esta es la herramienta de búsqueda más importante para el cumplimiento de los objetivos de seguridad del restaurante.
- **Filtro de Responsabilidad:** En la sección de procesos, se permite filtrar las tarjetas por el nombre del encargado (**Assignee**), facilitando la supervisión de las tareas realizadas por cada miembro del equipo.

**VISUALIZACIÓN DE RESULTADOS Y RETORNO**

Para mantener la consistencia en la arquitectura de información, los resultados se visualizan utilizando el mismo formato de **lista vertical de tarjetas**:
- **Estado de Vacío:** En caso de no encontrar coincidencias, el sistema muestra un mensaje informativo claro acompañado de un botón de "Limpiar filtros", garantizando que el usuario pueda retornar a la vista completa de forma inmediata.
- **Persistencia Mínima:** Los filtros se mantienen activos mientras el usuario navega dentro del módulo, pero se reinician al cambiar de área en la Sidenav para evitar confusiones sobre la disponibilidad de los datos.

Este diseño evita la complejidad de motores de búsqueda avanzados, optando por filtrados lógicos sobre la data en memoria, lo que asegura un rendimiento fluido incluso en aplicaciones móviles y una curva de implementación muy reducida para el equipo de desarrollo.
