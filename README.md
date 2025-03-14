# HTML

**HTML** (HyperText Markup Language) es un lenguaje de marcado de texto. Se utiliza para darle una estructura al sitio web.

## Contenido

- [Estructura básica html](#estructura-basica-html)
- [Atributos](#atributos)
- [Texto](#texto)
- [Anchor](#anchor)
- [Agrupación](#agrupacion)
  - Listas
  - Figure
  - Div
- [Tablas](#tablas)
- [Multimedia](#multimedia)
  - Imágenes
  - Picture
  - Videos
  - Audios
- [HTML semántico](#html-semantico)
- [Elementos reemplazables](#elementos-reemplazables)
- [Formularios](#formularios)
- [Details y Summary](#details-y-summary)
- [Dialog](#dialog)

---

## Estructura basica html

- `<head>`: Contiene información técnica del navegador como: metadatos, archivos que se cargan e información de la página. Este contenido no es visible para los usuarios. *Más información sobre los metadatos en el archivo HTML.*

- `<body>`: Es el contenido que aparece en el navegador. Dentro de esta etiqueta tenemos las siguientes:

  - `<header>`: Cabecera de la página. Usualmente encuentras el logo y el menú de navegación del sitio.

  - `<main>`: Etiqueta especial de html, ***solo puede haber una en todo el documento***. Se usa para englobar el contenido principal de la página.

  - `<footer>`: Es el contenido que se encuentra al final de la página.

![Estructura Basica HTML](https://lenguajehtml.com/html/documento/estructura-documento-html/estructura-documento-html.png)

> **Nota:** Tanto la etiqueta `<header>` y `<footer>` se pueden usar dentro de etiquetas contenedoras (section, article...) para dar mejor semántica a la lectura de la informacíon.


## Estructura de una etiqueta HTML

![Estructura de etiqueta html](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSCYfPub1F_0XMffla0fHCQR8PYJOL-NOE9cw&s)

---

## Atributos

Los atributos generalmente van asociados a un valor determinado. Este par *atributo-valor* se escribe después del nombre de la etiqueta, separándola por espacio y antes del carácter de cierre `>` de la etiqueta de apertura.

```html
<p class="saludo">hi</p> <!-- atributo -> class="valor" -->
```
### Tipos de atributos

- **Atributos globales:** Se pueden usar en todas las etiquetas html como: `class, id`.

```html
<strong id="dato" class="clas">Texto</strong>
```

- **Atributos específicos:** Son propios de ciertas etiquetas como: `src, alt`.

```html
<img src="logo.png" alt="MDN" srcset="logo.png 2x" />
```

- **Atributos booleanos:** Solo basta con escribirlos en la etiqueta, si lo ponemos funcionan como `true`, por ejemplo el atributo `hidden`.

```html
<img src="logo.png" alt="MDN" hidden /> <!-- la imágen esta oculta -->
```

### Atributos comunes

|Atributo|Valor|Descripción|
|--------|-----|-----------|
|id|nombre|Establece un identificador único a la etiqueta HTML. Sólo el mismo nombre una vez por documento.|
|class|nombre|Establece una clase (género) a una etiqueta HTML. Puede repetirse por documento.|
|style|estilos CSS|Aplica propiedades CSS directamente al elemento HTML en cuestión.|

---

## Texto

Las etiquetas de texto dan significado semántico a los textos que contienen.


### Etiquetas de fragmentos de texto
Estas etiquetas dan significado o contexto a un fragmento de texto. Funciona como un elemento en línea y suelen ir dentro de una etiqueta contenedora como la etiqueta `<p>`.

```html
<p>El texto esta en <strong>negrita</strong></p>
```

- `<strong>`: Resalta el texto en forma de **negrita**.

- `<em>`: Muestra el texto en *cursiva*.

- `<u>`: Muestra el texto **subrayado**.

- `<small>`: Hace el texto más pequeño. Se usa para dar contenido adicional o anotaciones menores.

- `<mark>`: Funciona como un resaltador, muestra el texto con un **fondo amarillo**.

- `<s>`: Hace que el texto aparezca tachado.

- `<span>`: Fragmentos de texto en línea, no cambia el flujo del mismo.

- `<sup>`: Superíndice.

- `<sub>`: Subíndice.

- `<code>`: Indicamos al navegador que el texto que incluyamos en su interior, debe ser interpretado visualmente como un fragmento de código.

### Etiquetas que agrupan otras etiquetas de texto

Estas estiquetas permiten agrupar otras etiquetas de texto.

- `<h1>`: Permite resaltar el texto en forma de **títulos**, su tamaño de mayor a menor va desde la etiqueta `<h1>` hasta la `<h6>`.

- `<p>`: Define una parte que debe mostrarse como un **párrafo**.

---

## Anchor

Permite enlazar recursos para que el usuario pueda navegar desde un punto a otro, es la base de las páginas webs y de Internet en sí, por lo que se podría decir que la etiqueta `<a>` es el pilar indiscutible de HTML.

### Rutas relativas o absolutas

Un detalle muy importante que no hay que infravalorar, es cómo indicar las rutas en atributos como `href` en un enlace, en `src` de imágenes o videos, etc. Aunque a priori parece muy sencillo, hay que tener muchas cosas en cuenta para realizar enlaces de forma correcta.

| Tipo de ruta | Ejemplo | ¿Dónde busca el archivo? |
|--------------|---------|------------------------- |
|Sin ruta      |imagen.jpg |El recurso se encuentra en la carpeta actual.|
|Ruta relativa ascendente |img/imagen.jpg |El recurso se encuentra en la carpeta img/ de la ruta actual.|
|Ruta relativa descendente |../imagen.jpg |El recurso se encuentra en la carpeta anterior a la actual.|
|Ruta relativa global |/img/imagen.jpg |El primer / simboliza el principio de la URL (root, raíz).|
|Ruta absoluta |https://idk.com |Exactamente la URL indicada.|

### Anchor para navegación interna

Los anchor o anclas `<a>` en una URL no son más que un fragmento de texto precedido por el carácter `#` que indica al navegador que debe buscar una etiqueta HTML con un atributo `id` con ese texto. 

```html
<a href='#main'>Main</a> <!-- enlace -->
<h2 id='main'>Principal</h2> <!-- destino del enlace-->
```

- `href`: Es el atributo con el que se indica la dirección URL a la página, documento o recursos que se quiere enlazar.

### Anchor para navegación externa

Para esto usamos las rutas absolutas acompañadas de ciertos atributos para aumentar la seguridad y experiencia de navegación.

```html
<a 
  href="https://www.twitch.tv/sylvee"
  target="_blank"
  rel="noreferrer"
>Sylvee</a>
```
- `target="_blank"`: Abre el enlace en otra pestaña.
- `rel="noreferrer"`: Impide dar información adicional del usuario.

Otros atributos que podemos usar en la etiqueta `<a>` son:

- `hreflang="en"`: Indica el idioma mediante un código ISO 639-1.
- `download`: Descarga el enlace como fichero del sistema.

### Anchor con protocolos especiales

```html
<a href="mailto:core@gmail.com">Envíame un correo</a>
<a href="tel:+324562342">LLámame</a>
<a href="whatsapp://send?text=hola">Envíame un wp</a>
```

---

## Agrupacion

Mejor conocidas como etiquetas de contenedoras, son las que agrupan el contenido que hay en su interior. Entre ellas tenemos: `<ul>` `<ol>` `<div>` `<figure>`.

### Listas:

### Listas ordenadas

Usamos la etiqueta `<ol>` para crear una lista ordenada númerica o alfabéctica y dentro de ella usamos la etiqueta `<li>` para cada elemento de la lista.

```html
<ol>
  <li>item 1</li> <!-- 1. item 1 -->
  <li>item 2</li> <!-- 2. item 2 -->
  <li>item 3</li> <!-- 3. item 3 -->
</ol>
```

Podemos usar ciertos atributos en la etiqueta `<ol>` para alterar su orden o la forma de especificar su ordenación:

- `type="1 | a | A | i | I"`: Establece una lista de orden de: números enteros, letras o números romanos (minúsculas o mayúsculas)..
- `start="7"`: Indica el valor desde donde queremos que empice la lista.
- `reversed`: Invierte el orden del lista.

En la etiquta `<li>` podemos agregar el siguiente atributo:

- `value="num"`: Establece un valor numérico especial al elemento de la lista.

```html
<ol type="1" reversed start="7">
  <li>item 7</li> <!-- 7. item 7 -->
  <li>item 6</li> <!-- 6. item 6 -->
  <li>item 5</li> <!-- 5. item 5 -->
  <li value="10">item 10</li> <!-- 10. item 10 -->
</ol>
```

### Lista desordenadas

Usamos la etiqueta `<ul>` para crear una lista desordenada establecida por viñetas.

```html
<ul>
  <li>item</li>               <!-- ● item -->
  <li type="circle">item</li> <!-- ○ item -->
  <li type="square">item</li> <!-- ■ item -->
</ul>
```

```html
<ul type="square">
  <li>item</li> <!-- ■ item -->
  <li>item</li> <!-- ■ item -->
  <li>item</li> <!-- ■ item -->
</ul>
```

> **Nota:** Podemos usar el atributo `type="circle|square"` tanto en la etiqueta `<ul>` para todos los elementos de la lista, como en la etiqueta `<li>` para los elementos individuales de la lista.

### Figure y Figcaption

`<figure>` es una etiqueta de agrupación que debe contener el elemento de contenido, en este ejemplo una imagen `<img>`, y la etiqueta `<figcaption> `que contendrá la leyenda o mensaje que acompaña al elemento anterior.

```html
<figure>
  <img src="https://lenguajehtml.com/assets/logo.png" alt="Logotipo de HTML5">
  <figcaption>Logotipo oficial del lenguaje de marcas HTML5.</figcaption>
</figure>
```

### Div

La etiqueta `<div>` la usamos cuando queremos agrupar elementos cuando no hay un significado semántico. Funciona como una etiqueta de bloque es decir, da salto de linea.

Se la utilizan con un atributo `id` o `class` para referenciarla más facilmente.

```html
<div class="movie-data">
  <h2>Interstellar</h2>
  <div class="description">
    <p>
      <strong>Interstellar</strong> es una película dirigida
      por <strong>Christopher Nolan</strong>.
    </p>
  </div>
</div>
```

> **Nota:** La etiqueta `<span>` es la versión en línea de una etiqueta `<div>`. Mientras que esta última se utiliza para agrupar otras etiquetas variadas y organizarlas de forma semántica o con cierto sentido, la etiqueta `<span>` permite hacer lo mismo con fragmentos de texto en línea, sin cambiar el flujo del mismo.

---

## Tablas

Una tabla puede ser sencilla o compleja, dependiendo de nuestro objetivo y la cantidad de etiquetas o atributos a utilizar.

|Etiqueta |Descripción |
|---------|----------- |
|`<table>` |Etiqueta contenedora que tendrá en su interior toda la tabla. |
|`<tr>  ` |Table Row. Etiqueta contenedora de cada fila de la tabla. |
|`<td>` |Table Data. Cada una de las celdas de la tabla. |
|`<th>` |Table Header. Cada una de las celdas de cabecera de la tabla. |

La etiqueta `<table>` sería el elemento que contendría todos los elementos de la tabla, mientras que `<th>` y `<td>` se utilizarían para cada uno de los campos de la tabla. Cada vez que se quisiera añadir una nueva fila, habría que incluirlo todo dentro de una etiqueta `<tr>`.

```html
<table>
  <!-- Fila de la cabecera -->
  <tr>
    <th>Título columna 1</th> <!-- Celda cabecera de la columna 1 -->
    <th>Título columna 2</th> <!-- Celda cabecera de la columna 2 -->
    <th>Título columna 3</th> <!-- Celda cabecera de la columna 3 -->
  </tr>
  <!-- Primera fila -->
  <tr>
    <td>Celda 1x1</td> <!-- Primera celda de la primera fila -->
    <td>Celda 2x1</td> <!-- Segunda celda de la primera fila -->
    <td>Celda 3x1</td> <!-- Tercera celda de la primera fila -->
  </tr>
  <!-- Segunda fila -->
  <tr>
    <td>Celda 1x2</td> <!-- Primera celda de la segunda fila -->
    <td>Celda 2x2</td> <!-- Segunda celda de la segunda fila -->
    <td>Celda 3x2</td> <!-- Tercera celda de la segunda fila -->
  </tr>
</table>
```

> **Nota:** Debemos tener claro que las tablas son un mecanismo para mostrar datos tabulares, es decir, para mostrar cierta información de forma más cómoda, pero no es un mecanismo de maquetación para colocar elementos.

---

## Multimedia

Las etiquetas multimedias nos permiten cargar en nuestra páginas audios, videos, ímagenes y hasta fragmentos de otras páginas web.

### Imágenes

Para cargar imágenes usamos la etiqueta `<i>` la cual cuenta con ciertos atributos que la hacen interesante.

- `src="url"`: Indica el nombre o la URL de la imagen a mostrar. Atributo obligatorio.
- `alt=""`: Describe la imagen. Atributo obligatorio.
- `width="100px"`: Indica el ancho de la imagen en píxels.
- `height="100px"`: Indica el alto de la imagen en píxels.
- `loading="lazy"`: El navegador pospone la descarga de este recurso hasta que sea necesario.

```html
<img 
  src="html.webp"
  alt="Logo de HTML5"
  width="400" 
  height="400"
  loading="lazy"
/>
```

> **Nota:** El atributo `loading="lazy"` carga las imágenes mientras se scrollea la página, se recomienda usar este atributo solo en las imágenes que estan de la mitad para abajo de la página.

### Imágen responsive

Para hacer que una imágen ajuste su tamaño automáticamente con el tamaño de la página usamos el siguiente atributo.

- `style="width: 100%; aspect-ratio: valor/valor;"`

```html
<img 
  src="html.webp"
  alt="Logo de HTML"
  style="width: 100%; aspect-ratio: 1056/283;"
/>
```

> **Nota:** No usamos los atributos de `width` y `height`. Ver el `aspect-ratio` de cada imágen en las herramientas de desarrollo del navegador. 

### Imágen como enlace

Para hacer una imagen que funcione como enlace la tenemos que envolver con una etiqueta `<a>` y especificar la **URL**. Dependerá de nosotros los atributos que le pongamos al anchor.

```html
<a  href="https://url.com" 
    target="_blank" 
    rel="noreferrer">
  <img src="dog.jpg" alt="small white dog">
</a>
```

### Imágen descargable

Para hacer una imagen descargable la tenemos que envolver con una etiqueta `<a>` y agregarle el atributo `download`.

```html
<a href="#" download>
  <img src="./img/moon.webp" width="200">
</a>
```

> **Nota:** El atributo `download` fuerza la descarga de la imágen con darle click. Solo funciona con los archivos de nuestro dominio.

### Picture

La etiqueta `<picture>` es una etiqueta contenedora la cual nos dá la posibilidad de establecer diferentes imágenes alternativas con las etiquetas `<source>` las cuales se aplicarán dependiendo del tamaño que requiramos.

```html
<picture>
  <!-- <source> -> posibles imágenes candidatas  -->
  <!-- <source> -> posibles imágenes candidatas  -->
  <!-- <img> -> imagen  a utilizar por defecto -->
</picture>
```
La etiqueta interna `<source>` puede contener los siguientes atributos:

- `srcset`: 	Serie de imágenes (separadas por coma) que se utilizarán. Atributo obligatorio.
- `src`: Se utiliza cuando se indica audio o video. En imágenes es ignorado.
- `sizes`: Consulta de medios (media queries) para determinar si la imagen o imágenes se mostrarán.
- `media`: Condición que se debe cumplir para que muestre la imagen.
- `type`: 	Sugerencia para indicar al navegador el formato que se utiliza. Opcional.

Ejemplo de una imágenes responsive usando la `<picture>`.

```html
<picture>
  <source media="(width >= 900px)"
          srcset="logo-large.png">
  <source media="(width >= 600px) and (width < 900px)"
          srcset="logo-medium.png">
  <source media="(width < 600px)"
          srcset="logo-small.png">
  <img src="logo-medium.png" alt="HTML5 logo">
</picture>
```

De esta forma, estamos indicando que se muestren diferentes imágenes dependiendo de la resolución de pantalla (ancho) del dispositivo:

- Dispositivos grandes (igual o más de 900px): Muestra la imagen logo-large.png
- Dispositivos grandes (entre 600-899px): Muestra la imagen logo-medium.png
- Dispositivos pequeños (menos de 600px): Muestra la imagen logo-small.png
- Si no cumple las anteriores (o no soporta estas etiquetas): Muestra la imagen `<img>` logo-medium.png 

### Videos y Audios

Estas etiquetas funcionan relativamente igual ya que usamos los mismos atributos.

### Videos

La etiqueta `<video>` tiene varios atributos que podemos utilizar como `src` para su url o dirección del fichero, `width` y `height` para su tamaño.

```html
<video src="video.mp4" width="360" height="640"></video>
```

- `poster="poster.png"`: Este atributo permite cagar una imágen a modo de miniatura YouTube que aparece antes de darle play al video.

```html
<video 
  src="video.mp4" 
  width="360" 
  height="640" 
  poster="poster.png">
</video>
```


Aparte de los anteriores atributos la etiqueta `<video>` cuenta con los siguientes atributos `booleanos` especiales.

- `autoplay`: Comienza a reproducir el video automáticamente.
- `loop`: Vuelve a iniciar el video cuando finaliza su reproducción.
- `muted`: Establece que el video se reproduzca con sonido muteado.
- `controls`: Muestra los controles de reproducción (por defecto no se muestran).

```html
<video src="video.mp4" autoplay muted loop controls></video>
```

### Audio

La etiqueta de `<audio>` utiliza los mismos atributos que la de video.

```html
<audio src="audio.mp3" controls loop autoplay muted></audio>
```

---

## HTML Semantico

Es el uso correcto de las diferentes etiquetas html para la descripción del contenido la página.

- `<nav>`: Representa una sección de una página cuyo propósito es proporcionar enlaces de navegación, ya sea dentro del documento actual o a otros documentos. 
- `<section>`: Representa una sección genérica de un documento.
- `<article>`: Representa información propia contenida que puede extraerse a otra parte de la página.
- `<aside>`: Representa contenido que está indirectamente relacionado con el contenido principal del documento.

![Semántica](https://static.semrush.com/blog/uploads/media/0a/0f/0a0fd07d0a6ee7a7f893b0e21379c0ae/ES-Semantic-Search-Non-Semantic.png)

---

## Elementos reemplazables

Algunos objetos que normalmente funcionan como objetos de reemplazo. Se los pueden identificar porque no tienen etiquetas de cierre como: `<img>` o elementos de formulario como `<textarea>`, `<input>`.

---

## Formularios

Los formularios son unos de los recursos más utilizados en todo el internet ya que le permite al usuario enviar datos al servidor.

### Form

La etiqueta `<form>` define un formulario HTML para la entrada del usuario. Es la etiqueta que engloba todo el contenido del formulario. 

Dentro de esta etiqueta podemos definir ciertos atributos especiales para conexión al sevidor:

- `method="post/get"`: Método HTTP de envío. GET a través de URL, POST para envío extenso de información..
- `action="/"`: Dirección URL del backend al cuál se enviará la información obtenida en el formulario.
- `name=""`: Nombre del formulario. Útil para identificar el formulario y procesar posteriormente.

```html
<form method="post" action="/">

  <label>Nombre:
    <input 
      type="text" name="name"> 
  </label>

<button>Enviar</button>
</form>
```

### Fieldset y Legend

Estas dos etiquetas van juntas y su propósito es darle un agrupamiento visual a los inputs.

- `<fieldset>`: Permite agrupar inputs que comparte el mismo propósito en una especie de caja.
- `<legend>`: Le pone nombre al fieldset.

```html
<form method="post" action="/">

  <fieldset>
    <legend>Información personal</legend>
      <!-- Inputs para recuperar información -->
      <!-- Inputs para recuperar información -->
  </fieldset>

  <button>Enviar</button>
</form>
```

### Input

Los `<input>` son elementos básicos de un formulario ya que son los que nos permiten recuperar la información del usuario de diferentes formas.

Atributos de la etiqueta `<input>`:

| Atributo     | Descripción |
|--------   |--------|
| `name`   |Es el nombre del campo el cual se enviará desde el formulario al servidor.  |
| `type`   |Indica la naturaleza de datos que se espera del usuario (texto, número, fechas, etc...).  |
| `value`   |Indica el valor inicial que tendrá este campo de datos. Si se omite, está vacío. |
| `form`   |Asocia este campo con un formulario específico. Útil si necesitamos tenerlo fuera del `<form>`. |
| `placeholder`   |	Indica una sugerencia al usuario antes de escribir el valor en el campo. |
| `size`   |	Tamaño visual (aprox: número de carácteres) del campo de datos. |
| `autocomplete`   |	Activa `on` o desactiva `off` el autocompletado para este campo. Activado por defecto. |
| `autofocus`   |	Establece el foco (coloca el cursor) en este campo al cargar la página. |
| `required`   |	Indica que la información de dicho input es obligatoria. |

Tipos de `<input>` por su `type`:

![Inputs](https://preview.redd.it/how-many-html-input-types-do-you-use-v0-4cubete8zz7d1.jpeg?auto=webp&s=8bc9ee73cb783267fa06468526fe6ad2ee898632)

### Input - `type="range"`

Es una barra de desplazamiento que representa un número entre un rango numérico específico.

Sin embargo, este método tiene dos inconvenientes:

- Por defecto, no se muestra el valor elegido.
- Por defecto, los valores mínimo y máximo son 0 y 100.

```html
<!-- con el atributo value podemos indicar un valor inicial -->
<input type="range" value="5.0"> 
<input type="range" value="10"> 
```

Uso del `type="range"` con salida dinámica, es decir muestra los valores mientras se mueve el rango.

```html
<input 
  type="range" 
  value="5.0" 
  onInput="this.nextElementSibling.value = this.value">
<output>5.0</output>
```
>**Nota:** Tenemos que colocar los atributos en el orden visto anteriormente. Con la etiqueta `<output>` podemos visualizar el valor del range mientras los desplazamos.

En ambas etiquetas input numéricas se pueden indicar los atributos **min** y **max** para restringir el valor mínimo y máximo que puedes escribir en el campo de entrada de datos:

```html
<form method="post" action="/send/">
  Un valor numérico:
  <input type="number" value="25" min="10" max="50">

  Un valor numérico en rango:
  <input type="range" value="25" min="10" max="50" onInput="this.nextElementSibling.value = this.value">
  <output>25</output>
</form>
```

### Input - `type="file"`

Este atributo nos permite enviar archivos a travéz de un formulario. Como el modo de adjuntar archivos de Gmail.

Para poder usar este tipo de input tenemos que especificar unos **atributos** importantes en la etiqueta `<form>`.

```html
<form method="post" action="/send/" enctype="multipart/form-data">
  <input type="file">
</form>
```

Es posible indicar el atributo `accept` a modo de sugerencia para el navegador, de modo que podamos indicar los formatos de archivos permitidos subir al formulario.

```html
<form method="post" action="/send/" enctype="multipart/form-data">
  Selecciona una foto para enviar:
  <input type="file" accept="image/jpeg"> <!-- el formulario solo permite subir imágnes -->
</form>
```

>**Nota:** Existen varios tipos de archivos que podemos especificar en el formulario. [Ver lista de archivos](https://lenguajehtml.com/html/formularios/etiqueta-html-input-file/).

### Label
La etiqueta `<label>` define un control para el formulario HTML. Esta etiqueta esta asociada directamente con los `<input>`. 

```html
<label>Nombre:</label>
```

### Formas de enlazar un label con el input

1. Envolver un input con la etiqueta label:

```html
<label>Nombre:
  <input 
    type="text" 
    name="name"
    placeholder="Ana De Armas"
    required
  >
</label>
```

2. Con la etiqueta `<label>` asociada correctamente con el `<input>` por su atributo `for` (que contiene el atributo `id` del elemento `<input>`).

```html
<label for="correo">Email:</label>
<input 
  type="email" 
  name="email"
  id="correo"
  placeholder="ana@gmail.com"
  required 
>
```

> **Nota:** Las dos opciones son correctas, solo tenemos que tener encuenta que si tenemos el `<input>` al lado del `<label>` podemos usar la primera opción.

### Select

`<select>` Es una etiqueta contenedora que permite crear una lista desplegable de elementos, estos elementos deben ir en la etiqueta `<option>`.

```html
<form method="post" action="/send/">
  <label for="op">Selecciona la opción deseada:</label>
  
  <select id="op">
    <option value="1">Opción 1</option>
    <option value="2" selected>Opción 2</option> <!-- el atributo select nos presenta una opción inicial por defecto -->
    <option value="3">Opción 3</option>
  </select>
</form>
```

Podemos crear grupos de opciones con la etiqueta.

```html
<form method="post" action="/send/">
  Selecciona la opción deseada:
  <select>
    <optgroup label="Categoría 1"> <!-- nombre del grupo o categoría -->
      <option value="1">Opción 1</option>
      <option value="2">Opción 2</option>
    </optgroup>
    <optgroup label="Categoría 2">
      <option value="3">Opción 3</option>
      <option value="4">Opción 4</option>
    </optgroup>
  </select>
</form>
```

### Datalist

Es una etiqueta potenciada de select, permite personalizar una lista de datos.

La etiqueta `<datalist>` debe indicarse con un atributo `id` para identificarse. En su interior, incluiremos varias etiquetas `<option>` para añadir opciones, al igual que lo hacemos en una etiqueta `<select>`.

Utilicemos la etiqueta `<input type="text">` para permitir al usuario introducir texto pero aumentándola con las capacidades de `<datalist>`. Utilizaremos el atributo list del `<input>` para conectar con el id del `<datalist>`:

```html
<label>
  ¿Con qué lenguajes quieres que te ayude?
  <input list="languages" name="languages">
</label>
<datalist id="languages">
  <option value="JavaScript"></option>
  <option value="Java"></option>
  <option value="C#"></option>
</datalist> 
```

Podemos usar la etiqueta `<datalist>` de una forma más avanzada como en un rango de opciones.

```html
<form method="post" action="/send/">
  <input type="range" list="items" min="1" max="5" value="3">
  <output></output>
  <datalist id="items">
    <option value="1">Muy satisfecho.</option>
    <option value="2">Satisfecho.</option>
    <option value="3">Indiferente.</option>
    <option value="4">Decepcionado.</option>
    <option value="5">Muy decepcionado.</option>
  </datalist>
</form>
```

### Botones en el formulario

Los botones en los formularios se pueden definir de las siguientes formas:

1. Mediante la etiqueta `<input>` con el atributo `type="submit"`.

```html
<input type="submit" value="Enviar contacto"> <!-- el value representa el nombre del botón -->
```

2. Mediante la etiqueta `<button>`.

```html
<button>Enviar contacto</button>
```

> **Nota:** Los botones que están dentro de un formulario son siempre de `type="submit"` por lo que no es necesario escribir este atributo.

### Botón reset

El botón con el atributo `type="reset"` nos ofrece la posibilidad de resetear por completo el formulario a sus valores iniciales.

```html
<form method="post" action="/send/">
  <label>Usuario:
    <input name="username">
  </label>
  <input type="submit" value="Enviar formulario"> 
  <input type="reset" value="Borrar formulario">
</form>
```

### Botón desactivado

Esta opción es intersante cuando queremos que el usuario cumpla con ciertos requerimientos importante antes de continuar.

Usamos el atributo `disabled` para desactivar un botón.

```html
<button>Botón activado</button>
<button disabled>Botón desactivado</button> <!-- el botón se muestra transparente y no se puede clicar-->
```

---

## Details y Summary

Son etiquetas interáctivas para presentar la información. `<details>` es la etiqueta envoltorea y `<summary>` la que tiene el contenido.

Podemos destacar dos atributos importantes de `<details>`:

- `name="ask"`: Este atributo va en todos los details y permite cerrar el dialog automáticamente e identificarlos en un mismo grupo.
- `open`: Permite tener abierto por defecto la opción.

```html
<section>
  <details name="ask">
    <summary>¿Qué estudios tienes?</summary>
    <p>Estudié en la universidad pública de mi ciudad.</p>
  </details>

  <details name="ask">
    <summary>¿Cuáles son tu hobbies?</summary>
    <p>Me gusta el deporte y dibujar.</p>
  </details>

  <details open name="ask">
    <summary>¿Cuál es tu lenguaje favorito?</summary>
    <p>Me gusta mucho JavaScript porque fue el primero que aprendí.</p>
  </details>
</section>
```

---

## Dialog

Es una etiqueta interactiva la cual funciona como modal para mostrar información cuando le demos click a un botón.

```html
<dialog id="modal">
  <h1>¿Sabías que puedes abrir una modal así?</h1>
  <p>¡Y es totalmente nativo!</p>
  <button id="cerrar">Cerrar modal</button>
</dialog>

<button id="abrir">Ver más información</button>
```

Lo malo es que tenemos que acompañarla con un poco de JavaScript para sacarle su pontencial ya que aún está en desaarrollo.

```javascript
// botón de abrir
window.abrir.addEventListener('click', () => {
  window.modal.showModal()
})

// botón de cerrar
window.cerrar.addEventListener('click', () => {
  window.modal.close()
})
```

[Volver arriba](#contenido)

---

Hasta aquí la información sobre **HTML**. A medida que vaya aprendiendo nuevas cosas iré actualizando este repositorio.

> Referencia del contenido: [Manz.dev](https://lenguajehtml.com/), [Midu.dev](https://midu.dev/)