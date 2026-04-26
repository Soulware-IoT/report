Se presenta a continuación el conjunto de User Stories planificadas para el alcance del proyecto.

<table>
    <thead>
        <tr>
            <th>Epic / Story ID</th>
            <th>Título</th>
            <th>Descripción</th>
            <th>Criterios de Aceptación</th>
            <th>Relacionado con (Epic ID)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>US-5</td>
            <td>Crear procesos de control interno</td>
            <td>Como Dueño de restaurante, quiero registrar los procesos de control interno de mi restaurante para tener la tranquilidad de que mi negocio opera con la estructura y consistencia que necesito</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de creación de proceso de control interno<br>
                    <strong>Given</strong> el dueño está administrando los procesos de control interno<br>
                    <strong>When</strong> elige crear un nuevo proceso de control interno<br>
                    <strong>Then</strong> se solicita al dueño ingresar el nombre de este nuevo proceso de control interno
                    </li>
                    <li>
                    <strong>Scenario:</strong> Crear proceso de control interno (éxito)<br>
                    <strong>Given</strong> el dueño ha elegido crear un nuevo proceso de control interno<br>&nbsp;&nbsp;And el nombre ingresado es válido (sin caracteres especiales, no vacío)<br>
                    <strong>When</strong> confirma la creación del nuevo proceso de control interno<br>
                    <strong>Then</strong> el nuevo proceso de control interno debe ser agregado en su organización<br>&nbsp;&nbsp;And se informa al usuario su creación mediante un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Crear proceso de control interno (nombre inválido)<br>
                    <strong>Given</strong> el dueño ha elegido crear un nuevo proceso de control interno<br>
                    <strong>When</strong> ingrese un nombre inválido (con caracteres especiales o vacío)<br>
                    <strong>Then</strong> se desactiva la opción de crear el nuevo proceso de control interno<br>&nbsp;&nbsp;And se explica la razón por la cual la opción ingresada no es válida con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Crear proceso de control interno (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la creación de un nuevo proceso de control interno<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se crea el nuevo proceso de control interno<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo mediante un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-6</td>
            <td>Crear nuevo formato de registro</td>
            <td>Como Dueño de restaurante, quiero crear formatos de registro para procesos de control internos para registrar los documentos que utilizo en mi negocio para dichos procesos</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de creación de formato de registro para proceso de control interno<br>
                    <strong>Given</strong> el dueño cuenta con al menos un proceso de control interno<br>&nbsp;&nbsp;And ha seleccionado uno de los procesos de control interno existentes<br>
                    <strong>When</strong> elige crear un formato de registro<br>
                    <strong>Then</strong> se solicita ingresar un nombre para el proceso de control interno
                    </li>
                    <li>
                    <strong>Scenario:</strong> Crear proceso de control interno (éxito)<br>
                    <strong>Given</strong> el dueño ha elegido crear un nuevo formato de registro para un proceso de control interno específico<br>&nbsp;&nbsp;And ha ingresado un nombre válido (sin caracteres especiales, no vacío)<br>
                    <strong>When</strong> confirma la creación de el nuevo formato de registro<br>
                    <strong>Then</strong> se crea un formato de registro para el proceso de control interno seleccionado con el nombre ingresado, dos columnas por defecto a modo de ejemplo y el estado 'INACTIVO'<br>&nbsp;&nbsp;And se confirma al usuario la creación con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Crear proceso de control interno (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la creación de un formato de registro<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se crea el formato de registro<br>&nbsp;&nbsp;And se informa al usuario la razón por la que la operación falló
                    </li>
                    <li>
                    <strong>Scenario:</strong> Crear proceso de control interno (nombre inválido)<br>
                    <strong>Given</strong> el dueño ha elegido crear un nuevo formato de registro para un proceso de control interno específico<br>
                    <strong>When</strong> ingresa un nombre inválido (con caracteres especiales, vacío)<br>
                    <strong>Then</strong> la opción de confirmar la creación del nuevo formato de registro debe desactivarse
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-7</td>
            <td>Configurar políticas de formato de registro</td>
            <td>Como Dueño de restaurante, quiero establecer reglas sobre la modificación o frecuencia de los registros asociados a mis procesos para garantizar la validez y la integridad de los datos, manteniendo la disciplina operativa y evitando inconsistencias</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Acceder a configuración de políticas de formato de registro<br>
                    <strong>Given</strong> el dueño del restaurante se encuentra visualizando un formato de registro<br>
                    <strong>When</strong> selecciona editar las políticas del formato de registro<br>
                    <strong>Then</strong> se debe visualizar las configuraciones de las políticas asociadas al formato de registro como un formulario editable
                    </li>
                    <li>
                    <strong>Scenario:</strong> Intención de modificar políticas de formato de registro<br>
                    <strong>Given</strong> el dueño se encuentra visualizando las políticas asociadas a un formato de registro<br>
                    <strong>When</strong> cambia las configuraciones de las políticas asociadas<br>
                    <strong>Then</strong> se debe activar la opción de confirmar cambios a las políticas del formato de registros
                    </li>
                    <li>
                    <strong>Scenario:</strong> Modificar políticas de formato de registro (éxito)<br>
                    <strong>Given</strong> el dueño se encuentra visualizando las políticas asociadas a un formato de registro<br>&nbsp;&nbsp;And ha cambiado las configuraciones de las políticas asociadas<br>
                    <strong>When</strong> confirma los cambios<br>
                    <strong>Then</strong> se deben cambiar las políticas asociadas a las nuevas configuraciones ingresadas<br>&nbsp;&nbsp;And se debe confirmar al usuario los cambios con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Modificar políticas de formato de registro (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado los cambios a las políticas de un formato de registros<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se modifican las políticas asociadas al formato de registro<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo con un mensaje
                    </li>
                    <li>Las opciones de políticas deberían incluir la frecuencia de creación de nuevos registros: diario, semanal, mensual. Estos se corresponden con el bloque según semanas (se valida de lunes a lunes y de 1ro de un mes al último día de dicho mes).</li>
                    <li>Las opciones de políticas deberían incluir la cantidad máxima de registros que se pueden añadir en un periodo de tiempo (número personalizable)</li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-8</td>
            <td>Realizar registros para un formato de registros</td>
            <td>Como Cocinero asignado como 'RESPONSABLE' a un formato de registros, quiero llenar los formatos de registro de los procesos de control interno de forma sencilla y eficiente para documentar el cumplimiento de los procesos de control, eliminando la incertidumbre de la 'confianza verbal'</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de creación de nuevo registro<br>
                    <strong>Given</strong> el cocinero tiene el rol de 'RESPONSABLE' para al menos un formato de registros<br>&nbsp;&nbsp;And selecciona uno de los formatos de registros de los cuales es responsable<br>&nbsp;&nbsp;And el formato de registros seleccionado tiene el estado 'ACTIVO'<br>
                    <strong>When</strong> elige añadir un nuevo registro<br>
                    <strong>Then</strong> se debe visualizar un formulario con campos correspondientes al formato de registros
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adición de nuevo registro (éxito)<br>
                    <strong>Given</strong> el cocinero se encuentra llenando un formulario correspondiente a un formato de registros<br>&nbsp;&nbsp;And ha llenado correctamente todos los campos del formato de registros<br>
                    <strong>When</strong> confirme la adición del nuevo registro<br>
                    <strong>Then</strong> se debe almacenar el nuevo registro<br>&nbsp;&nbsp;And se confirma al usuario su adición mediante un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adición de nuevo registro (fallo)<br>
                    <strong>Given</strong> el cocinero ha confirmado la adición del nuevo registro<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se añade el registro<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adición de nuevo registro (campos inválidos)<br>
                    <strong>Given</strong> l cocinero se encuentra llenando un formulario correspondiente a un formato de registros<br>
                    <strong>When</strong> llene algún campo de forma inválida (vacío si es requerido, o valores no admitidos por el campo)<br>
                    <strong>Then</strong> se desactiva la opción de confirmar la adición del nuevo registro<br>&nbsp;&nbsp;And se señala al usuario el campo que hace que el campo sea válido<br>&nbsp;&nbsp;And se proporciona la razón de que la opción ingresada sea inválida
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-9</td>
            <td>Crear organización</td>
            <td>Como Dueño de restaurante, quiero crear la organización correspondiente a mi restaurante dentro del sistema para tener una visión clara y estructurada de mi negocio para una gestión más eficaz y un mayor control</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Solicitar creación de organización al ingresar por primera vez<br>
                    <strong>Given</strong> Given el dueño no tiene configurada una organización creada<br>
                    <strong>When</strong> ingrese a la aplicación por primera vez<br>
                    <strong>Then</strong> se solicitan datos crear una organización, los cuales incluyen nombre (requerido) y foto, dirección y ubicación GPS (opcionales)
                    </li>
                    <li>
                    <strong>Scenario:</strong> Creación de organización (éxito)<br>
                    <strong>Given</strong> el dueño se encuentra creando su organización<br>&nbsp;&nbsp;And ha llenado al menos el único campo obligatorio (nombre) de forma válida (caracteres especiales permitidos, no vacío)<br>
                    <strong>When</strong> confirme la creación de la organización<br>
                    <strong>Then</strong> se debe registrar la organización con los datos registrados<br>&nbsp;&nbsp;And se informa al usuario sobre su creación mediante un mensaje<br>&nbsp;&nbsp;And se lo conduce a la interfaz principal
                    </li>
                    <li>
                    <strong>Scenario:</strong> Creación de organización (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la creación de su organización<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se crea la organización<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Intención de añadir foto de restaurante<br>
                    <strong>Given</strong> el dueño se encuentra creando su organización<br>
                    <strong>When</strong> elija añadir una foto de organización<br>
                    <strong>Then</strong> se debe permitir utilizar el sistema de archivos del dispositivo para elegir una foto
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir foto de restaurante (éxito)<br>
                    <strong>Given</strong> el dueño ha seleccionado una foto de su sistema de archivos<br>
                    <strong>When</strong> confirme la selección de la foto como foto de la organización<br>
                    <strong>Then</strong> la foto debe quedar almacenada en el sistema inmediatamente<br>&nbsp;&nbsp;And se confirma su almacenamiento al usuario mediante un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir foto de restaurante (fallo)<br>
                    <strong>Given</strong> ha confirmado la selección de una foto como foto de la organización<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> la foto no se registra en el sistema<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo
                    </li>
                    <li>
                    <strong>Scenario:</strong> Intención de añadir ubicación GPS del restaurante<br>
                    <strong>Given</strong> el dueño se encuentra creando su organización<br>
                    <strong>When</strong> elija añadir la ubicación del restaurante<br>
                    <strong>Then</strong> se debe permitir abrir un mapa interactivo tomando como ubicación inicial, de ser posible, la ubicación actual del usuario mediante GPS
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir ubicación GPS del restaurante (éxito)<br>
                    <strong>Given</strong> el dueño ha seleccionado un punto en el mapa o ingresado coordenadas válidas (en Lima Perú)<br>
                    <strong>When</strong> confirme la selección de la ubicación como posición de la organización<br>
                    <strong>Then</strong> la ubicación debe quedar almacenada en el sistema inmediatamente<br>&nbsp;&nbsp;And se confirma su almacenamiento al usuario mediante un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir ubicación GPS del restaurante (fallo)<br>
                    <strong>Given</strong> ha confirmado la selección de una ubicación como posición de la organización<br>
                    <strong>When</strong> la operación falle por falta de permisos de GPS o error de red<br>
                    <strong>Then</strong> la ubicación no se registra en el sistema<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo
                    </li>
                    <li>
                    <strong>Scenario:</strong> Creación de organización (nombre inválido)<br>
                    <strong>Given</strong> el dueño se encuentra creando su organización<br>
                    <strong>When</strong> ingrese un nombre de organización inválido (vacío)<br>
                    <strong>Then</strong> se debe bloquear la opción de confirmar la creación de la organización con las opciones ingresadas<br>&nbsp;&nbsp;And se debe informar al usuario la razón por la que la opción ingresada es inválida
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-20</td>
            <td>Suspensión de procesos de control interno</td>
            <td>Como Dueño de restaurante, quiero suspender procesos de control interno para impedir el ingreso de nuevos registros cuando por razones de negocio se va a cesar su aplicación temporal o permanentemente</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de suspender proceso de control interno<br>
                    <strong>Given</strong> el dueño tiene al menos un proceso de control interno<br>&nbsp;&nbsp;And selecciona uno de ellos<br>
                    <strong>When</strong> intente suspender el proceso de control interno<br>
                    <strong>Then</strong> se solicita al usuario una confirmación 
                    </li>
                    <li>
                    <strong>Scenario:</strong> Suspensión de proceso de control interno (éxito)<br>
                    <strong>Given</strong> el dueño ha intentado suspender un proceso de control interno<br>
                    <strong>When</strong> confirme la acción<br>
                    <strong>Then</strong> se debe cambiar el estado del proceso seleccionado a 'SUSPENDIDO'<br>&nbsp;&nbsp;And se notifica al usuario su suspensión con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Suspensión de proceso de control interno (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la suspensión de un proceso de control interno<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> el estado del proceso de control interno no cambia<br>&nbsp;&nbsp;And se notifica al usuario la razón del fallo con un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-21</td>
            <td>Actualizar formato de registros </td>
            <td>Como Dueño de restaurante, quiero actualizar el formato de los registros para procesos de control interno para mantener el formato actualizado según evoluciona y madura la aplicación de los procesos de control interno del negocio</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Adición de nueva columna al formato de registro (éxito)<br>
                    <strong>Given</strong> el dueño se encuentra modificando un formato de registro<br>
                    <strong>When</strong> seleccione añadir una nueva columna<br>
                    <strong>Then</strong> se debe crear una nueva columna con un nombre por defecto y un tipo de dato por defecto<br>&nbsp;&nbsp;And se confirma al usuario que la nueva columna fue añadida con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adición de nueva columna al formato de registro (fallo)<br>
                    <strong>Given</strong> el dueño ha seleccionado añadir una nueva columna<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se añade ninguna nueva columna<br>&nbsp;&nbsp;And se notifica al usuario la razón del fallo
                    </li>
                    <li>
                    <strong>Scenario:</strong> Intención de remoción de columna existente de un formato de registro<br>
                    <strong>Given</strong> el dueño se encuentra modificando un formato de registro<br>&nbsp;&nbsp;And el formato de registro cuenta con al menos una columna<br>
                    <strong>When</strong> seleccione remover una de las columnas existentes<br>
                    <strong>Then</strong> se debe solicitar al usuario una confirmación de la operación seleccionada
                    </li>
                    <li>
                    <strong>Scenario:</strong> Remoción de columna existente de un formato de registro (éxito)<br>
                    <strong>Given</strong> el dueño ha seleccionado remover una columna existente de un formato de registros<br>
                    <strong>When</strong> confirme la eliminación de la columna<br>
                    <strong>Then</strong> se debe eliminar la columna específicada por el usuario<br>&nbsp;&nbsp;And se confirma al usuario su eliminación con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Remoción de columna existente de un formato de registro (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la eliminación de una columna existente de un formato de registros<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se elimina ninguna columna del formato de registro<br>&nbsp;&nbsp;And se notifica al usuario la razón del fallo con un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-22</td>
            <td>Renombrar procesos de control interno</td>
            <td>Como Dueño de restaurante, quiero quiero ajustar el nombre asignado a procesos de control interno para mantener el nombre de los procesos actualizado a como madura el lenguaje de mi negocio</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Iniciar cambio de nombre de proceso de control interno<br>
                    <strong>Given</strong> el dueño de restaurante cuenta con al menos un proceso de control interno<br>
                    <strong>When</strong> elige cambiar el nombre del proceso de control interno<br>
                    <strong>Then</strong> debe mostrarse un modal o formulario para ingresar el nuevo nombre<br>&nbsp;&nbsp;And este debe contener como valor inicial el nombre actual del proceso de control interno
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar nombre de proceso de control interno (éxito)<br>
                    <strong>Given</strong> el dueño de restaurante ha elegido modificar el nombre de un proceso de control interno<br>&nbsp;&nbsp;And ha ingresado un nuevo nombre válido (no vacío, sin caracteres especiales)<br>
                    <strong>When</strong> decide confirmar el cambio de nombre<br>
                    <strong>Then</strong>  el nombre del proceso de control interno cambia al ingresado por el usuario<br>&nbsp;&nbsp;And se confirma el cambio al usuario con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar nombre de proceso de control interno (fallo)<br>
                    <strong>Given</strong> el dueño de restaurante ha confirmado el cambio del nombre de un proceso de control interno<br>
                    <strong>When</strong> el proceso falla por algún motivo<br>
                    <strong>Then</strong> el nombre del proceso se mantiene sin cambios<br>&nbsp;&nbsp;And se informa al usuario la razón por la que la operación ha fallado con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar nombre de proceso de control interno (nombre inválido)<br>
                    <strong>Given</strong> el dueño de restaurante ha elegido modificar el nombre de un proceso de control interno<br>&nbsp;&nbsp;And <br>
                    <strong>When</strong> ingrese un nombre no válido (vacío, con caracteres especiales o idéntico al nombre actual)<br>
                    <strong>Then</strong> la opción de confirmar el cambio de nombre del proceso debe deshabilitarse<br>&nbsp;&nbsp;And señalar la razón por la cual la opción ingresada no es válida mediante un mensaje
                    </li>
                    <li>La edición debería contar con un modal u otra forma de confirmación para evitar una modificación accidental.</li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-23</td>
            <td>Suspender formato de registro de procesos de control interno</td>
            <td>Como Dueño de restaurante, quiero suspender un formato de registro de procesos de control interno para evitar el ingreso de nuevos registros en dicho formato específico, sin afectar a otros formatos correspondientes al mismo proceso</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Suspender un proceso de control interno (éxito)<br>
                    <strong>Given</strong> el dueño ha elegido suspender un proceso de control interno<br>
                    <strong>When</strong> confirme su suspensión<br>
                    <strong>Then</strong> el proceso de control interno debe pasar a tener el estado 'SUSPENDIDO'<br>&nbsp;&nbsp;And se confirma la suspensión al usuario con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Intención de suspender un proceso de control interno<br>
                    <strong>Given</strong> el dueño tiene al menos un proceso de control interno<br>
                    <strong>When</strong> elige suspender el proceso de control interno<br>
                    <strong>Then</strong> se debe solicitar una confirmación que explique cuales son las consecuencias de suspender un proceso de control interno
                    </li>
                    <li>
                    <strong>Scenario:</strong> Suspender un proceso de control interno (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la suspensión de un proceso de control interno<br>
                    <strong>When</strong> el proceso falle<br>
                    <strong>Then</strong> se informa al usuario al razón del fallo mediante un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-29</td>
            <td>Cambiar estado de formato de registro</td>
            <td>Como Dueño de restaurante, quiero cambiar el estado de un formato de registro para controlar qué formatos de registros son visibles o utilizables para y por mis empleados</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de actualización de formato de registros<br>
                    <strong>Given</strong> el dueño se encuentra editando un formato de registros<br>
                    <strong>When</strong> selecciona cambiar el estado del formato de registros<br>
                    <strong>Then</strong> se deben visualizar los posibles estados ('ACTIVO' e 'INACTIVO')
                    </li>
                    <li>
                    <strong>Scenario:</strong> Actualizar estado de formato de registro a (éxito)<br>
                    <strong>Given</strong> el dueño esta visualizando los estados posibles de un formato de registros<br>
                    <strong>When</strong> selecciona un estado de formato de registros diferente al valor actual<br>
                    <strong>Then</strong> se actualiza el estado del formato de registros actual al nuevo valor elegido por el usuario<br>&nbsp;&nbsp;And se informa al usuario del cambio de estado con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Actualizar estado de formato de registro a (fallo)<br>
                    <strong>Given</strong> el dueño ha seleccionado un formato de registros diferente al valor actual<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se cambia el estado del formato de registros<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo con un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-30</td>
            <td>Listar procesos de control interno</td>
            <td>Como Dueño de restaurante, quiero visualizar el listado de todos los procesos de control interno para saber qué áreas de mi negocio se están modelando dentro del sistema</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Listar procesos de control interno<br>
                    <strong>Given</strong> el dueño posee al menos un proceso de control interno en su organización<br>
                    <strong>When</strong> ingrese al panel de procesos de control interno<br>
                    <strong>Then</strong> se muestran todos los procesos de control interno creados en la organización
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-31</td>
            <td>Listar formatos de registro</td>
            <td>Como Usuario del sistema con permisos de escritura para procesos de control, quiero ver los formatos de registro existentes asociados a un proceso de control interno para saber qué documentos o estructuras de control ya se encuentran presentes dentro del sistema</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Listar formatos de registro de un proceso de control interno<br>
                    <strong>Given</strong> el usuario se encuentra en el panel de procesos de control interno<br>&nbsp;&nbsp;And la organización posee al menos un proceso de control interno<br>&nbsp;&nbsp;And este proceso de control interno posee al menos un formato de registro<br>
                    <strong>When</strong> decida ver el desglose del proceso de control interno<br>
                    <strong>Then</strong> se muestran la lista de formatos de registro asociados a ese proceso de control interno
                    </li>
                </ul>
            </td>
            <td>EP-1</td>
        </tr>
        <tr>
            <td>US-14</td>
            <td>Vincular dispositivos IoT</td>
            <td>Como Usuario del sistema con permisos de modificación para dispositivos IoT, quiero registrar mis dispositivos IoT de seguridad para mi restaurante para asegurar que mi negocio esté protegido por el sistema integrado en caso de emergencias</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de añadir dispositivo<br>
                    <strong>Given</strong> el usuario cuenta con permisos de escritura para dispositivos IoT<br>
                    <strong>When</strong> elija la opción de añadir un nuevo dispositivo<br>
                    <strong>Then</strong> el sistema debe solicitar los datos de identificación del dispositivo (ej. ID, clave de activación)
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir dispositivo IoT (éxito)<br>
                    <strong>Given</strong> el usuario ha ingresado datos de identificación válidos para un dispositivo IoT<br>
                    <strong>When</strong> confirme la acción de añadir<br>
                    <strong>Then</strong> el dispositivo se vincula a la organización y al sistema<br>&nbsp;&nbsp;And se confirma al usuario el éxito de la operación mediante un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir dispositivo IoT (fallo)<br>
                    <strong>Given</strong> el usuario ha solicitado la vinculación de un dispositivo IoT<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> el dispositivo no se vincula a la organización<br>&nbsp;&nbsp;And se informa al usuario la razón específica del fallo mediante un mensaje de error
                    </li>
                    <li>El dato solicitado para vincular el dispositivo IoT debería ser fácil de ubicar para el usuario</li>
                </ul>
            </td>
            <td>EP-2</td>
        </tr>
        <tr>
            <td>US-15</td>
            <td>Monitorear datos de seguridad en tiempo real</td>
            <td>Como Dueño de restaurante con permisos de lectura para dispositivos IoT, quiero ver en tiempo real la información de mis dispositivos IoT desde cualquier lugar para tener visibilidad constante sobre el estado de seguridad de mi negocio sin tener que estar físicamente presente</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Error de transferencia de datos (consulta directa)<br>
                    <strong>Given</strong> que el usuario cuenta con permisos de lectura para dispositivos IoT<br>&nbsp;&nbsp;And la organización cuenta con al menos un dispositivo IoT conectado<br>&nbsp;&nbsp;And alguno de los dispositivos presenta problemas de conexión<br>
                    <strong>When</strong> ingrese a una vista que requiera los datos de dicho dispositivo<br>
                    <strong>Then</strong> se debe alertar al usuario de que el(los) dispositivo(s) IoT requerido(s) presentan problemas de conexión con un mensaje que lo inste a revisar las instalaciones de los dispositivos
                    </li>
                    <li>La funcionalidad debe contar con una vista agregada de múltiples dispositivos IoT de forma simultánea.</li>
                    <li>La funcionalidad debe contar con una vista individual de un único dispositivo IoT.</li>
                </ul>
            </td>
            <td>EP-2</td>
        </tr>
        <tr>
            <td>US-17</td>
            <td>Desvincular dispositivo IoT</td>
            <td>Como Usuario del sistema con permisos de escritura para dispositivos IoT, quiero desvincular dispositivos IoT del sistema integrado para dejar de visualizar en el sistema aquellos que ya dejaron de funcionar o van a ser reemplazados</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de desvincular dispositivo<br>
                    <strong>Given</strong> el usuario cuenta con permisos de escritura para dispositivos IoT<br>&nbsp;&nbsp;And la organización a la que pertenece cuenta con al menos un dispositivo IoT vinculado<br>
                    <strong>When</strong> elija desvincular el dispositivo<br>
                    <strong>Then</strong> se debe solicitar una confirmación de la acción al usuario
                    </li>
                    <li>
                    <strong>Scenario:</strong> Desvincular dispositivo IoT (éxito)<br>
                    <strong>Given</strong> el usuario quiere desvincular un dispositivo IoT vinculado<br>
                    <strong>When</strong> confirme la desvinculación<br>
                    <strong>Then</strong> se desvincula de la organización y el sistema el dispositivo IoT seleccionado<br>&nbsp;&nbsp;And se confirma al usuario la desinvulación con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Desvincular dispositivo IoT (fallo)<br>
                    <strong>Given</strong> el usuario ha confirmado la desvinculación de un dispositivo IoT vinculado<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se desvincula el dispositivo de la organización ni el sistema<br>&nbsp;&nbsp;And se informa la usuario la razón del fallo mediante un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-2</td>
        </tr>
        <tr>
            <td>US-18</td>
            <td>Listar dispositivos IoT</td>
            <td>Como Usuario del sistema, quiero visualizar la lista de dispositivos IoT que he registrado en el sistema para asegurarme de que vinculé todos los dispositivos que he adquirido y que se encuentran en buen estado</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Listar dispositivos IoT conectados<br>
                    <strong>Given</strong> el usuario posee permisos de lectura para dispositivos IoT<br>&nbsp;&nbsp;And la organización a la que pertenece posee al menos un dispositivo IoT vinculado<br>
                    <strong>When</strong> el usuario ingrese al panel IoT<br>
                    <strong>Then</strong> se deben visualizar todos los dispositivos IoT vinculados a la organización
                    </li>
                </ul>
            </td>
            <td>EP-2</td>
        </tr>
        <tr>
            <td>US-19</td>
            <td>Cambiar identificador alias de dispositivo IoT</td>
            <td>Como Usuario del sistema con permisos de escritura para dispositivos IoT, quiero cambiar el identificador alias de mis dispositivos IoT para mantenerlo actualizado y relevante como por ejemplo, al cambiarlo de ubicación</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de cambio de nombre para dispositivos IoT<br>
                    <strong>Given</strong> el usuario tiene permisos de escritura para dispositivos IoT<br>&nbsp;&nbsp;And la organización tiene al menos un dispositivo IoT conectado al sistema<br>
                    <strong>When</strong> seleccione cambiar el nombre de un dispositivo IoT<br>
                    <strong>Then</strong> se debe solicitar el nuevo nombre para el dispositivo, usando como valor inicial el nombre alias actual
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar nombre alias a dispositivo IoT (éxito)<br>
                    <strong>Given</strong> el usuario ha ingresado el nuevo nombre alias para un dispositivo IoT<br>
                    <strong>When</strong> confirme el cambio del alias<br>
                    <strong>Then</strong> se debe actualizar el alias del dispositivo al nuevo<br>&nbsp;&nbsp;And se debe confirmar el cambio al usuario con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar nombre alias a dispositivo IoT (fallo)<br>
                    <strong>Given</strong> el usuario ha confirmado el cambio de alias de un dispositivo IoT<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se debe actualizar el alias del dispositivo<br>&nbsp;&nbsp;And se explica al usuario la razón del fallo con un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-2</td>
        </tr>
        <tr>
            <td>US-24</td>
            <td>Configurar ubicación (dirección física y referencia)</td>
            <td>Como Dueño de restaurante, quiero configurar la información de ubicación de mi restaurante incluyendo dirección física y referencia para los servicios de emergencia tengan los datos básicos precisos en caso de emergencia</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Valores por defecto del formulario (datos no configurados previamente)<br>
                    <strong>Given</strong> el dueño no ha configurado previamente la ubicación de su restaurante<br>
                    <strong>When</strong> ingresa a la configuración de ubicación de su restaurante<br>
                    <strong>Then</strong> los campos de ubicación física y referencia deben estar vacíos
                    </li>
                    <li>
                    <strong>Scenario:</strong> Persistencia de datos en el formulario (datos configurados previamente)<br>
                    <strong>Given</strong> el dueño ha configurado previamente la ubicación de su restaurante<br>
                    <strong>When</strong> ingresa a la configuración de ubicación de su restaurante<br>
                    <strong>Then</strong> los campos de ubicación física, coordenadas, referencias y archivos multimedia deben mostrar la información registrada en la última sesión de guardado.
                    </li>
                    <li>Dada la naturaleza de la información, la interfaz para esta funcionalidad debería usar un formulario reactivo que permite guardar los cambios al modificar la información.</li>
                </ul>
            </td>
            <td>EP-3</td>
        </tr>
        <tr>
            <td>US-25</td>
            <td>Realizar llamada de emergencia</td>
            <td>Como Usuario del sistema, quiero iniciar una llamada telefónica a servicios de emergencia y tener la información de mi ubicación visible al mismo tiempo para pueda comunicarme de forma efectiva y asegurar una respuesta rápida y precisa en situaciones críticas, minimizando el error humano.</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Superposición de datos del restaurante durante llamada<br>
                    <strong>Given</strong> el restaurante tiene configurado los datos de su ubicación física y referencia<br>
                    <strong>When</strong> se realice una llamada de emergencia<br>
                    <strong>Then</strong> estos datos deben ser visibles para el usuario durante la llamada
                    </li>
                    <li>La opción de realizar la llamada a emergencias debería ser fácil de encontrar, pero difícil de accionar por accidente, dado que realizar llamadas innecesarias a las líneas de emergencias es delito.</li>
                </ul>
            </td>
            <td>EP-3</td>
        </tr>
        <tr>
            <td>US-27</td>
            <td>Activación automática de dispositivos IoT contra-incendios</td>
            <td>Como Dueño de restaurante, quiero que los dispositivos contra-incendios (como alarmas, aspersores, extractores de humo, etc.) se activen de forma automática ante la detección de fuego para tener la seguridad de que existe una primera línea de defensa que proteja mi negocio y mitigue incluso si mis trabajadores no pueden hacerlo</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Activación automática de los dispositivos IoT<br>
                    <strong>Given</strong> al menos un dispositivo IoT se encuentra vinculado al nodo EDGE<br>
                    <strong>When</strong> se detecten valores que atentan contra los establecidos en la política<br>
                    <strong>Then</strong> se deben activar los dispositivos de acción correspondientes para responder a la emergencia
                    </li>
                    <li>Esta funcionalidad no debería fallar bajo ninguna circunstancia.</li>
                </ul>
            </td>
            <td>EP-3</td>
        </tr>
        <tr>
            <td>US-28</td>
            <td>Activación manual de dispositivos IoT contra-incendios</td>
            <td>Como Usuario del sistema en presencia cercana al dispositivo IoT, quiero activar de forma manual dispositivos contra-incendios (como alarmas, aspersores, turbinas extractoras, etc.)  para mitigar un riesgo potencial o no detectado por el sistema y alertar al equipo y clientes en el local</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Accionamiento remoto de dispositivos<br>
                    <strong>Given</strong> que el usuario cuenta con permisos de lectura para dispositivos IoT<br>
                    <strong>When</strong> cuando seleccione accionar un dispositivo IoT<br>
                    <strong>Then</strong> el dispositivo IoT debe activar la función correspondiente
                    </li>
                    <li>La opción u opciones disponibles deben variar según el tipo de dispositivo conectado.</li>
                    <li>Esta funcionalidad no debería fallar bajo ninguna circunstancia.</li>
                </ul>
            </td>
            <td>EP-3</td>
        </tr>
        <tr>
            <td>US-33</td>
            <td>Configurar ubicación GPS (coordenadas exactas)</td>
            <td>Como Dueño de restaurante, quiero configurar las coordenadas GPS de mi establecimiento mediante un mapa interactivo para los servicios de emergencia tengan la ubicación exacta y puedan llegar sin confusiones o demoras al buscar la calle por su nombre.</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Permiso de geolocalización denegado<br>
                    <strong>Given</strong> el sistema ha solicitado el permiso de ubicación<br>
                    <strong>When</strong> el usuario rechaza la solicitud del sistema<br>
                    <strong>Then</strong> el mapa debe mostrar una vista predeterminada<br>&nbsp;&nbsp;And debe mostrarse un mensaje informativo indicando que la geolocalización automática no está disponible y se requiere ajuste manual
                    </li>
                    <li>
                    <strong>Scenario:</strong> Agregar dirección GPS (éxito)<br>
                    <strong>Given</strong> el usuario se encuentra seleccionando la ubicación GPS en el mapa<br>&nbsp;&nbsp;And un marcador está posicionado en el mapa<br>
                    <strong>When</strong> el usuario confirma la dirección en el mapa<br>
                    <strong>Then</strong> el sistema guarda la ubicación correspondiente en coordenadas<br>&nbsp;&nbsp;And se informa al usuario que los datos se guardaron exitosamente con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Solicitar permiso de geolocalización<br>
                    <strong>Given</strong> el usuario accede a la sección de configuración de ubicación GPS<br>&nbsp;&nbsp;And el sistema no tiene permisos GPS aún<br>
                    <strong>When</strong> decide agregar la ubicación GPS <br>
                    <strong>Then</strong> el sistema debe disparar la solicitud nativa del navegador o dispositivo para acceder a la ubicación del usuario
                    </li>
                    <li>
                    <strong>Scenario:</strong> Permiso de geolocalización aceptado<br>
                    <strong>Given</strong> el sistema ha solicitado el permiso de ubicación<br>
                    <strong>When</strong> el usuario acepta la solicitud del sistema<br>
                    <strong>Then</strong> el mapa debe centrarse en las coordenadas detectadas por el dispositivo<br>&nbsp;&nbsp;And el marcador debe posicionarse automáticamente en ese punto
                    </li>
                    <li>
                    <strong>Scenario:</strong> Agregar dirección GPS (fallo)<br>
                    <strong>Given</strong> el usuario ha confirmado al dirección en el mapa<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se guarda la dirección ingresada<br>&nbsp;&nbsp;And el sistema no abandona la interfaz del mapa<br>&nbsp;&nbsp;And se debe informar al usuario que la información no fue guardada con un mensaje
                    </li>
                    <li>Dada la naturaleza de la información, esta debería guardarse inmediatamente tras haberlo ingresado.</li>
                </ul>
            </td>
            <td>EP-3</td>
        </tr>
        <tr>
            <td>US-10</td>
            <td>Invitar empleados</td>
            <td>Como Dueño de restaurante, quiero añadir a mis empleados al sistema y asignarles roles como 'Teniente' o 'Encargado' para delegar responsabilidades de forma clara y asegurar que mis trabajadores contribuyan al control interno según su asignación</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de añadir nuevo empleado<br>
                    <strong>Given</strong> el dueño se encuentra en el panel de Recursos Humanos<br>
                    <strong>When</strong> decida agregar un nuevo empleado<br>
                    <strong>Then</strong> se deben solicitar los datos obligatorios del empleado (nombre, apellido, correo electrónico y rol)<br>&nbsp;&nbsp;And el campo obligatorio de rol debe tener como valor por defecto el rol 'ENCARGADO'<br>&nbsp;&nbsp;And se incluye una explicación del significado del rol
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambio de rol al añadir nuevo empleado<br>
                    <strong>Given</strong> el dueño se encuentra añadiendo un nuevo empleado<br>
                    <strong>When</strong> cambie el valor del rol del nuevo empleado<br>
                    <strong>Then</strong> se debe actualizar la descripción que explica el significado de los roles a una correspondiente al nuevo rol seleccionado
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir nuevo empleado (éxito)<br>
                    <strong>Given</strong> el dueño ha llenado todos los campos de nuevo empleado <br>&nbsp;&nbsp;And los nombres y apellidos son válidos (no vacíos y sin caracteres especiales)<br>&nbsp;&nbsp;And el correo es válido (no vacío, cumple REGEX de correo electrónico)<br>&nbsp;&nbsp;And el correo no pertenece a ningún empleado ya presente en la organización<br>
                    <strong>When</strong> cuando confirme la adición del nuevo empleado<br>
                    <strong>Then</strong> se debe registrar una invitación en el sistema con los datos del empleado proporcionados<br>&nbsp;&nbsp;And se confirma al usuario que la invitación a la organización
                    </li>
                    <li>
                    <strong>Scenario:</strong> Añadir nuevo empleado (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la adición de un nuevo empleado<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se genera ninguna invitación<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo con un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-4</td>
        </tr>
        <tr>
            <td>US-11</td>
            <td>Modificar permisos de los usuarios</td>
            <td>Como Dueño de restaurante, quiero ajustar qué acciones puede realizar cada usuario del sistema en función de las áreas IoT, RRHH y Procesos de control para mantener un control preciso sobre la seguridad y las responsabilidades, protegiendo mi inversión y garantizando la integridad de las operaciones</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de modificar los permisos de un empleado<br>
                    <strong>Given</strong> que el dueño tiene registrado al menos un empleado<br>
                    <strong>When</strong> seleccione modificar los permisos asignados a uno de los empleados<br>
                    <strong>Then</strong> se debe mostrar el checklist de permisos asociados con el rol correspondiente al empleado<br>&nbsp;&nbsp;And se debe evidenciar los permisos relativos del empleado relativos a su rol
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar los permisos de empleado (éxito)<br>
                    <strong>Given</strong> el dueño se encuentra cambiando los permisos de un empleado<br>&nbsp;&nbsp;And ha realizado cambios mediante los check a los permisos del empleado<br>
                    <strong>When</strong> confirme los cambios<br>
                    <strong>Then</strong> se deben modificar los permisos del usuario en el sistema a los nuevos específicados por el usuario<br>&nbsp;&nbsp;And se informa al usuario el éxito de la operación con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Cambiar los permisos de empleado (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado los cambios de permisos de un empleado<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> no se cambian los permisos del empleado<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo con un mensaje
                    </li>
                </ul>
            </td>
            <td>EP-4</td>
        </tr>
        <tr>
            <td>US-35</td>
            <td>Primer ingreso al sistema por correo electrónico</td>
            <td>Como Dueño de restaurante, quiero que al añadir empleados a mi organización puedan recibir la invitación formal a su correo para tener una forma segura y rápida de verificar que el proceso ha funcionado correctamente</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Aceptar invitación <br>
                    <strong>Given</strong> el usuario invitado ha recibido una invitación a un restaurante<br>
                    <strong>When</strong> acepte la invitación en el correo electrónico<br>
                    <strong>Then</strong> se lo debe redirigir a la página de la aplicación web o aplicación móvil a visualizar las invitaciones
                    </li>
                    <li>El proceso para enviar el correo de invitación debe contar con un hipervinculo que redirija al usuario a la página web o aplicación al mismo tiempo que acepta la invitación.</li>
                    <li>La operación de envío del correos debería ser asíncrona, usando reintentos y consistencia eventual para garantizar la entrega.</li>
                </ul>
            </td>
            <td>EP-4</td>
        </tr>
        <tr>
            <td>US-36</td>
            <td>Visualizar invitaciones</td>
            <td>Como Cocinero, quiero poder ver las invitaciones que he recibido a distintos restaurantes para poder unirme al sistema del restaurante en el que trabajo</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Visualizar invitaciones<br>
                    <strong>Given</strong> el cocinero tiene invitaciones pendientes<br>
                    <strong>When</strong> el panel de invitaciones cargue<br>
                    <strong>Then</strong> el sistema debe mostrar una lista con todas las invitaciones pendientes<br>&nbsp;&nbsp;And cada elemento de la lista debe incluir el nombre de la organización, la fecha de la invitación y el estado 'PENDIENTE'
                    </li>
                </ul>
            </td>
            <td>EP-4</td>
        </tr>
        <tr>
            <td>US-37</td>
            <td>Registrarme con mi cuenta de Google</td>
            <td>Como Dueño de restaurante, quiero crear mi cuenta de usuario utilizando mi identidad de Google para simplifique el proceso de acceso y pueda concentrarme en proteger mi inversión sin demoras</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Registrarse con cuenta de Google (éxito)<br>
                    <strong>Given</strong> el usuario se encuentra en la interfaz de registro<br>&nbsp;&nbsp;And y la cuenta de Google del registro no se encuentra registrada aún<br>
                    <strong>When</strong> se registre usando dicha cuenta de Google<br>
                    <strong>Then</strong> se debe utilizar todos los datos proporcionados por OAuth para generarle un usuario en el sistema
                    </li>
                    <li>
                    <strong>Scenario:</strong> Registrarse con cuenta de Google (fallo)<br>
                    <strong>Given</strong> el usuario se ha registrado con su cuenta Google<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> se informa al usuario la razón del fallo con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Registrarse con cuenta de Google (cuenta ya registrada)<br>
                    <strong>Given</strong> el usuario se encuentra en la interfaz de registro<br>&nbsp;&nbsp;And y la cuenta de Google ya se encuentra registrada<br>
                    <strong>When</strong> se registre usando dicha cuenta de Google<br>
                    <strong>Then</strong> no se registra al usuario nuevamente<br>&nbsp;&nbsp;And se informa al usuario que dicha cuenta se encuentra registrada, por lo que debe hacer login
                    </li>
                </ul>
            </td>
            <td>EP-5</td>
        </tr>
        <tr>
            <td>US-38</td>
            <td>Iniciar sesión con mi cuenta de Google</td>
            <td>Como Usuario del sistema, quiero acceder al sistema utilizando mi identidad de Google para evite recordar credenciales adicionales y tenga una experiencia de inicio de sesión rápida y segura</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Iniciar sesión con Google (éxito)<br>
                    <strong>Given</strong> el usuario se encuentra en la interfaz de login del sistema<br>&nbsp;&nbsp;And se ha registrado previamente con OAuth Google<br>
                    <strong>When</strong> inicie sesión usando su cuenta de Google<br>
                    <strong>Then</strong> el sistema debe utilizar los datos proporcionados por OAuth para identificar al usuario
                    </li>
                    <li>
                    <strong>Scenario:</strong> Iniciar sesión con Google (fallo)<br>
                    <strong>Given</strong> el usuario ha iniciado sesión con OAuth Google<br>
                    <strong>When</strong> la operación falle<br>
                    <strong>Then</strong> se informa al usuario la razón del fallo con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Iniciar sesión con Google (no registrado aún)<br>
                    <strong>Given</strong> el usuario se encuentra en la interfaz de login del sistema<br>&nbsp;&nbsp;And no se ha registrado aún con OAuth Google<br>
                    <strong>When</strong> inicie sesión usando su cuenta de Google<br>
                    <strong>Then</strong> se informa al usuario que debe registrarse antes de iniciar sesión
                    </li>
                </ul>
            </td>
            <td>EP-5</td>
        </tr>
        <tr>
            <td>US-39</td>
            <td>Hero section</td>
            <td>Como Visitante de Landing Page, quiero ver una Hero Section de alto impacto que resuma de qué se trata el producto para tener una razón principal para interesarme a seguir revisando la landing page</td>
            <td>
                <ul>
                    <li>La sección debería ocupar toda la pantalla tanto en mobile como en desktop.</li>
                </ul>
            </td>
            <td>EP-6</td>
        </tr>
        <tr>
            <td>US-40</td>
            <td>Features</td>
            <td>Como Visitante de Landing Page, quiero quiero ver un listado de las funcionalidades del producto para tener razones concretas para querer adquirir el producto o servicio</td>
            <td>
                <ul>
                    <li>En la versión desktop debería ocupar toda la pantalla.</li>
                    <li>La versión mobile debería colocar un feature por vertical height del dispositivo.</li>
                </ul>
            </td>
            <td>EP-6</td>
        </tr>
        <tr>
            <td>US-41</td>
            <td>About the Product</td>
            <td>Como Visitante de Landing Page, quiero quiero una sección con un demo en vídeo del producto para ver el funcionamiento del producto</td>
            <td>
                <ul>
                    <li>Este video debe encontrarse incustrado en el sitio usando YouTube como fuente.</li>
                </ul>
            </td>
            <td>EP-6</td>
        </tr>
        <tr>
            <td>US-42</td>
            <td>About the Team</td>
            <td>Como Visitante de Landing Page, quiero tener una sección con una presentación del equipo de desarrollo para conocer las personas a cargo del producto y sentir confianza a través de su presencia</td>
            <td>
                <ul>
                    <li>El vídeo debe contener a todos los integrantes del equipo.</li>
                    <li>El vídeo debe contener secciones del equipo trabajando juntos.</li>
                </ul>
            </td>
            <td>EP-6</td>
        </tr>
        <tr>
            <td>US-43</td>
            <td>Suscripciones</td>
            <td>Como Visitante de Landing Page, quiero ver las opciones para adquirir el producto para evaluar si deseo adquirirlo en función del precio</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de compra<br>
                    <strong>Given</strong> el visitante del landing page se encuentra en la sección suscripciones de la landing page<br>
                    <strong>When</strong> elija adquirir alguna de las suscripciones<br>
                    <strong>Then</strong> se insta al usuario a registrarse o iniciar sesión en la aplicación web
                    </li>
                    <li>La sección debería ocupar toda la pantalla en la versión desktop.</li>
                </ul>
            </td>
            <td>EP-6</td>
        </tr>
        <tr>
            <td>US-45</td>
            <td>Visualizar suscripciones</td>
            <td>Como Dueño de restaurante, quiero ver las suscripciones disponibles  para seleccionar cual deseo adquirir para mi organización</td>
            <td>
                <ul>
                    <li>Las suscripciones disponibles deben contar con todas sus características disponibles</li>
                </ul>
            </td>
            <td>EP-8</td>
        </tr>
        <tr>
            <td>US-46</td>
            <td>Suscribirse</td>
            <td>Como Dueño de restaurante, quiero seleccionar una suscripción específica y adquirirla para obtener los beneficios que ofrece</td>
            <td>
                <ul>
                    <li>
                    <strong>Scenario:</strong> Intención de adquirir suscripción<br>
                    <strong>Given</strong> el dueño está visualizando las suscripciones<br>
                    <strong>When</strong> seleccione adquirir una de ellas<br>
                    <strong>Then</strong> se debe solicitar un medio de pago a modo de confirmación
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adquirir suscripción (éxito)<br>
                    <strong>Given</strong> el dueño ha seleccionado una suscripción<br>&nbsp;&nbsp;And y ha introducido un método de pago<br>
                    <strong>When</strong> confirme la compra<br>
                    <strong>Then</strong> se debe ejecutar una transacción que realiza el cobro correspondiente según la membresía seleccionada<br>&nbsp;&nbsp;And se activa la suscripción seleccionada para el usuario<br>&nbsp;&nbsp;And se confirma el éxito de la transacción al usuario con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adquirir suscripción (fallo)<br>
                    <strong>Given</strong> el dueño ha confirmado la compra de una suscripción<br>
                    <strong>When</strong> la transacción falle<br>
                    <strong>Then</strong> no se realiza ningún cobro<br>&nbsp;&nbsp;And no se activa ninguna suscripción<br>&nbsp;&nbsp;And se informa al usuario la razón del fallo con un mensaje
                    </li>
                    <li>
                    <strong>Scenario:</strong> Adquirir suscripción (ya suscrito)<br>
                    <strong>Given</strong> el dueño ha seleccionado una suscripción<br>&nbsp;&nbsp;And ha introducido un método de pago<br>&nbsp;&nbsp;And el dueño ya cuenta con una suscripción en su cuenta<br>
                    <strong>When</strong> confirme la compra<br>
                    <strong>Then</strong> no se realiza ningún cobro<br>&nbsp;&nbsp;And no se activa ni se renueva ninguna suscripción<br>&nbsp;&nbsp;And se informa al usuario que ya se encuentra suscrito
                    </li>
                    <li>Se debe usar una pasarela de pagos.</li>
                </ul>
            </td>
            <td>EP-8</td>
        </tr>
    </tbody>
</table>