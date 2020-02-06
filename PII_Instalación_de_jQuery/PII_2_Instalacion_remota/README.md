## Parte II.2. Instalación remota.

De la misma manera que nos hemos descargado **jQuery** para usarlo en nuestro proyecto podemos usar jQuery remotamente usando la copia almacenada en un **CDN**. Este CDN puede ser de varios proveedores como _Microsoft_, _Google_ etc...

Esto se hará en el código HTML de la siguiente manera:

```html
<!-- DENTRO DE LA CABECERA>
<head>
    ....
    <!-- o la versión uncompressed -->
    <!-- usando el CDN de Google -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    ....
</head>

```

Pero exactamente, ¿qué es esto de un CDN?:

Un _**CDN**_ _(Content Delivery Network)_ es una red de servidores distribuidos geográficamente que actúan como _caché_ , normalmente para achivos de uso frecuente, y que mejoran la velocidad de navegación de los usuarios.

De igual manera que cuando lo instalamos localmente, podemos comprobar fácilmente que todo está correcto desde la consola que nos proporcionan todos los navegadores dentro de sus herramientas para desarrolladores. Dentro de esa consola puedo ejecutar cualquiera de estas dos opciones para comprobarlo:

```javascript
$();

jQuery;
```

En caso de que nos devuelva algo diferente de _null_ (en el primer caso) o \*_jQuery is no defined_ (en el segundo caso) es que todo está correcto. Y si está correcto es muy interesante que profundicéis en lo que se os muestra ya que contiene todo lo que nos puede proporcionar la librería.

Y para usarla la librería en este caso la usaremos de la misma manera que lo hacíamos cuando instalábamos **jQuery** para ser usada de manera local.

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
