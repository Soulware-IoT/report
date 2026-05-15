En este Sprint 1, se han completado las bases fundamentales de la solución Cocina360, abarcando desde la presencia digital hasta la infraestructura de servicios y la primera interfaz de gestión.

**Landing Page**

Se implementó una página de valor profesional con interfaz amigable para los segmentos objetivos. La página incluye secciones estratégicas como los sensores IoT, beneficios, funcionalidades y compras.

+ **Evidencia:**

<img src="../../../../img/capitulo_6/execution_evidence/landing_1.png">
<img src="../../../../img/capitulo_6/execution_evidence/landing_2.png">
<img src="../../../../img/capitulo_6/execution_evidence/landing_3.png">
<img src="../../../../img/capitulo_6/execution_evidence/landing_4.png">
<img src="../../../../img/capitulo_6/execution_evidence/landing_5.png">

+ **Link de despliegue** [https://soulware-landing.vercel.app/](https://soulware-landing.vercel.app/)

**Backend**

Se desarrollaron los primeros endpoints de la API REST de Cocina360. Se implementó la autenticación mediante OAuth 2.0 con Google (registro e inicio de sesión), la creación de organizaciones y la gestión completa de procesos de control interno: creación, listado, renombrado y suspensión.

+ **Link de despliegue** [https://cocina360-api.azurewebsites.net](https://cocina360-api.azurewebsites.net)


**SPA (Single Page Application)**

Se desarrollaron las primeras vistas funcionales de la aplicación web. Se implementaron las pantallas de autenticación con Google, el flujo de creación de organización y el módulo de procesos de control interno con sus operaciones de listado, creación, renombrado y suspensión. Asimismo, se integró la vista de suscripciones activas del usuario.

+ **Link de despliegue** [https://cocina360-spa.azurestaticapps.net](https://cocina360-spa.azurestaticapps.net)


**Azure**

Para el despliegue de los servicios desarrollados en este sprint se utilizó Microsoft Azure como plataforma cloud. El Backend fue alojado mediante Azure App Service, mientras que la SPA fue publicada a través de Azure Static Web Apps. Ambos servicios se benefician de la infraestructura gestionada de Azure, garantizando disponibilidad, escalabilidad y un entorno seguro para las pruebas del sprint.