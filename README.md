# FutbolWebApp

Aplicación web de gestión de fútbol desarrollada con DataFlex 2025 y MySQL como parte de las prácticas de DAW.

## Sprint 1 - Vistas y Dashboard

### Tecnologías utilizadas
- DataFlex 2025 Studio 25.0
- MySQL y phpMyAdmin
- Git y GitHub

### Base de datos
Se utiliza la base de datos `futbol`, proporcionada para la práctica.

Tablas principales:
- entrenador
- jugador
- equipo
- liga
- posicion
- jugadorposicion

La tabla `jugadorposicion` permite asociar jugadores con sus posiciones.

### Vistas de la aplicación
Se han creado vistas de listado (Select) y ficha (Zoom) para:
- Entrenadores
- Jugadores
- Equipos
- Ligas
- Posiciones
- Posiciones de jugadores

### Dashboard
Se han configurado tarjetas para acceder a los listados de entrenadores, jugadores, equipos, ligas y posiciones.

Cada tarjeta utiliza la navegación de DataFlex mediante `WebRegisterPath` y `NavigatePath`.

### Control de versiones
El proyecto se organiza con Git y GitHub utilizando:
- `main`: versión principal.
- `develop`: integración de cambios.
- `feature/*`: desarrollo de funcionalidades y documentación.

### Estado del proyecto
Las vistas y la navegación principal funcionan en el navegador local.

Los archivos de conexión y configuración específicos del equipo no se incluyen en GitHub.
