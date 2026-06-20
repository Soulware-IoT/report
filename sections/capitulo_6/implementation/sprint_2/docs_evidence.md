En esta sección se presenta la documentación de los servicios RESTful desarrollados durante el sprint. La API sigue el estilo arquitectónico REST y utiliza JSON como formato de intercambio de datos. El backend ha sido implementado utilizando Spring Boot y sigue los principios de DDD con Spring Modulith. La documentación fue generada a partir de la especificación OpenAPI 3.1.0.

**Base URL (Producción):** `https://backend-production-c5e8.up.railway.app`

**Base URL (Local):** `http://localhost:8080`

---

### Security API — Edge

Endpoints consumidos exclusivamente por el Edge Gateway, autenticados mediante el header `X-Edge-Api-Key`.

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| POST | `/edge/readings` | Registrar un batch de lecturas IoT desde el Edge Gateway |
| GET | `/edge/registry` | Obtener el registro de dispositivos IoT asociados al Edge Gateway autenticado |
| GET | `/edge/me` | Obtener la identidad y estado del Edge Gateway autenticado |

---

### Security API — IoT Devices

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/organizations/{organizationId}/iot-devices` | Listar dispositivos IoT de una organización |
| POST | `/organizations/{organizationId}/iot-devices` | Vincular (claim) un dispositivo IoT provisionado a una organización |
| GET | `/iot-devices/{id}` | Obtener un dispositivo IoT por ID |
| PATCH | `/iot-devices/{id}` | Actualizar nombre, umbrales o estado de un dispositivo IoT |

---

### Security API — Edge Devices

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/organizations/{organizationId}/edge-device` | Obtener el Edge Device asociado a una organización |
| POST | `/organizations/{organizationId}/edge-device` | Vincular (claim) un Edge Device provisionado a una organización |
| GET | `/edge-device/{id}` | Obtener un Edge Device por ID |
| PATCH | `/edge-device/{id}` | Actualizar nombre o estado de un Edge Device |

---

### Security API — Provisioning (Internal)

Endpoints de uso interno para el aprovisionamiento de dispositivos. No están expuestos al cliente.

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| POST | `/internal/iot-devices/provision` | Provisionar un nuevo IoT Device (genera código y API Key) |
| POST | `/internal/edge-device/provision` | Provisionar un nuevo Edge Device (genera código y API Key) |

---

### Restaurant API — Organizations

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/organizations` | Listar organizaciones de un perfil (`?profileId=`) |
| POST | `/organizations` | Crear una organización |
| GET | `/organizations/{id}` | Obtener una organización por ID |
| PATCH | `/organizations/{id}` | Actualizar nombre, imagen o dirección de una organización |
| DELETE | `/organizations/{id}` | Eliminar una organización |

---

### Restaurant API — Organization Members

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/organizations/{organizationId}/members` | Listar miembros de una organización |
| GET | `/organizations/{organizationId}/members/{memberId}` | Obtener un miembro por ID |
| PUT | `/organizations/{organizationId}/members/{memberId}/permissions` | Actualizar permisos de un miembro (security, iot, internalControl) |
| DELETE | `/organizations/{organizationId}/members/{memberId}` | Eliminar un miembro de la organización |

---

### Restaurant API — Invitations

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/organizations/{organizationId}/invitations` | Listar invitaciones enviadas por una organización |
| POST | `/organizations/{organizationId}/invitations` | Enviar una invitación a un usuario por email |
| GET | `/invitations/{id}` | Obtener una invitación por ID |
| POST | `/invitations/{id}/accept` | Aceptar una invitación |
| POST | `/invitations/{id}/decline` | Rechazar una invitación |
| GET | `/profiles/{profileId}/invitations` | Listar invitaciones recibidas por un perfil |

---

### Profiles API

| Método | Endpoint | Descripción |
| ------ | -------- | ----------- |
| GET | `/profiles` | Obtener un perfil por email (`?email=`) |
| GET | `/profiles/{id}` | Obtener un perfil por ID |
| PATCH | `/profiles/{id}` | Actualizar nombre completo, nombre preferido o avatar de un perfil |