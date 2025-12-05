# BilogChallenge - Backend

API para gestionar especialidades médicas.

## Tecnologías
- .NET 8
- Entity Framework Core
- SQL Server
- AutoMapper

## Arquitectura



| Método | Ruta                | Descripción                                          |
| ------ | ------------------- | ---------------------------------------------------- |
| GET    | /api/specialty      | Lista todas las especialidades                       |
| GET    | /api/specialty/{id} | Obtiene una especialidad por ID                      |
| POST   | /api/specialty      | Crea una nueva especialidad                          |
| PUT    | /api/specialty/{id} | Actualiza una especialidad (control de concurrencia) |
| DELETE | /api/specialty/{id} | Elimina una especialidad                             |
