El sistema de navegación de Cocina360 ha sido diseñado para minimizar la carga cognitiva del usuario, garantizando que el acceso a la información crítica de seguridad sea inmediato. Se basa en una estructura que combina una navegación global persistente con sistemas de guiado contextual.

**NAVEGACIÓN GLOBAL (SIDENAV)**

Para la plataforma de gestión (Web App), se implementa una **barra de navegación lateral (Sidenav)** persistente, inspirada en la arquitectura de Jira. Esta elección técnica permite al usuario mantener el contexto de su organización mientras navega entre los tres núcleos principales:
- **IoT Devices:** Acceso a la monitorización y control de hardware.
- **Control Processes:** Acceso a la gestión de disciplina operativa.
- **Organization:** Acceso a la administración del restaurante y personal.

Esta barra lateral permite un salto directo entre módulos, eliminando la necesidad de múltiples niveles de menús desplegables y asegurando que las funciones críticas estén a un solo clic de distancia.

**NAVEGACIÓN LOCAL Y CONTEXTUAL**

Dentro de cada módulo operativo, la navegación se especializa para facilitar la gestión de detalles:
- **Navegación por Tarjetas (Cards):** El usuario interactúa directamente con las listas verticales de tarjetas para profundizar en la información de un sensor o proceso específico. Cada tarjeta actúa como un disparador de navegación hacia la vista de detalle.
- **Breadcrumbs (Migas de pan):** En las vistas de configuración profunda, se utilizan rutas de navegación jerárquica para que el usuario pueda retornar al nivel anterior sin ambigüedad (ej. Organization > RRHH > Employee Detail).
- **CTAs de Acción Rápida:** Botones de alto contraste (Negro sólido) se posicionan de forma predecible para guiar al usuario hacia flujos de creación (Add, Create) o acciones de emergencia (Emergency Call).

**NAVEGACIÓN EN LA LANDING PAGE**

A diferencia de la aplicación, la Landing Page utiliza una **barra de navegación superior (Navbar)**. Este sistema está orientado a la conversión y la información, dirigiendo al visitante a través de los beneficios del producto y culminando en el botón de acceso "Get Started", que actúa como el puente principal hacia la aplicación de gestión.

**TÉCNICAS DE GUIADO Y RECORRIDO**

Para asegurar que los usuarios (como el *Assignee* o el *Lieutenant*) recorran el contenido de forma satisfactoria, se aplican las siguientes técnicas:
- **Guiado por Estados:** Se utiliza la paleta semántica (Verde/Rojo) en los elementos de navegación para atraer la atención hacia áreas que requieren revisión.
- **Navegación Lineal:** Los flujos de configuración siguen un orden lógico secuencial, impidiendo que el usuario se pierda en procesos de múltiples pasos.
- **Confirmación Visual:** Micro-interacciones de estado (como iconos de pulso en tiempo real) confirman al usuario que la navegación ha sido exitosa y que el sistema está respondiendo correctamente.
