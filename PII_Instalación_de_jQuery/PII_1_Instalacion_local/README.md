## Parte II.1. Instalación Local

Para empezar usar a **jQuery** en mi página web y, de esta manera, poder dotarla de vida e interactividad lo primero que tengo que hacer es _instalar_ **jQuery** en mi proyecto para que dicha librería esté disponible cuando se carga la página.

Lo primero que tenemos que hacer es descargar **jQuery** desde la siguiente [página](https://jquery.com/downloads). Actualmente la versión disponible es la versión 3.4.1.

En esa página encontraremos varias cosas pero para empezar elegiremos entre una de estas dos opciones:

- jQuery **_compressed_** que es la más adecuada para producción. Ocupa menos espacio pero es prácticamente ilegible.
- jQuery **_uncompressed_** que es la más adecuada para desarrollo. Ocupa más espacio pero es legible y podremos consultar el código de jQuery si es necesario.

Una vez hemos descargado ese fichero tendremos que añadirlo a nuestra página. Esto se hará en el código HTML de la siguiente manera:

```html
<!-- DENTRO DE LA CABECERA>
<head>
    ....
    <!-- o la versión uncompressed -->
    <!-- hemos colocado el fichero en la carpeta js -->
    <script src="js/jquery-3.4.1.js"></script>
    ....
</head>

```

Podemos comprobar fácilmente que todo está correcto desde la consola que nos proporcionan todos los navegadores dentro de sus herramientas para desarrolladores. Dentro de esa consola puedo ejecutar cualquiera de estas dos opciones para comprobarlo:

```javascript
$();

jQuery;
```

En caso de que nos devuelva algo diferente de _null_ (en el primer caso) o \*_jQuery is no defined_ (en el segundo caso) es que todo está correcto. Y si está correcto es muy interesante que profundicéis en lo que se os muestra ya que contiene todo lo que nos puede proporcionar la librería.


Una vez hemos hecho esta _instalación_ ya podemos crear nuestros scripts usando la librería **jQuery**. Estos scripts los añadiremos al final de \<body\> por varios motivos:

* **jQuery** trabaja con el árbol HTML y nunca está de más echar un vistazo al contenido que tiene la página antes de empezar a "jugar" con ella.
* Aunque los navegadores ya tienen multihilo para cargar los distintos elementos de la página es cierto que es recomendable empezar a "jugar" cuando estemos seguros que todo lo demás se ha cargado.

Para ello podremos optar por una de estas dos opciones para usar **jQuery**:

```html

<!-- Versión más larga -->
    <script>
        $(document).ready(function() {
        //Código que desarrollaremos nosotros
        });
    </script>
</body>

<!-- Versión corta. Yo la prefiero -->

    <script>
        $(function() {
        });
    </script>
</body>

```

Os dejo una plantilla para tener todo esto a vuestra disposición en la carpeta template de este mismo repositorio.

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
