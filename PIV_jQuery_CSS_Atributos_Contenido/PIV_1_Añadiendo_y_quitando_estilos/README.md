## Parte IV.1. Añadiendo y quitando estilos

Una de las grande ventajas de **jQuery** es la facilidad que nos da tanto para **obtener** como para **modificar** los **estilos** de los diferentes elementos de nuestra web.

### La función .css(..)

La función principal de **jQuery** para trabajar con estilos es  ***.css()*** y cuando trabajemos con ella podemos diferenciar principalmente dos situaciones:

* Cuando trabajemos con **una única propiedad** CSS para obtener o establecer.
* Cuando trabajemos para establecer o obtener el valor de **más de una propiedad** CSS.

Para una propiedad:

```js

//Obtener el valor de una sola propiedad
//MUY IMPORTANTE: La propiedad se obtiene del PRIMER ELEMENTO que nos devuelve el selector.
var valor =  $("some_selector").css("propiedad");

//Ejemplo
var color = $("li").css("color");

//Establecer el valor de una propiedad para todos los elementos que nos devuelve el selector
$("some_selector").css("propiedad","valor");

//Ejemplo (Incremento en 50px el valor actual)
$("img").css("width","+=50");


//Pasando una funcíon que recibe como parámetros la posición dentro de los seleccionado y el antiguo valor
$("some_selector").css("propiedad",function(index, valor))  {
    //$(this) hará referencia el elemento actual
});

```
Para varias propiedades:

```js

//Si queremos obtener varias propiedades CSS del PRIMER ELEMENTO que nos devuelva el selector
//Devuelve una ARRAY
var props = $("some_selector").css([ "prop1","prop2",....."propn"]);

//Ejemplo 
var colores = $("li").css(["color","background-color"]);

//Para establecer el valor de varias propiedades en los elementos seleccionados 
$("some_selector").css( {
    prop1: valor1, //o expresión/función
    prop2: valor2, //o expresión/función
    ....
    propN: valorn //o expresión / función
});

//Ejemplo
$("li").css({
    color: #FFF,
    background-color: #000
});

```

### Funciones adicionales

Además de la función ***.css()*** tenemos a nuestra disposición dos funciones más para trabajar con la anchura y la altura de los elementos:

* La función **.width()**.
* La función **.height()**.

Lo que podemos hacer con estas funciones también podemos hacerlo con la función **.css()** y de igual manera no sirven para obtener o establecer la altura y la anchura.

```js

//Obtener el valor de las propiedades del primer elemento de entre los seleccionados
var altura = $("some_selector").height();
var anchura = $("some_selector").width();


//Para modificar la altura o anchura de todos los elementos seleccionados
$("some_selector").height("(valor");
$("some_selector").width("(valor");
```

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars
