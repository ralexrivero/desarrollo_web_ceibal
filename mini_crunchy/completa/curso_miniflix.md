# Guía del Docente: Creación de MiniFlix Paso a Paso (Clase en Vivo)

Esta guía didáctica está diseñada para orientar el desarrollo de la página **MiniFlix** en una clase en vivo o taller práctico de desarrollo web. Utiliza un enfoque incremental y de "esqueleto a interfaz final", donde primero se comprende y analiza la estructura HTML y luego se construye la capa visual con CSS, explicando detalladamente cada propiedad y su porqué.

---

## 🎯 Objetivos de Aprendizaje
Al finalizar este curso práctico, los estudiantes sabrán:
1. Leer, estructurar e interpretar **HTML5 semántico** (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`).
2. Implementar un diseño responsivo utilizando **Flexbox** (`display: flex`, `flex-wrap`, `justify-content`).
3. Dominar el posicionamiento moderno con **Sticky Headers** (`position: sticky`).
4. Aplicar interactividad y dinamismo mediante **Transiciones y Transformaciones** en CSS (`transition`, `transform: translateY`, `transform: scale`).
5. Utilizar selectores avanzados, pseudo-clases (`:hover`, `:focus`, `:required`) y pseudo-elementos (`::before`).
6. Manejar la relación de aspecto de videos y elementos multimedia de forma responsiva (`aspect-ratio`).

---

## 📅 Estructura Sugerida para la Clase en Vivo

El curso se divide en dos bloques principales que pueden distribuirse en una o dos sesiones:

*   **Bloque 1 (HTML):** Análisis del Esqueleto Semántico y Enlaces de Navegación Interna (Duración estimada: 30-40 min).
*   **Bloque 2 (CSS):** Maquetación, Estética Premium y Efectos Dinámicos (Duración estimada: 80-90 min).

---

# Bloque 1: El Esqueleto de MiniFlix (HTML5 Semántico)

Antes de pintar la pantalla de negro y rojo, necesitamos construir las bases. Les presentamos a los alumnos el archivo **HTML base sin estilos**. 

*Nota para el docente:* Para iniciar, los estudiantes deben tener una plantilla HTML limpia que contenga únicamente el contenido dentro del `<body>`. La etiqueta `<style>` del `<head>` comenzará completamente vacía.

Analicemos la estructura del documento paso a paso:

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>MiniFlix</title>
  <style>
    /* Aquí desarrollaremos el CSS en el Bloque 2 */
  </style>
</head>
```
*Explicar a los alumnos:*
*   `meta name="viewport"`: Esencial para que la página sea responsiva en dispositivos móviles. Evita que el navegador del celular renderice la página en una resolución gigante y la achique artificialmente.

---

### Paso 1: El Encabezado Semántico (`<header>`)
El encabezado contiene la identidad del sitio y los enlaces principales.

```html
<header id="encabezado">
  <h1 class="logo">MiniFlix</h1>

  <nav class="menu">
    <a href="#destacadas">Destacadas</a>
    <a href="#formulario">Suscribite</a>
  </nav>
</header>
```

**Conceptos clave a explicar:**
*   `<header>` vs. `<h1>`: El `<header>` es el contenedor del encabezado (puede llevar logo, menú, buscador), mientras que `<h1>` es el título principal de mayor jerarquía.
*   `<nav>`: Etiqueta semántica para indicarle a los motores de búsqueda y lectores de pantalla que este bloque contiene la navegación principal.
*   `href="#destacadas"`: Enlaces de ancla (anclaje). Cuando el usuario hace clic, el navegador hace scroll automático hacia el elemento que posea el `id` correspondiente (ej. `<section id="destacadas">`).

---

### Paso 2: El Contenedor Principal y las Películas (`<main>` y `<section id="destacadas">`)
El cuerpo del contenido se agrupa dentro de `<main>`. La primera sección destaca las películas del catálogo.

```html
<main>
  <section id="destacadas">
    <h2>Películas destacadas</h2>
    <p>Según tus 🍪🍪🍪, Seleccionamos estas para vos:</p>

    <div class="peliculas">
      <!-- Película 1 -->
      <div class="pelicula">
        <img src="https://cartelera.montevideo.com.uy/imagenes_espectaculos/moviedetail13/16477.jpg" alt="Póster de El código secreto">
        <h3 class="titulo-pelicula">El código secreto</h3>
        <p class="sinopsis">Un enigma que cambiará el destino del mundo.</p>
      </div>
      
      <!-- Película 2 -->
      <div class="pelicula">
        <img src="https://cartelera.montevideo.com.uy/imagenes_espectaculos/moviedetail13/16478.jpg" alt="Póster de El séptimo hijo">
        <h3 class="titulo-pelicula">El séptimo hijo</h3>
        <p class="sinopsis">De cara al mal reclama tu destino.</p>
      </div>
      
      <!-- Película 3 -->
      <div class="pelicula">
        <img src="https://cartelera.montevideo.com.uy/imagenes_espectaculos/moviedetail13/16475.jpg" alt="Póster de Foxcatcher">
        <h3 class="titulo-pelicula">Foxcatcher</h3>
        <p class="sinopsis">Un señor con el ceño fruncido.</p>
      </div>
    </div>
    
    <hr>
    
    <h3>¿Por qué ver estas películas?</h3>
    <ul class="beneficios">
      <li>Top 10 en varios países</li>
      <li>Alta calidad de producción</li>
      <li>Subtítulos y doblaje</li>
    </ul>
  </section>
```

**Conceptos clave a explicar:**
*   `<main>`: Solo debe existir **uno** por página. Representa el contenido central exclusivo de este documento.
*   `<section>`: Divide el contenido en bloques temáticos independientes. Cada uno suele llevar un encabezado (`<h2>`, `<h3>`).
*   `alt` en las imágenes: No es opcional. Mejora la accesibilidad (lectores de pantalla para personas ciegas) y ayuda al posicionamiento SEO si la imagen no carga.
*   `<ul>` y `<li>`: Lista desordenada para enumerar las ventajas o beneficios de las películas.

---

### Paso 3: Sección Multimedia (El Tráiler Destacado)
Integramos contenido externo mediante un iframe de YouTube.

```html
  <section>
    <hr>
    <h2>Tráiler destacado</h2>
    <iframe src="https://www.youtube.com/embed/i-AIblqxslA" title="Ceibal Institucional" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </section>
```

**Conceptos clave a explicar:**
*   `<iframe>`: Permite incrustar un documento HTML completo (en este caso, el reproductor de YouTube) dentro de nuestra propia página. 
*   `allowfullscreen`: Habilita al reproductor de video a expandirse a pantalla completa cuando el usuario presiona el botón correspondiente.

---

### Paso 4: Sección de Captura (El Formulario de Suscripción)
El formulario permite interactuar con el usuario final.

```html
  <section id="formulario">
    <hr>
    <h2>Suscribite a MiniFlix</h2>
    <form>
      <label for="nombre">Nombre</label>
      <input type="text" id="nombre" name="nombre" required placeholder="Ingresa tu nombre">

      <label for="email">Correo electrónico</label>
      <input type="email" id="email" name="email" required placeholder="ejemplo@correo.com">

      <button type="submit" class="btn">Suscribirme</button>
    </form>
  </section>
</main>
```

**Conceptos clave a explicar:**
*   `<form>`: El contenedor de los campos de entrada de datos.
*   `<label for="nombre">` e `id="nombre"`: El atributo `for` del label debe coincidir exactamente con el `id` del input. Esto asocia el texto explicativo con el campo correspondiente, facilitando que al hacer clic en la etiqueta se enfoque el input.
*   `required`: Validación nativa de HTML5. Impide enviar el formulario si el campo está vacío.
*   `type="email"`: Valida automáticamente que la estructura del texto ingresado coincida con la de un correo válido (contenga `@` y un dominio).

---

### Paso 5: El Pie de Página (`<footer>`)
Cierra el sitio con los derechos de autor e información institucional.

```html
  <footer>
    <p>&copy; 2025 MiniFlix. Todos los derechos reservados Ciencias de la Computación - Ceibal.</p>
  </footer>
</body>
</html>
```

---

# Bloque 2: Estilando MiniFlix con CSS (Estética de Cine)

Una vez que los alumnos entienden qué contiene el HTML, pasamos a estilizarlo paso a paso. Agregamos el CSS dentro de la etiqueta `<style>`.

---

## 🎨 Fase de Estilos Paso a Paso

### Paso 1: Configuración Global y Dark Theme (El Fondo del Cine)
**Objetivo:** Establecer la paleta oscura de MiniFlix, el tipo de letra por defecto y limpiar los márgenes del navegador.

```css
/* =========================================
   1. ESTILOS GENERALES Y CUERPO
   ========================================= */
body {
  background-color: #141414; /* Color de fondo oficial de MiniFlix (Gris muy oscuro) */
  color: #ffffff;            /* Texto blanco para contrastar */
  font-family: Arial, Helvetica, sans-serif; /* Tipografía limpia y moderna */
  margin: 0;
  padding: 0;                /* Quitamos padding para que los elementos vayan de borde a borde */
  line-height: 1.6;          /* Espaciado de línea cómodo para lectura */
}

hr {
  border: 1px solid #333333; /* Líneas divisorias muy sutiles */
  margin: 30px 0;
}
```

💬 **Para explicar en vivo:**
*   *¿Por qué `#141414` en vez de negro puro (`#000000`)?* El negro puro fatiga la vista en pantallas modernas. El gris oscuro suaviza el contraste y da una sensación más elegante.
*   *¿Por qué `margin: 0` en el body?* Los navegadores aplican un margen por defecto de unos `8px`. Lo eliminamos para tener control total de la maquetación.

---

### Paso 2: El Encabezado Pegajoso (Sticky Navigation)
**Objetivo:** Diseñar un encabezado llamativo que se mantenga fijo al hacer scroll y estructurar el menú de navegación.

```css
/* =========================================
   2. ENCABEZADO Y NAVEGACIÓN
   ========================================= */
#encabezado {
  position: sticky;          /* El elemento hace scroll normal pero se queda fijo al llegar al tope */
  top: 0;                    /* Se ancla exactamente a 0px de la parte superior */
  width: 100%;
  z-index: 1000;             /* Se superpone ante cualquier otra capa en la pantalla */
  background-color: #141414;
  color: #ffffff;
  padding: 15px 0;
  text-align: center;
  border-bottom: 1px solid #333333;
}

.logo {
  color: #e50914;            /* Rojo insignia de MiniFlix */
  font-size: 3em;            /* Aumentamos el tamaño (3 veces la fuente base) */
  margin: 0;
  margin-bottom: 10px;
}

.menu {
  margin-top: 10px;
  text-align: center;
}

.menu a {
  display: inline-block;     /* Les permite recibir propiedades de padding y margin */
  text-decoration: none;     /* Quitamos el subrayado por defecto del enlace */
  color: #ffffff;
  padding: 8px 16px;
  margin: 0 10px;
  border-radius: 5px;
  transition: all 0.3s ease; /* Transición suave de cambios en hover */
}

.menu a:hover {
  background-color: rgba(255, 255, 255, 0.1); /* Fondo blanco con 10% de opacidad */
  color: #e50914;            /* Cambia el texto a rojo */
}
```

💬 **Para explicar en vivo:**
*   `position: sticky`: Gran alternativa a `fixed`. Permite que el encabezado empiece en su posición natural y "se pegue" arriba solo cuando el usuario baja en la página.
*   `z-index: 1000`: Imaginen la pantalla como capas de papel. Con un número alto, garantizamos que el encabezado esté arriba de todo.
*   `transition`: Si no la usamos, los cambios de color al pasar el cursor serian instantáneos y bruscos. `0.3s ease` hace que la animación tome 300ms de forma suave.

---

### Paso 3: Definición del Área de Contenido Principal y Secciones
**Objetivo:** Centrar y limitar el ancho del contenido para optimizar la lectura en pantallas grandes.

```css
/* =========================================
   3. CONTENIDO PRINCIPAL Y SECCIONES
   ========================================= */
main {
  max-width: 1000px;         /* Limita el ancho de la página a 1000px en monitores grandes */
  margin: 0 auto;            /* Truco clásico para centrar un contenedor en pantalla */
  padding: 0 20px;           /* Espaciado lateral para que el texto no toque el borde del móvil */
  margin-top: 20px;
}

section {
  margin-bottom: 40px;
  padding: 20px;
  border-radius: 8px;
}

section h2 {
  color: #ffffff;
  font-size: 2em;
  margin-top: 0;
  margin-bottom: 20px;
  border-bottom: 2px solid #e50914; /* Barra decorativa roja inferior */
  display: inline-block;     /* Ajusta la barra roja al ancho del texto exacto */
  padding-bottom: 5px;
}

section p {
  color: #cccccc;            /* Gris claro para el texto secundario */
  font-size: 1.1em;
  margin-bottom: 15px;
}
```

💬 **Para explicar en vivo:**
*   `margin: 0 auto`: Explicar que al definir un `max-width`, el margen automático calcula el espacio sobrante a la izquierda y derecha y lo reparte equitativamente, logrando el centrado horizontal.
*   `display: inline-block` en `h2`: Si no lo ponemos, el borde inferior cruzará toda la pantalla de lado a lado porque los encabezados son elementos de bloque.

---

### Paso 4: La Grilla de Películas (El Poder de Flexbox)
**Objetivo:** Alinear horizontalmente las tarjetas de películas y hacer que se adapten automáticamente si la pantalla se achica.

```css
/* =========================================
   4. TARJETAS DE PELÍCULAS
   ========================================= */
.peliculas {
  display: flex;             /* Activamos la caja flexible (Flexbox) */
  flex-wrap: wrap;           /* Si no entran en una línea, bajan a la siguiente */
  justify-content: space-evenly; /* Distribuye las tarjetas con espacios iguales a su alrededor */
  align-items: stretch;      /* Fuerza a que todas las tarjetas tengan la misma altura */
  gap: 20px;                 /* Separación uniforme entre las tarjetas */
  margin-bottom: 30px;
}

.pelicula {
  width: 250px;              /* Ancho fijo para cada tarjeta */
  background-color: #1c1c1c; /* Gris ligeramente más claro que el body */
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.4); /* Sombra suave para dar profundidad */
  margin: 0;
  transition: transform 0.3s ease, box-shadow 0.3s ease; /* Transición para efecto hover */
}

.pelicula:hover {
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.8); /* Sombra más fuerte y oscura */
  transform: translateY(-5px); /* Eleva la tarjeta 5 píxeles hacia arriba */
}

.pelicula img {
  width: 100%;               /* La imagen ocupará todo el ancho de su tarjeta (250px) */
  height: auto;              /* Mantiene la proporción original de la imagen */
  display: block;
  border-radius: 5px;
  margin-bottom: 15px;
}

.titulo-pelicula {
  font-size: 1.2em;
  margin: 10px 0;
  color: #e50914;
}

.sinopsis {
  font-size: 0.9em;
  margin-bottom: 10px;
  color: #aaaaaa;
}
```

💬 **Para explicar en vivo:**
*   `display: flex` + `flex-wrap: wrap`: Esta combinación es el corazón de la responsividad. En celulares pequeños, las películas se apilarán verticalmente de forma automática.
*   `transform: translateY(-5px)`: Esta propiedad genera un efecto tridimensional donde el elemento simula "flotar" cuando el cursor pasa por encima.

---

### Paso 5: Listas con Estilo (Uso de Pseudo-elementos)
**Objetivo:** Personalizar las viñetas por defecto de las listas (`<li>`) reemplazándolas por un emoji interactivo.

```css
.beneficios {
  list-style-type: none;     /* Quitamos los puntos negros tradicionales de las listas */
  padding: 0;
  margin: 0;
  color: #cccccc;
}

.beneficios li {
  margin-bottom: 8px;
}

/* El pseudo-elemento ::before inyecta contenido antes de cada elemento de la lista */
.beneficios li::before {
  content: "🍿 ";             /* Insertamos un emoji de pochoclos */
}
```

💬 **Para explicar en vivo:**
*   `::before`: Es un elemento virtual creado directamente en CSS. Evita tener que escribir a mano el emoji en cada línea del HTML, manteniendo el código limpio y fácil de mantener.

---

### Paso 6: El Tráiler Responsivo (Iframe de YouTube)
**Objetivo:** Lograr que el reproductor de video incrustado sea responsivo manteniendo la relación de aspecto cinematográfica 16:9 y reaccione estéticamente al cursor.

```css
/* =========================================
   5. TRÁILER DESTACADO (IFRAME YOUTUBE)
   ========================================= */
section iframe {
  display: block;
  margin: 0 auto;
  width: 80%;                /* Ocupa el 80% de su contenedor padre */
  max-width: 800px;          /* Nunca superará los 800px */
  aspect-ratio: 16 / 9;      /* Mantiene siempre proporción horizontal de pantalla panorámica */
  height: auto;              /* El alto se calcula automáticamente basado en la proporción */
  border-radius: 12px;
  border: 2px solid #333333;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.8);
  margin-top: 30px;
  margin-bottom: 40px;
  background-color: #000000;
  transition: transform 0.4s ease, box-shadow 0.4s ease, border-color 0.4s ease;
}

section iframe:hover {
  transform: scale(1.03);    /* Aumenta un 3% el tamaño del reproductor */
  border-color: #e50914;     /* El borde se vuelve rojo */
  box-shadow: 0 15px 40px rgba(229, 9, 20, 0.3); /* Resplandor rojo difuminado (Glow effect) */
}
```

💬 **Para explicar en vivo:**
*   `aspect-ratio: 16 / 9`: Propiedad moderna extremadamente útil. Ya no necesitamos trucos complejos con paddings para que el video mantenga sus dimensiones en móviles.
*   `box-shadow: ... rgba(229, 9, 20, 0.3)`: Al cambiar el color de la sombra a rojo con opacidad al 30%, generamos el efecto de retroiluminación led ("Glow") muy inmersivo.

---

### Paso 7: El Formulario Premium
**Objetivo:** Crear un formulario estilizado, centrado, con validación visual intuitiva y animaciones en los campos interactivos.

```css
/* =========================================
   6. FORMULARIO PREMIUM
   ========================================= */
#formulario {
  text-align: center;
  margin-top: 50px;
  margin-bottom: 60px;
}

#formulario h2 {
  margin-bottom: 25px;
}

#formulario form {
  display: flex;
  flex-direction: column;    /* Los inputs y labels se organizan en columna vertical */
  max-width: 450px;          /* Ajusta el ancho óptimo de lectura */
  margin: 0 auto;            /* Centra el formulario en la sección */
  background-color: #1c1c1c;
  padding: 40px;
  border-radius: 8px;
  border: 1px solid #333333;
  box-shadow: 0 15px 30px rgba(0, 0, 0, 0.8);
}

#formulario label {
  background-color: transparent;
  text-align: left;
  font-weight: 600;
  color: #b3b3b3;
  margin-bottom: 8px;
  font-size: 0.95em;
  letter-spacing: 0.5px;
}

#formulario input[type="text"],
#formulario input[type="email"] {
  background-color: #333333; /* Fondo de input gris oscuro */
  color: #ffffff;
  border: 1px solid #444444;
  border-radius: 4px;
  padding: 16px;
  font-size: 1em;
  margin-bottom: 25px;
  outline: none;             /* Elimina el borde azul default de Google Chrome */
  transition: all 0.3s ease;
}

/* Indicador visual de campo obligatorio nativo en CSS */
#formulario input:required {
  border-left: 3px solid #e50914; /* Pequeño borde rojo a la izquierda */
}

/* El input reacciona cuando el usuario hace clic para escribir */
#formulario input[type="text"]:focus,
#formulario input[type="email"]:focus {
  background-color: #454545; /* Fondo del input se aclara un poco */
  border-color: #e50914;     /* Borde rojo de foco */
  box-shadow: 0 0 10px rgba(229, 9, 20, 0.4); /* Resplandor rojo */
}

#formulario button[type="submit"] {
  background-color: #e50914;
  color: #ffffff;
  padding: 16px;
  border: none;
  border-radius: 4px;
  font-size: 1.2em;
  font-weight: bold;
  cursor: pointer;           /* El cursor se transforma en una mano indicando botón interactivo */
  margin-top: 10px;
  text-transform: uppercase; /* Pasa todo el texto a mayúsculas */
  letter-spacing: 1px;
  transition: background-color 0.3s ease, transform 0.2s ease;
}

#formulario button[type="submit"]:hover {
  background-color: #f40612; /* Rojo más encendido en hover */
  transform: scale(1.02);    /* Aumenta 2% de tamaño */
}
```

💬 **Para explicar en vivo:**
*   `flex-direction: column`: Flexbox por defecto alinea horizontalmente. Al cambiar la dirección a columna (`column`), apilamos las etiquetas (`label`), los campos (`input`) y el botón verticalmente.
*   `:required`: Permite aplicar estilos específicos a los campos que tienen el atributo `required` en el HTML. Aquí creamos una línea vertical roja para guiar visualmente al usuario.
*   `:focus`: Esta pseudo-clase se activa cuando el elemento es seleccionado. Estilizarla ayuda enormemente a la accesibilidad.

---

### Paso 8: El Pie de Página (Footer)
**Objetivo:** Diseñar la base de la web con tonos neutros e institucionales.

```css
/* =========================================
   7. PIE DE PÁGINA
   ========================================= */
footer {
  background-color: #000000; /* Negro puro para contrastar la base gris */
  color: #888888;            /* Texto gris atenuado */
  text-align: center;
  padding: 20px 0;
  margin-top: 40px;
  font-size: 0.8em;          /* Reducción de fuente */
  border-top: 1px solid #333333;
}
```

---

## 🙋‍♂️ Sección de Preguntas Frecuentes para la Clase (FAQs)

El docente puede utilizar esta sección para anticipar dudas comunes de los estudiantes:

1. **¿Por qué mi menú pegajoso (`position: sticky`) no se queda fijo arriba?**
   *   *Respuesta:* Para que `sticky` funcione, debes definir al menos una coordenada de pegado (como `top: 0`). Además, ninguno de sus contenedores padres directos (como `body` o algún div contenedor) debe tener la propiedad `overflow: hidden` o `overflow: scroll`.
2. **¿Cuál es la diferencia entre `transform: scale()` y cambiar el ancho (`width`) en una animación?**
   *   *Respuesta:* Cambiar el `width` fuerza al navegador a recalcular la posición de todos los elementos de alrededor (reflow), lo cual es costoso a nivel de rendimiento gráfico y puede verse pausado. Por otro lado, `transform` se procesa directamente en la GPU (placa de video), logrando animaciones ultra fluidas de 60fps sin alterar el flujo físico del resto de la página.
3. **¿Para qué sirve `outline: none` en los inputs?**
   *   *Respuesta:* Por defecto, los navegadores añaden un anillo de color (azul o negro) alrededor de los campos cuando haces clic en ellos. Al quitarlo con `outline: none`, debemos asegurarnos de proveer un indicador visual alternativo mediante `:focus` (como un cambio en `border-color` o un `box-shadow`) para que el sitio siga siendo accesible para navegación con teclado.
4. **¿Por qué usamos `transition: all`?**
   *   *Respuesta:* Hace que cualquier cambio en las propiedades CSS de ese elemento (color, fondo, bordes, transformación) ocurra de manera gradual en el tiempo definido (`0.3s`). Si solo quisiéramos animar la transformación, escribiríamos `transition: transform 0.3s ease`.
