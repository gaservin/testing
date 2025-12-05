# BilogChallenge - Backend

API para la gestión de especialidades médicas.

## Endpoints principales

| Método | Ruta                | Descripción                                          |
| ------ | ------------------- | ---------------------------------------------------- |
| GET    | /api/specialty      | Lista todas las especialidades                       |
| GET    | /api/specialty/{id} | Obtiene una especialidad por ID                      |
| POST   | /api/specialty      | Crea una nueva especialidad                          |
| PUT    | /api/specialty/{id} | Actualiza una especialidad (control de concurrencia) |
| DELETE | /api/specialty/{id} | Elimina una especialidad                             |

## Arquitectura

El proyecto está estructurado en múltiples capas para asegurar separación de responsabilidades, escalabilidad y mantenimiento a largo plazo:

# API
- Punto de entrada de la aplicación.
- Contiene los controladores.
- Gestiona las solicitudes HTTP y retorna respuestas adecuadas.

# APPLICATION
- Contiene la lógica de negocio.
- Define interfaces, servicios, DTOs, mapeos, validaciones y excepciones.
- Implementa validaciones de unicidad y control de concurrencia mediante rowversion.

# DOMAIN
- Modela la entidad principal del sistema.

# INFRAESTRUCTURE
- Gestiona la persistencia y comunicación con la base de datos.
- Implementa los repositorios definidos en Application.

/Api
  └── Controladores
/Application
  ├── DTOs
  ├── Excepciones
  ├── Interfaces
      ├── Repositories
      ├── Servicies
  ├── Services 
  └── Mapeos
/Domain
  └── Entidades
/Infrastructure
  ├── Persistence
    └── Repositorios
  └── DbContext

## Decisiones de diseño

Arquitectura con separación de responsabilidades en capas.
Inversión de dependencias para evitar acoplamientos innecesarios.
DTOs, para no exponer directamente las entidades del dominio.
AutoMapper, para automatizar el mapeo entre entidades y DTOs.
Excepciones personalizadas, para mejorar la interación con el usuario.

# Configuración del proyecto

# Rquisitos
- .NET 8 SDK
- SQL Server
- Cadena de conexión

## Configurar base de datos

Editar appsettings.json: agregar 

"ConnectionStrings": {
  "DefaultConnection": ""
}

## Cómo levantar la API

- dotnet restore
- dotnet build
- dotnet run
