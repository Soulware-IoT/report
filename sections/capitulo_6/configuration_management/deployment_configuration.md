La estrategia de despliegue se divide en dos entornos diferenciados para optimizar la entrega de contenido estático y la ejecución de servicios de lógica de negocio.

* **Frontend (Landing Page):** Se utiliza **Vercel** para el alojamiento de la landing page. Esta plataforma permite un despliegue continuo (*Continuous Deployment*) mediante la sincronización directa con el repositorio de GitHub. Ante cualquier cambio en la rama principal, Vercel ejecuta automáticamente los procesos de construcción y despliega la aplicación a través de su infraestructura global optimizada para aplicaciones web modernas.

* **Backend:** Los servicios del lado del servidor se despliegan utilizando **Azure Container Instances (ACI)**. Este servicio permite ejecutar contenedores de Docker de forma *serverless* en la nube de Azure, eliminando la necesidad de gestionar máquinas virtuales y facilitando la escalabilidad de los servicios mediante una infraestructura bajo demanda.

* **Flujos de CI/CD con GitHub Actions:** Se implementan flujos de trabajo automatizados mediante **GitHub Actions** para garantizar la integridad y entrega del software:

  * **Integración Continua (CI):** Ante cada *push* o *pull request*, se ejecutan disparadores que realizan el *linting* del código y las pruebas unitarias con **NUnit** para validar la calidad del incremento.
  * **Despliegue Continuo (CD):** Una vez superadas las pruebas, las *actions* se encargan de compilar los artefactos, construir las imágenes de contenedor, subirlas al registro correspondiente y actualizar automáticamente las instancias en Azure y Vercel.
