Para el seguimiento de las modificaciones del código fuente y la documentación, el equipo utliza **GitHub** como plataforma principal.

**Repositorios de Software**

A continuación, se detallan las URLs de los repositorios para cada producto de la solución:

+ **Project Report:** [https://github.com/Soulware-IoT/report](https://github.com/Soulware-IoT/report)
+ **Landing Page:** [https://github.com/Soulware-IoT/landing](https://github.com/Soulware-IoT/landing)

**Estrategias de Ramas (GitFlow)**

El equipo implementa el flujo de trabajo GitFlow para la gestión de versiones. Se han definido las siguientes ramas principales y convenciones:

*   **main branch:** Contiene el código en estado de producción, siempre estable y listo para despliegue.
*   **develop branch:** Rama de integración donde se consolidan las funcionalidades terminadas antes de pasar a producción.
*   **Feature branches:** Ramas temporales creadas para el desarrollo de nuevas características o capítulos del informe.
    *   **Convención:** `feature/nombre-de-la-caracteristica` (Ej: `feature/chapter-I`, `feature/iam-context`).
*   **Release branches:** Ramas de preparación para una nueva entrega o lanzamiento oficial.
    *   **Convención:** `release/vX.Y.Z` aplicando **Semantic Versioning 2.0.0**. (Ej: `release/v1.0.0`).
*   **Hotfix branches:** Ramas para correcciones críticas urgentes que deben aplicarse directamente sobre la rama `main`.
    *   **Convención:** `hotfix/nombre-del-error` (Ej: `hotfix/urgent-fix`).


**Estándares de Commits**

Para mantener un historial de cambios legible y profesional, el equipo aplica la convención de **Conventional Commits**. Los mensajes de commit deben seguir la estructura: `<tipo>: <descripción breve>`.

*   **feat:** Una nueva funcionalidad.
*   **fix:** Corrección de un error.
*   **docs:** Cambios en la documentación.
*   **style:** Cambios que no afectan el significado del código (espacios, formato, etc.).
*   **refactor:** Un cambio en el código que no corrige un error ni añade una funcionalidad.
*   **test:** Añadir o corregir pruebas.
*   **chore:** Cambios en el proceso de construcción o herramientas auxiliares.