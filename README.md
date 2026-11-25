# ⚽ FutbolWebApp

Aplicación web de gestión de fútbol desarrollada con **DataFlex 2025 (versión 25.0) y MySQL**, como parte de las prácticas del ciclo de Desarrollo de Aplicaciones Web (DAW).

**Autora:** Sara Montesinos Villalba  
**Proyecto:** FutbolWebApp  
**Estado:** Sprint 5 · Posiciones de cada jugador

**Fecha:** 25 de noviembre de 2026

---

## Sprint 5 · Posiciones de cada jugador

La ficha muestra las posiciones asignadas al jugador. Para modificarlas, abre **Jugadores**, elige un jugador guardado, pulsa el lápiz y selecciona **Editar Posiciones**. La lista izquierda contiene el catálogo completo. La derecha muestra las posiciones del jugador elegido. [Ficha de jugador](AppSrc/ZoomJugador.wo)

**Añadir** comprueba si la pareja `JugadorID` y `PosicionID` ya existe en `jugadorposicion`. Si existe, muestra un aviso. Si es nueva, guarda la asignación. **Quitar** elimina la asignación seleccionada en la lista derecha. La posición sigue disponible en el catálogo para otros jugadores. Ambos botones guardan el cambio en el momento. [Editor de posiciones](AppSrc/SelectJugadorPosicion.wo)

### Pruebas en local con Thibaut Courtois

| Acción | Resultado observado |
|---|---|
| Intentar añadir Portero cuando ya estaba asignado | Apareció el aviso «Esta posición ya está asignada al jugador» y Portero siguió apareciendo una sola vez. |
| Añadir Defensa y Centrocampista y volver a la ficha | La ficha mostró Portero, Defensa y Centrocampista. |
| Quitar las dos posiciones de prueba y volver a la ficha | Courtois volvió a figurar solo como Portero. |

## Sprint 4 · Validaciones y control de equipos por liga

Al cambiar un equipo de liga, la aplicación resta una plaza ocupada en la liga de origen y suma una en la de destino. Si la liga de destino ha alcanzado su máximo, rechaza el cambio y conserva tanto la asignación original como los dos contadores. Esta lógica está en el diccionario de equipos, en los métodos `Backout` y `Update`. [Ver implementación](DDSrc/cequipoDataDictionary.dd)

La ficha de liga muestra la ocupación encima del listado de clubes. Con plazas disponibles, el indicador aparece en verde. Al alcanzar el máximo, pasa a rojo y añade el texto «Liga completa». [Ver ficha de liga](AppSrc/ZoomLiga.wo)

### Validaciones y gestión de entrenadores

- Los diccionarios de datos protegen las claves y definen los campos obligatorios. En las fichas de jugador y entrenador, el nombre y el apellido se introducen en el alta y quedan bloqueados tras guardar.
- Las fichas de jugador y entrenador permiten elegir la nacionalidad en un desplegable. Ambas listas leen las descripciones del tipo `NACION` en `CodeMast`.
- El botón **Despedir** conserva la ficha del entrenador y guarda `NULL` en `EquipoID`, de modo que el entrenador queda disponible. [Ver ficha de entrenador](AppSrc/ZoomEntrenador.wo)

### Pruebas realizadas en local

| Prueba | Resultado observado |
|---|---|
| Cambiar el Arsenal FC a una liga con plazas | Los contadores de ambas ligas coincidieron con el recuento de equipos en MySQL. |
| Intentar el cambio con la liga de destino llena | La aplicación mostró el aviso y mantuvo el equipo en su liga con los contadores originales. |
| Consultar la Premier League con máximos de 3 y 20 | Con tres clubes, la ficha mostró «3 de 3 equipos · Liga completa» en rojo y, tras restaurar el máximo, «3 de 20 equipos» en verde. |
| Crear una liga dejando el país vacío | El formulario señaló el campo **País** como obligatorio al intentar guardar. |
| Despedir a Arne Slot | Se comprobó en MySQL que su registro seguía existiendo con `EquipoID` a `NULL`. |
| Guardar una nacionalidad y reabrir la ficha | La selección se conservó. En la ficha del jugador Dani Calatrava se verificó también el bloqueo de nombre y apellido. |

[Consultar el commit de implementación del Sprint 4](https://github.com/saramv90/FutbolWebApp/commit/57a9370b4ede639f4d9c594c6363cb67a154d9d1)

## 1. Descripción del proyecto

FutbolWebApp es una aplicación web que permite consultar y gestionar información relacionada con el fútbol.

El proyecto organiza los datos en diferentes apartados:

- Entrenadores
- Jugadores
- Equipos
- Ligas
- Posiciones
- Relaciones entre jugadores y posiciones

La aplicación utiliza una base de datos MySQL y una interfaz creada mediante DataFlex WebApp.

## 2. Sprint 1 – Estructura inicial

Durante el primer Sprint se creó la estructura inicial de la aplicación, incluyendo:

- Configuración del proyecto en DataFlex Studio.
- Conexión con la base de datos.
- Creación de las vistas de selección y detalle.
- Configuración de los Data Dictionaries.
- Desarrollo del Dashboard principal.
- Navegación básica entre las distintas secciones.

## 3. Sprint 2 – Navegación y diseño visual

El segundo Sprint se ha centrado en mejorar la navegación, las relaciones entre los datos y la presentación visual de la aplicación.

### 3.1. Navegación entre vistas

Se ha trabajado con diferentes mecanismos de navegación de DataFlex, utilizando:

- `WebRegisterPath`
- `NavigatePath`
- `ntNavigateForward`
- `ntNavigateForwardCustom`
- `OnNavigateForward`

Estos mecanismos permiten acceder a los listados, abrir fichas individuales y navegar entre secciones relacionadas.

### 3.2. Títulos dinámicos

Se han personalizado los encabezados de las fichas para mostrar información del registro seleccionado.

Por ejemplo:

- Jugador: Thibaut Courtois
- Entrenador: Pep Guardiola
- Equipo: Real Madrid
- Liga: LaLiga

También se muestran títulos específicos cuando se accede a formularios de creación, como «Nuevo jugador», «Nuevo entrenador», «Nuevo equipo» y «Nueva liga».

### 3.3. Relaciones entre tablas

Se han trabajado las relaciones entre los diferentes elementos de la base de datos mediante los Data Dictionaries.

Entre las funcionalidades desarrolladas destacan:

- Consulta de los equipos asociados a una liga.
- Visualización de equipos dentro de la ficha de una liga.
- Selección de la liga correspondiente a un equipo.
- Selección del equipo asociado a un entrenador.
- Acceso al listado de posiciones desde la ficha de un jugador.

Se han utilizado componentes como `cWebList`, `cWebForm`, `cWebButton` y los correspondientes Data Dictionaries.

### 3.4. Rediseño del Dashboard – Street Football

Se ha realizado una personalización completa del panel principal, sustituyendo el diseño inicial por una interfaz inspirada en el fútbol urbano.

**Características del nuevo diseño:**

- Colores verdes oscuros, negro, blanco y detalles rojos.
- Tipografía deportiva para los títulos.
- Tarjetas con franjas diagonales.
- Iconos identificativos para cada sección.
- Subtítulos descriptivos.
- Efectos visuales al pasar el ratón.
- Personalización de la cabecera principal.
- Distribución adaptable a diferentes tamaños de pantalla.

El Dashboard contiene seis tarjetas:

| Sección | Descripción |
|---|---|
| Bienvenido | Acceso al panel principal |
| Entrenadores | Dirección técnica |
| Jugadores | Plantillas y fichas |
| Equipos | Gestión de clubes |
| Ligas | Competiciones |
| Posiciones | Demarcaciones |

### 3.5. Personalización mediante CSS

Se ha modificado el archivo:

`AppHtml/CssStyle/application.css`

Se han creado clases CSS específicas para personalizar las tarjetas, evitando conflictos con los estilos originales de DataFlex.

También se han utilizado variables CSS para adaptar los colores del tema `Df_Material` a la estética del proyecto.

### 3.6. Diseño responsive

Se ha comprobado el comportamiento visual del Dashboard utilizando las herramientas de desarrollador de Google Chrome.

La prueba se ha realizado con una simulación de **iPhone 16 (393 × 852 píxeles)**.

Se ha verificado que las tarjetas se reorganizan en una sola columna y mantienen visibles sus títulos, subtítulos e iconos.

La comprobación corresponde a una simulación de navegador; el acceso desde un teléfono físico no forma parte de las pruebas completadas.

## 4. Archivos principales del Sprint 2

| Archivo | Función |
|---|---|
| `AppSrc/Dashboard.wo` | Dashboard y navegación principal |
| `AppSrc/ZoomJugador.wo` | Personalización de la ficha de jugador |
| `AppSrc/ZoomEntrenador.wo` | Personalización de la ficha de entrenador |
| `AppSrc/ZoomEquipo.wo` | Personalización de la ficha de equipo |
| `AppSrc/ZoomLiga.wo` | Ficha de liga y equipos relacionados |
| `AppHtml/CssStyle/application.css` | Diseño visual Street Football |

## 5. Pruebas del Sprint 2

Durante el Sprint se han realizado comprobaciones de compilación, navegación y visualización.

Se han probado los accesos desde el Dashboard a los cinco listados principales:

- Listado de entrenadores.
- Listado de jugadores.
- Listado de equipos.
- Listado de ligas.
- Listado de posiciones.

También se ha revisado la presentación de fichas individuales, los títulos dinámicos y las relaciones entre distintas vistas.

Se han corregido errores de estructura del código DataFlex y problemas de carga y aplicación de estilos CSS.

El Dashboard final se ha comprobado visualmente tanto en escritorio como en la simulación móvil.

## 6. Tecnologías utilizadas

- **DataFlex 2025 (25.0):** desarrollo de la aplicación web.
- **MySQL:** almacenamiento de datos.
- **HTML y CSS:** personalización de la interfaz.
- **Visual Studio Code:** edición de estilos.
- **Google Chrome DevTools:** pruebas visuales y responsive.
- **Git y GitHub:** control de versiones.

## 7. Ejecución del proyecto

El proyecto está preparado para ejecutarse en un entorno local con DataFlex Studio 2025, la configuración web correspondiente y acceso a la base de datos.

Para abrir la aplicación en el entorno de desarrollo:

1. Abrir el workspace de FutbolWebApp en DataFlex Studio.
2. Comprobar la configuración de la conexión a la base de datos.
3. Seleccionar `WebApp.src`.
4. Compilar y ejecutar la aplicación.
5. Acceder desde el navegador a la dirección local configurada.

Dirección utilizada durante las prácticas:

`http://localhost/FutbolWebApp/Index.html`

**Nota:** El repositorio contiene el código fuente; GitHub no ejecuta directamente la aplicación DataFlex.

## 8. Conclusiones del Sprint 2

En este segundo Sprint se ha conseguido mejorar la estructura de navegación de FutbolWebApp y hacer más clara la consulta de los datos relacionados.

También se ha trabajado la presentación visual de la aplicación, creando un Dashboard más atractivo y personalizado, con una estética futbolística y una distribución adaptable a diferentes pantallas.

El proyecto permite seguir ampliando funcionalidades y continuar trabajando sobre una base más organizada.

---

**Sara Montesinos Villalba**  
Prácticas DAW – Sprint 5

25 de noviembre de 2026
