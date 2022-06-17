author: Original de Marc DiPasquale, adaptación al castellano por David Romero
summary: Aprende cómo crear un CodeLab usando Markdown
id: es-codelab-markdown
categories: codelab,markdown
environments: Web
status: Published
feedback link: https://github.com/DavidLMS/davidlms.github.io/issues/new?title=Error+en+gu%C3%ADa+Crear+un+Codelab

# Crear un CodeLab

## Introducción
Duration: 0:02:00

¿Quieres crear un contenido similar a este tutorial? A continuación aprenderás **cómo crear tu propio CodeLab** en muy poco tiempo.

A la hora de crear un CodeLab tenemos dos opciones:
1. Usar un Documento de Google
2. Usar un fichero Markdown

En este CodeLab vamos a explicar la segunda opción y crear el nuestro usando un **fichero Markdown**. Esto nos garantiza la flexibilidad de reutilizar el archivo en otras ocasiones y la posibilidad de almacenarlo en nuestro repositorio de Git con cualquier otro código que pudiese ser útil en un tutorial. No obstante, puedes ver cómo hacerlo a partir de un Documento de Google en este [artículo de Juan Antonio Gómez](https://medium.com/shokmaster/google-codelab-en-5-minutos-5043f4cd21f4).

Este es otro ejemplo de cómo puede quedar un CodeLab generado:

![Práctica de Wireguard con CodeLab](img/codelab-wireguard.png)

**Créditos y Recursos:** 
* Este CodeLab **es una adaptación del original de Marc DiPasquale** que puedes encontrar aquí: [Enlace al CodeLab](https://www.marcd.dev/codelab-4-codelab)
* El archivo Markdown del original de Marc DiPasquale está accesible aquí: [codelab.md](https://github.com/Mrc0113/codelab-4-codelab/blob/master/codelab.md)
* [Google CodeLabs Tools Github](https://github.com/googlecodelabs/tools) - El repositorio que contiene la herramienta claat que vamos a utilizar
* [Google Group for CodeLab Authors](https://groups.google.com/forum/#!forum/codelab-authors) - foro de consulta sobre CodeLabs y discusión sobre futuras funcionalidades
* Si quieres acceder al archivo Markdown de este CodeLab, puedes hacerlo aquí: [codelab.md](https://github.com/DavidLMS/davidlms.github.io/blob/master/Practicas/crear-codelab/codelab.md)

## Preparación del entorno
Duration: 0:05:00

Para crear un CodeLab, necesitas tener instalados *Go* y *claat* (la herramienta por línea de comandos de codelabs).

A continuación puedes ver las instrucciones de instalación para los sistemas operativos más populares.

###Windows

Vamos a la [página de releases de claat](https://github.com/googlecodelabs/tools/releases) y **descargamos la versión apropiada**. Si tienes Windows de 64 bits, descargamos "claat-windows-amd64.exe".

![Releases de claat](img/codelab.releases.png)

###Linux (Probado en Ubuntu)

Vamos a la [página de releases de claat](https://github.com/googlecodelabs/tools/releases) y **descargamos la versión apropiada**. Si tienes Linux de 64 bits, descargamos "claat-linux-amd64".

![Releases de claat](img/codelab.releases.png)

**Abrimos una terminal** y accedemos a la carpeta en la que tengamos descargado el ejecutable de claat.

Le damos **permisos de ejecución**:

``` bash
sudo chmod +x claat-linux-amd64
```
(sustitumos claat-linux-amd64 por nuestra versión)

###macOS

#### Instala Go 

Instala [Go](https://golang.org/dl/) si no has hecho aún.
Puedes usar **Homebrew** si lo tienes en macOS:

``` bash
$ brew install go
```

#### Establece las variables de entorno

Ejecuta lo siguiente en una **Terminal** para establecer las variables de entorno necesarias:

``` bash
$ export GOPATH=$HOME/Go
$ export GOROOT=/usr/local/opt/go/libexec
$ export PATH=$PATH:$GOPATH/bin
$ export PATH=$PATH:$GOROOT/bin
```

#### Instala claat

Para **instalar claat**, ejecuta lo siguiente en una Terminal:

``` bash
$ go install github.com/googlecodelabs/tools/claat@latest
```

Ahora deberías tener el comando *claat* disponible en la terminal. 

``` bash
$ claat
```

## Crea tu primer CodeLab
Duration: 0:05:00

Ahora que tenemos el entorno configurado, vamos a crear **un fichero markdown** en el que escribiremos un CodeLab.

### Creación del archivo
Crea un archivo llamado **codelab.md** y ábrelo con tu editor de texto favorito.

### Cabecera con información del CodeLab
**Copia y pega** la cabecera a continuación en el fichero markdown y modifica los valores acorde al CodeLab que quieres crear.
Debajo del ejemplo tienes la explicación de cada una de las variables.

```console
author: Nombre del autor
summary: Resumen del CodeLab
id: identificador-unico-del-codelab
categories: codelab,markdown
environments: Web
status: Published
feedback link: Un enlace en el que los usuarios puedan darte feedback (quizás creando un issue en un repositorio de git)
analytics account: ID de Google Analytics
```

Los metadatos consisten en **parejas de valores clave** de la forma "clave: valor". Los valores deben estar en una sola línea. Todos los metadatos deben escribirse antes del título del CodeLab. En principio se pueden utilizar todas las claves y valores que quieras, sin embargo, solo los siguientes los interpretará el renderizador:

* summary: Una descripción del CodeLab resumida. Por defecto en blanco.
* id: Un identificador compuesto por letras minúsculas y sin espacios que idealmente describen el contenido del CodeLab. Este campo debe ser único entre los CodeLabs.
* categories: Una lista separada por comas de los temas que trata el CodeLab.
* environments: Una lista de entornos en los que se podrá encontrar el CodeLab. Los marcados como "Web" estarán visibles en el índice de CodeLabs.
* status: El estado de la publicación del CodeLab. Los valores válidos son:
- Draft: Es un borrador.
- Published: Está terminado y visible.
- Deprecated: Ha quedado obsoleto.
- Hidden: Oculto, no se mostrará en el índice.
* feedback link: Un enlace en el que los usuarios puedan darte feedback de errores encontrados en tu CodeLab.
* analytics account: Un ID de Google Analytics para incluir todas las páginas del CodeLab. Por supuesto, es opcional y puedes eliminar esta línea.

### Añade el título
Añade ahora tu título usando el **carácter almohadilla** '#' (equivalente a la primera cabecera en markdown)

```
# Título del CodeLab
```

### Añade secciones y sus duraciones
Luego para cada sección usa la **segunda cabecera** de markdown o '##' y especifica, de forma opcional, el **tiempo estimado** necesario para completar esa sección. Este tiempo estimado se indica como "Duration" con el formato hh:mm:ss.

Ejemplo:
``` bash
## Sección 1
Duration: 0:10:00

## Sección 2
Duration: 0:05:00
```

### Añade contenido en la sección
Ahora que tenemos 2 secciones en nuestro CodeLab podemos **añadir contenido en cada sección**. Copia y pega el ejemplo a continuación debajo del Duration de la sección 1:

```
### Cajas de información
Texto plano dentro de cajas de información verdes y amarillas

Negative
: Esto aparecerá en una caja de información amarilla.

Positive
: Esto aparecerá en una caja de información verde.

¡Ya tienes tus cajas de información creadas!

### Lista con viñetas
Texto plano en una lista con viñetas:

* Hola
* CodeLab
* Mundo

¡Ya tienes tu lista con viñetas creada!

### Lista numerada
1. Lista
2. Utilizando
3. Números

¡Ya tienes tu lista numerada creada!

```

En la sección 2 vamos a añadir varios elementos más, una imagen entre ellos. Para **añadir imágenes locales**, crea una carpeta al lado de tu fichero .md llamada "img". Dentro de la misma, añade una imagen cualquiera que se llame prueba.png.

Copia ahora en la sección 2 (debajo de Duration): 
```
### Añade un enlace
¡Añadiendo un enlace!
[Ejemplo de enlace](https://www.davidlms.com)

### Añade una imagen
¡Añadiendo una imagen!

![Descripción de la imagen](img/prueba.png)

### Incrusta un iframe

![https://codepen.io/tzoght/embed/yRNZaP](https://en.wikipedia.org/wiki/File:Example.jpg "Try Me Publisher")
```

Puedes encontrar más ejemplos [aquí](https://github.com/googlecodelabs/tools/tree/master/claat/parser/md).

## Exportar y servir
Duration: 0:02:00

Ahora que tenemos un CodeLab inicial definido en nuestro archivo markdown, vamos a generar **la página web estática**.
Podemos exportar y servir el contenido de forma local usando el comando `claat` que instalamos anteriormente.

###Windows

Movemos nuestro archivo codelab.md que queremos generar a la carpeta en la que tengamos descargado el ejecutable de claat.

Abrimos el símbolo del sistema y accedemos desde el mismo a la carpeta en la que tengamos descargado el ejecutable de claat.

![Acceso al CMD en Windows](img/cmd-windows.png)

Escribimos el siguiente comando:

``` bash
claat-windows-amd64.exe export codelab.md
```
(sustitumos claat-windows-amd64.exe por nuestra versión)

![claat export en Windows](img/codelab-export-windows.png)

Y ya tendremos nuestros archivos generados.

![Archivos generados por claat en Windows](img/archivos-generados-windows.png)

A continuación, podemos servirlo de forma local ejecutando el comando:

``` bash
claat-windows-amd64.exe serve
```
(sustitumos claat-windows-amd64.exe por nuestra versión)

* Tu navegador debería haberse abierto (si no lo hace, prueba a escribir localhost:9090 en la dirección de tu navegador).
* Elige la carpeta que tiene por nombre el "id" puesto en la cabecera del archivo. 
* ¡Listo! ¡Ya tienes tu primer CodeLab!

###Linux (Probado en Ubuntu)

Movemos nuestro archivo codelab.md que queremos generar a la carpeta en la que tengamos descargado el ejecutable de claat.

Abrimos una terminal y accedemos desde el mismo a la carpeta en la que tengamos descargado el ejecutable de claat. Ejecutamos el comando:

``` bash
./claat-linux-amd64 export codelab.md
./claat-linux-amd64 serve
```
(sustitumos claat-linux-amd64 por nuestra versión)

* Tu navegador debería haberse abierto (si no lo hace, prueba a escribir localhost:9090 en la dirección de tu navegador).
* Elige la carpeta que tiene por nombre el "id" puesto en la cabecera del archivo. 
* ¡Listo! ¡Ya tienes tu primer CodeLab!

###macOS

Abre una Terminal y accede desde la misma a la carpeta en la que se encuentre el archivo codelab.md. Luego ejecuta:

``` bash
$ claat export codelab.md
$ claat serve
```

* Tu navegador debería haberse abierto (si no lo hace, prueba a escribir localhost:9090 en la dirección de tu navegador).
* Elige la carpeta que tiene por nombre el "id" puesto en la cabecera del archivo. 
* ¡Listo! ¡Ya tienes tu primer CodeLab!

## Aloja tu CodeLab
Duration: 0:01:00

Cuando ejecutaste el comando `claat export` creaste el sitio web estático necesario para alojar en un servidor web tu CodeLab.
Se generó **una carpeta con el identificador** que especificaste en "id" que contiene todos los archivos de la página, entre ellos el index.html, que puedes abrirlo de forma local.

Negative
: Ten en cuenta que cuando ves la página localmente abriendo el index.html algunos de los gráficos no se mostrarán (como access_time, Next, Back), pero funcionarán una vez esté online. 

Ahora que tienes el contenido estático generado puedes **alojarlo donde prefieras**.
Una opción es subiéndolo a un repositorio de Github y servirlo usando [Netlify](https://www.netlify.com/).

Si quieres crear tu propio índice con enlaces a los CodeLabs, [similar a este]((https://codelabs.developers.google.com)), también hay una herramienta que lo hace. Echa un vistazo aquí: [CodeLabs Site](https://github.com/googlecodelabs/tools/blob/master/site/README.md)
