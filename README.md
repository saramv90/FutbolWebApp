# ⚽ FutbolWebApp

Aplicación web de gestión de fútbol desarrollada con **DataFlex 2025 (versión 25.0) y MySQL**, como parte de las prácticas del ciclo de Desarrollo de Aplicaciones Web (DAW).

**Autora:** Sara Montesinos Villalba  
**Proyecto:** FutbolWebApp  
**Estado:** Sprint 2 completado  
**Fecha:** 11 de noviembre de 2026

---

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

## 4. Archivos principales modificados

| Archivo | Función |
|---|---|
| `AppSrc/Dashboard.wo` | Dashboard y navegación principal |
| `AppSrc/ZoomJugador.wo` | Personalización de la ficha de jugador |
| `AppSrc/ZoomEntrenador.wo` | Personalización de la ficha de entrenador |
| `AppSrc/ZoomEquipo.wo` | Personalización de la ficha de equipo |
| `AppSrc/ZoomLiga.wo` | Ficha de liga y equipos relacionados |
| `AppHtml/CssStyle/application.css` | Diseño visual Street Football |

## 5. Pruebas realizadas

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

## 8. Conclusiones

En este segundo Sprint se ha conseguido mejorar la estructura de navegación de FutbolWebApp y hacer más clara la consulta de los datos relacionados.

También se ha trabajado la presentación visual de la aplicación, creando un Dashboard más atractivo y personalizado, con una estética futbolística y una distribución adaptable a diferentes pantallas.

El proyecto permite seguir ampliando funcionalidades y continuar trabajando sobre una base más organizada.

---

**Sara Montesinos Villalba**  
Prácticas DAW – Sprint 2  
11 de noviembre de 2026
