En esta sección se presenta la documentación de los servicios RESTful desarrollados durante el sprint. La API sigue el estilo arquitectónico REST y utiliza JSON como formato de intercambio de datos. El backend ha sido implementado utilizando Spring Boot y sigue los principios de DDD.

### Intern Control API

Base URL: `http://localhost:8080/intern-control`

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/api/v1/control-processes` | Listar procesos de control interno por organización |
| POST | `/api/v1/control-processes` | Crear proceso de control interno |
| GET | `/api/v1/control-processes/{id}` | Obtener proceso de control interno por ID |
| DELETE | `/api/v1/control-processes/{id}` | Eliminar proceso de control interno |
| PATCH | `/api/v1/control-processes/{id}/rename` | Renombrar proceso de control interno |
| PATCH | `/api/v1/control-processes/{id}/suspend` | Suspender proceso de control interno |
| GET | `/api/v1/control-processes/{processId}/templates` | Listar formatos de registro de un proceso |
| POST | `/api/v1/control-processes/{processId}/templates` | Crear formato de registro |
| GET | `/api/v1/control-processes/{processId}/templates/{templateId}` | Obtener formato de registro por ID |
| PUT | `/api/v1/control-processes/{processId}/templates/{templateId}` | Actualizar nombre y/o columnas del formato de registro |
| PATCH | `/api/v1/control-processes/{processId}/templates/{templateId}/status` | Cambiar estado del formato de registro (ACTIVE o INACTIVE) |
| PATCH | `/api/v1/control-processes/{processId}/templates/{templateId}/suspend` | Suspender formato de registro |

### Restaurant API

Base URL: `http://localhost:8080/restaurant`

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| POST | `/api/v1/users` | Crear usuario y su organización automáticamente |
| POST | `/api/v1/users/register` | Registrar usuario sin organización asociada |
| GET | `/api/v1/users/{id}` | Obtener usuario por ID interno |
| GET | `/api/v1/users/{id}/organizations` | Listar organizaciones del usuario |
| GET | `/api/v1/users/by-auth/{authId}` | Obtener usuario por Auth ID (UUID) |
| POST | `/api/v1/organizations` | Crear organización |
| GET | `/api/v1/organizations/{id}` | Obtener organización por ID |
| GET | `/api/v1/organizations/{organizationId}/members` | Listar miembros de la organización |
| POST | `/api/v1/organizations/{organizationId}/members` | Agregar usuario a la organización |
| PATCH | `/api/v1/organizations/{organizationId}/members/{userId}/permissions` | Configurar permisos de un miembro |
| GET | `/api/v1/organizations/{organizationId}/members/{userId}/permissions/check` | Verificar permiso de un miembro en la organización |