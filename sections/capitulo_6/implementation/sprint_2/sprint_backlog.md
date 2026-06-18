En este sprint se desarrollan las funcionalidades de gestión de organizaciones, el control interno (formatos de registro y políticas) y la plataforma IoT de seguridad. Las historias de usuario de organizaciones y control interno se completaron, mientras que las correspondientes a la plataforma IoT quedaron en proceso debido a su mayor complejidad técnica.

<table>
    <thead>
        <tr>
            <th colspan="2">User Story</th>
            <th colspan="6">Work-Item / Task</th>
        </tr>
        <tr>
            <th><strong>Id</strong></th>
            <th><strong>Title</strong></th>
            <th><strong>Id</strong></th>
            <th><strong>Title</strong></th>
            <th><strong>Description</strong></th>
            <th><strong>Estimation (Hours)</strong></th>
            <th><strong>Assigned To</strong></th>
            <th><strong>Status</strong></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">US-24</td>
            <td rowspan="2">Configurar ubicación (dirección física y referencia)</td>
            <td>T01</td>
            <td>Diseño del formulario de ubicación</td>
            <td>Diseñar la interfaz para capturar dirección física y referencia de la organización</td>
            <td>3</td>
            <td>Chi Cruzatt</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T02</td>
            <td>Implementación de configuración de ubicación</td>
            <td>Desarrollar el endpoint y la lógica para almacenar la dirección física y referencia</td>
            <td>4</td>
            <td>Guerrero Tomas</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-33</td>
            <td rowspan="2">Configurar ubicación GPS (coordenadas exactas)</td>
            <td>T03</td>
            <td>Integración de mapa interactivo</td>
            <td>Integrar Google Maps para la selección de coordenadas GPS del establecimiento</td>
            <td>5</td>
            <td>Nelson Fabrizio</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T04</td>
            <td>Persistencia de coordenadas GPS</td>
            <td>Desarrollar la lógica para guardar y validar las coordenadas exactas de la organización</td>
            <td>4</td>
            <td>Orozco Torres</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-10</td>
            <td rowspan="2">Invitar empleados</td>
            <td>T05</td>
            <td>Diseño del flujo de invitación</td>
            <td>Diseñar pantallas para invitar empleados y asignar roles dentro de la organización</td>
            <td>3</td>
            <td>Kevin Jorge</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T06</td>
            <td>Implementación de invitación de empleados</td>
            <td>Desarrollar el endpoint y la lógica para crear invitaciones con rol asignado</td>
            <td>6</td>
            <td>León Vivas</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-35</td>
            <td rowspan="2">Primer ingreso al sistema por correo electrónico</td>
            <td>T07</td>
            <td>Diseño de la plantilla de correo</td>
            <td>Diseñar la plantilla del correo de invitación con el enlace de acceso al sistema</td>
            <td>3</td>
            <td>Henry Paolo</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T08</td>
            <td>Implementación del envío de correo</td>
            <td>Desarrollar la integración con el servicio de correo para enviar invitaciones formales</td>
            <td>6</td>
            <td>Álvaro Joaquín</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-36</td>
            <td rowspan="2">Visualizar invitaciones</td>
            <td>T09</td>
            <td>API de listado de invitaciones</td>
            <td>Implementar endpoint para recuperar las invitaciones recibidas por un usuario</td>
            <td>3</td>
            <td>Fabrizio Amir</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T10</td>
            <td>Vista de invitaciones recibidas</td>
            <td>Desarrollar la pantalla para visualizar y gestionar las invitaciones recibidas</td>
            <td>4</td>
            <td>Chi Cruzatt</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-11</td>
            <td rowspan="2">Modificar permisos de los usuarios</td>
            <td>T11</td>
            <td>Diseño de gestión de permisos</td>
            <td>Diseñar la interfaz para ajustar permisos por área (IoT, RRHH, Procesos de control)</td>
            <td>4</td>
            <td>Nelson Fabrizio</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T12</td>
            <td>Implementación de actualización de permisos</td>
            <td>Desarrollar el endpoint y la lógica para actualizar los permisos de cada miembro</td>
            <td>5</td>
            <td>Guerrero Tomas</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-6</td>
            <td rowspan="2">Crear nuevo formato de registro</td>
            <td>T13</td>
            <td>Diseño del editor de formatos</td>
            <td>Diseñar la interfaz para crear formatos de registro con campos dinámicos</td>
            <td>4</td>
            <td>Kevin Jorge</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T14</td>
            <td>Implementación de creación de formato</td>
            <td>Desarrollar el endpoint y la lógica para registrar nuevos formatos asociados a un proceso</td>
            <td>6</td>
            <td>Orozco Torres</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-31</td>
            <td rowspan="2">Listar formatos de registro</td>
            <td>T15</td>
            <td>API de listado de formatos</td>
            <td>Implementar endpoint GET para recuperar los formatos asociados a un proceso de control</td>
            <td>3</td>
            <td>Henry Paolo</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T16</td>
            <td>Vista de listado de formatos</td>
            <td>Desarrollar tabla con filtros para visualizar los formatos de registro existentes</td>
            <td>4</td>
            <td>León Vivas</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-21</td>
            <td rowspan="2">Actualizar formato de registros</td>
            <td>T17</td>
            <td>Diseño de edición de formato</td>
            <td>Diseñar el flujo de edición de campos y estructura de un formato existente</td>
            <td>4</td>
            <td>Álvaro Joaquín</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T18</td>
            <td>Implementación de actualización de formato</td>
            <td>Desarrollar la lógica para modificar la estructura de un formato manteniendo versiones</td>
            <td>6</td>
            <td>Fabrizio Amir</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-7</td>
            <td rowspan="2">Configurar políticas de formato de registro</td>
            <td>T19</td>
            <td>Diseño de configuración de políticas</td>
            <td>Diseñar la interfaz para establecer reglas de modificación y frecuencia de registros</td>
            <td>4</td>
            <td>Chi Cruzatt</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T20</td>
            <td>Implementación de políticas de formato</td>
            <td>Desarrollar la lógica de validación de reglas sobre los registros de un formato</td>
            <td>5</td>
            <td>Nelson Fabrizio</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-29</td>
            <td rowspan="2">Cambiar estado de formato de registro</td>
            <td>T21</td>
            <td>Diseño de cambio de estado</td>
            <td>Diseñar el control para activar o desactivar la visibilidad de un formato</td>
            <td>2</td>
            <td>Guerrero Tomas</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T22</td>
            <td>Implementación de cambio de estado</td>
            <td>Desarrollar la lógica para cambiar el estado de un formato de registro</td>
            <td>3</td>
            <td>Kevin Jorge</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-23</td>
            <td rowspan="2">Suspender formato de registro de procesos de control interno</td>
            <td>T23</td>
            <td>Diseño de suspensión de formato</td>
            <td>Diseñar el flujo de suspensión de un formato con confirmación del usuario</td>
            <td>3</td>
            <td>Orozco Torres</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T24</td>
            <td>Implementación de suspensión de formato</td>
            <td>Desarrollar la lógica para suspender un formato sin afectar otros del mismo proceso</td>
            <td>4</td>
            <td>Henry Paolo</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-8</td>
            <td rowspan="2">Realizar registros para un formato de registros</td>
            <td>T25</td>
            <td>Diseño de formulario dinámico de registro</td>
            <td>Diseñar el formulario dinámico para el llenado de registros según el formato</td>
            <td>4</td>
            <td>León Vivas</td>
            <td>Done</td>
        </tr>
        <tr>
            <td>T26</td>
            <td>Implementación de llenado de registros</td>
            <td>Desarrollar la captura y persistencia de registros asociados a un formato</td>
            <td>6</td>
            <td>Álvaro Joaquín</td>
            <td>Done</td>
        </tr>
        <tr>
            <td rowspan="2">US-14</td>
            <td rowspan="2">Vincular dispositivos IoT</td>
            <td>T27</td>
            <td>Diseño del flujo de vinculación</td>
            <td>Diseñar el flujo para registrar y vincular dispositivos IoT a la organización</td>
            <td>4</td>
            <td>Fabrizio Amir</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>T28</td>
            <td>Implementación de vinculación de dispositivos</td>
            <td>Desarrollar el endpoint y la lógica para registrar dispositivos IoT de seguridad</td>
            <td>6</td>
            <td>Chi Cruzatt</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td rowspan="2">US-18</td>
            <td rowspan="2">Listar dispositivos IoT</td>
            <td>T29</td>
            <td>API de listado de dispositivos</td>
            <td>Implementar endpoint GET para recuperar los dispositivos IoT registrados</td>
            <td>3</td>
            <td>Nelson Fabrizio</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>T30</td>
            <td>Vista de listado de dispositivos</td>
            <td>Desarrollar la pantalla con el estado de los dispositivos IoT vinculados</td>
            <td>4</td>
            <td>Guerrero Tomas</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>US-19</td>
            <td>Cambiar identificador alias de dispositivo IoT</td>
            <td>T31</td>
            <td>Implementación de cambio de alias</td>
            <td>Desarrollar la funcionalidad inline para editar el alias de un dispositivo IoT</td>
            <td>3</td>
            <td>Kevin Jorge</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>US-17</td>
            <td>Desvincular dispositivo IoT</td>
            <td>T32</td>
            <td>Implementación de desvinculación</td>
            <td>Desarrollar la lógica para desvincular dispositivos IoT del sistema integrado</td>
            <td>5</td>
            <td>Orozco Torres</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td rowspan="2">US-15</td>
            <td rowspan="2">Monitorear datos de seguridad en tiempo real</td>
            <td>T33</td>
            <td>Diseño del dashboard de monitoreo</td>
            <td>Diseñar el panel de monitoreo en tiempo real de los sensores IoT</td>
            <td>5</td>
            <td>Henry Paolo</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>T34</td>
            <td>Implementación de monitoreo en tiempo real</td>
            <td>Desarrollar el canal de datos en tiempo real (WebSocket/MQTT) hacia la aplicación móvil</td>
            <td>8</td>
            <td>León Vivas</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td rowspan="2">US-27</td>
            <td rowspan="2">Activación automática de dispositivos IoT contra-incendios</td>
            <td>T35</td>
            <td>Diseño de lógica de activación automática</td>
            <td>Definir los umbrales y la lógica de detección de fuego para la activación automática</td>
            <td>6</td>
            <td>Álvaro Joaquín</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>T36</td>
            <td>Implementación de activación automática</td>
            <td>Desarrollar la lógica en el sistema embebido y edge para activar actuadores contra-incendios</td>
            <td>8</td>
            <td>Fabrizio Amir</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td rowspan="2">US-28</td>
            <td rowspan="2">Activación manual de dispositivos IoT contra-incendios</td>
            <td>T37</td>
            <td>Diseño del control de activación manual</td>
            <td>Diseñar el control físico y de aplicación para la activación manual de actuadores</td>
            <td>5</td>
            <td>Chi Cruzatt</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>T38</td>
            <td>Implementación de activación manual</td>
            <td>Desarrollar la lógica para activar manualmente los dispositivos contra-incendios</td>
            <td>7</td>
            <td>Nelson Fabrizio</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td rowspan="2">US-25</td>
            <td rowspan="2">Realizar llamada de emergencia</td>
            <td>T39</td>
            <td>Diseño de la pantalla de emergencia</td>
            <td>Diseñar la pantalla que inicia la llamada y muestra la información de ubicación</td>
            <td>3</td>
            <td>Guerrero Tomas</td>
            <td>In-Process</td>
        </tr>
        <tr>
            <td>T40</td>
            <td>Implementación de llamada de emergencia</td>
            <td>Desarrollar la integración para iniciar llamadas a servicios de emergencia con ubicación visible</td>
            <td>5</td>
            <td>Kevin Jorge</td>
            <td>In-Process</td>
        </tr>
    </tbody>
</table>
