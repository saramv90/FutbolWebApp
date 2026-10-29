# Navegación de FutbolWebApp

## Introducción

Durante el Sprint 1 he trabajado con la navegación de DataFlex 2025 para conectar las distintas pantallas de la aplicación de fútbol.

El objetivo es poder acceder a los listados desde el Dashboard y consultar las fichas de los registros.

## 1. Dashboard

El Dashboard es la pantalla principal de FutbolWebApp.

He configurado cinco tarjetas:
- Entrenadores
- Jugadores
- Equipos
- Ligas
- Posiciones

Cada tarjeta permite acceder al listado correspondiente.

## 2. WebRegisterPath y NavigatePath

En Dashboard.wo he utilizado WebRegisterPath para registrar la navegación hacia las vistas de listado.

NavigatePath se ejecuta al pulsar una tarjeta y permite abrir la vista correspondiente.

Por ejemplo, la tarjeta de jugadores utiliza:

    WebRegisterPath ntNavigateForwardCustom oSelectJugador

    Procedure OnClick String sId String sParam
        Send NavigatePath
    End_Procedure

## 3. Navegación Select y Zoom

Para las tablas principales he creado dos tipos de vistas:

- Select: muestra un listado de registros.
- Zoom: muestra la ficha de un registro seleccionado.

Al seleccionar un jugador, por ejemplo, se puede acceder a su ficha con el nombre, apellido, nacionalidad y equipo.

La navegación también permite volver al listado anterior.

## 4. Relaciones entre tablas

La aplicación utiliza las relaciones configuradas en DataFlex.

Por ejemplo:
- Cada equipo pertenece a una liga.
- Cada jugador pertenece a un equipo.
- La tabla jugadorposicion relaciona jugadores con posiciones.

En los formularios relacionados he utilizado las opciones de búsqueda para seleccionar registros de otras tablas.

## 5. Pruebas realizadas

He probado la navegación en el navegador local.

He comprobado que:
- Las tarjetas del Dashboard abren los listados.
- Los listados muestran los datos de MySQL.
- Las fichas permiten consultar registros individuales.
- Las búsquedas permiten seleccionar datos relacionados.
- La asociación de jugadores y posiciones se guarda en la base de datos.

Como prueba he relacionado a Thibaut Courtois con las posiciones Portero y Defensa.

## 6. Conclusión

Con esta práctica he aprendido a organizar la navegación de una aplicación web en DataFlex, conectar vistas y trabajar con registros relacionados.

La aplicación queda preparada para continuar incorporando funcionalidades en el siguiente sprint.
