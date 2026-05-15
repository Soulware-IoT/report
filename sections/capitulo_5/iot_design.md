El diseño del dispositivo IoT de Cocina360 ha sido concebido como una solución de ingeniería robusta que integra monitorización de precisión y respuesta inmediata en un factor de forma optimizado para entornos industriales.

**DISEÑO FÍSICO Y ESTÉTICA INDUSTRIAL**

El hardware presenta una estética minimalista y funcional, diseñada para ser instalada en techos o paredes de cocinas comerciales sin obstruir el flujo de trabajo.
- **Interfaz Luminosa:** Se implementa un indicador LED perimetral que espeja la paleta semántica del sistema (Verde: Óptimo / Rojo: Alerta), permitiendo una supervisión visual rápida a distancia.
- **Resistencia Térmica:** El chasis está fabricado en materiales ignífugos de alta durabilidad, capaces de soportar las temperaturas y la humedad características de una cocina profesional.

<img src="../../img/capitulo_5/iot/fire_detector/device.png">

<div style="page-break-after: always;"></div>

**DISEÑO ELECTRÓNICO Y ESQUEMÁTICO**

La arquitectura interna del dispositivo se basa en un microcontrolador de bajo consumo con conectividad inalámbrica, diseñado para una telemetría constante y confiable.
- **Subsistema de Sensores:** Integra transductores especializados para la detección de partículas de humo y cambios bruscos de temperatura ambiental.
- **Control de Actuadores:** El circuito incluye salidas de potencia para la activación automática de alarmas locales y sistemas de ventilación (turbinas), garantizando una mitigación inmediata del riesgo incluso en caso de pérdida de conexión externa.

<img src="../../img/capitulo_5/iot/fire_detector/circuit.png">

**FLUJO DE OPERACIÓN Y CONEXIÓN**

El dispositivo opera como un nodo inteligente dentro del ecosistema Cocina360:
1.  **Vigilancia Continua:** Los sensores capturan datos de telemetría cada segundo y los envían a la plataforma de gestión.
2.  **Detección Local:** En caso de superar los umbrales de seguridad, el dispositivo procesa la alerta localmente para una respuesta de milisegundos.
3.  **Sincronización:** El estado se actualiza en tiempo real en los Dashboards de las aplicaciones móviles y web, permitiendo al *Assignee* supervisar la situación desde su dispositivo personal.
