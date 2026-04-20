La User Task Matrix es una herramienta clave para desglosar las acciones específicas que las personas realizan dentro de nuestra plataforma. Al evaluar la recurrencia y el impacto de cada tarea, obtenemos la claridad necesaria para enfocar de manera eficiente nuestros esfuerzos de diseño y desarrollo, garantizando así una mejora continua en la experiencia del usuario.


| User Task | Roberto (Dueño) Frequency | Roberto (Dueño) Importance | José (Cocinero) Frequency | José (Cocinero) Importance |
| :--- | :--- | :--- | :--- | :--- |
| Leer el estado actual de temperatura y humo | Medium | Medium | High | Medium |
| Recibir alerta por anomalías térmicas o de humo | Low | High | Low | High |
| Registrar la ejecución de un nuevo mantenimiento | Low | Medium | Medium | High |
| Revisar fechas programadas de próximos mantenimientos | Medium | High | Medium | Medium |
| Descargar reporte de estado para Defensa Civil | Low | High | None | Low |
| Activar alarma o botón de pánico manualmente | None | Low | Low | High |
| Encender turbinas de ventilación manualmente | None | Low | High | Medium |
| Desactivar o silenciar una falsa alarma | Low | High | Low | High |
| Cancelar llamada a bomberos (tiempo de gracia) | Low | High | Low | High |
| Configurar números de emergencia y contactos | Low | High | None | Low |

La User Task Matrix revela una clara división en los modelos de interacción de ambos arquetipos, lo que dictará la arquitectura de la información de la solución. Por un lado, Roberto (el Dueño) tiene un perfil de usuario supervisor; sus interacciones son de baja frecuencia pero de altísima importancia, centradas en la configuración, la mitigación de riesgos financieros (cancelar falsas alarmas, recibir alertas críticas) y el cumplimiento normativo (reportes para Defensa Civil). Por otro lado, José (el Cocinero) es un usuario operativo con tareas de alta frecuencia, interactuando constantemente con el sistema en el día a día para monitorear el entorno, encender turbinas y registrar mantenimientos.
