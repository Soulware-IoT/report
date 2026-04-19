**Paso 1: Identificar de eventos**
El proceso comenzó identificando todos los eventos significativos que ocurren en el ecosistema de la cocina. Nos enfocamos en verbos en pasado: Process added, Device added, Risk detected, User added. En esta etapa, el objetivo fue no dejar nada fuera.

<img src="../../img/capitulo_2/eventstorming/eventstorming-1.jpg">

**Paso 2: Ordenar eventos**
Ordenamos los eventos cronológicamente. Aquí fue donde notamos que el flujo de Cocina360 no es lineal, sino que tiene ramas paralelas.

<img src="../../img/capitulo_2/eventstorming/eventstorming-2.jpg">

**Paso 3: Identificar puntos pivote**
Identificamos los eventos que marcan un cambio de fase en el negocio. El más importante fue la división entre la gestión de dispositivos IoT y la identificación de riesgos. Estos puntos nos dieron las primeras pistas sobre dónde estarían las fronteras de nuestros contextos.

<img src="../../img/capitulo_2/eventstorming/eventstorming-3.jpg">

**Paso 4: Identificar comandos**
Para cada evento, definimos la acción humana o del sistema que lo dispara. Por ejemplo:

El comando Add registry dispara el evento Registry added.

El comando Manual activation dispara Actuator activated.

<img src="../../img/capitulo_2/eventstorming/eventstorming-4.jpg">

**Paso 5: Identificar políticas**
Establecimos las reglas de "Siempre que ocurra X, haz Y". Una política clave en Cocina360 es: Siempre que se detecte un riesgo (Risk detected), activar el protocolo de emergencia o actuar sobre el actuador (Actuator activated). Esto une el mundo de los sensores con la seguridad del local.

<img src="../../img/capitulo_2/eventstorming/eventstorming-5.jpg">

**Paso 6: Vistas y lecturas**
Diseñamos lo que los usuarios necesitan ver para tomar decisiones.

<img src="../../img/capitulo_2/eventstorming/eventstorming-6.jpg">

**Paso 7: Actores**
Asignamos responsabilidades. Identificamos claramente que el Dueño interactúa mayormente con la configuración, el Encargado con la ejecución de procesos, y el Sistema con la detección de riesgos de seguridad.

<img src="../../img/capitulo_2/eventstorming/eventstorming-7.jpg">

**Paso 8: Identificar de Agregados**
Este fue el punto de debate técnico más rico en dominio. Decidimos romper la idea de un "Agregado Restaurante" gigante para evitar cuellos de botella. Definimos tres raíces de agregados claras:

Process: El contenedor de la lógica de los formularios tipo Excel.

Device: El dueño de la telemetría y el estado de los sensores.

Restaurant (Organization): El gestor de la jerarquía de usuarios y permisos.

<img src="../../img/capitulo_2/eventstorming/eventstorming-8.jpg">

**Paso 9: Definir Contextos**
Finalmente, agrupamos los agregados y sus eventos relacionados en fronteras lingüísticas y funcionales claras:

<img src="../../img/capitulo_2/eventstorming/eventstorming-9.jpg">