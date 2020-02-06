## Parte III.6 Each and this.

En ocasiones con los elementos seleccionados queremos hacer cosas muy similares pero con ligeras diferencias.

Un enfoque posible para eso sería algo así:

```js
    $(function() {
        ...
        $("some_selector").eq(0).accion0..
        $("some_selector").eq(1).accion1..
        $("some_selector").eq(2).accion2..
        ...
        $("some_selector").eq(n).accionn..

    });
```

Una aproximación de este tipo presenta principalmente dos problemas.

- Es muy **ineficiente**, sobre todo si tenemos dentro de las acciones partes que se repiten.
- Tenemos que ir seleccionando **uno por uno** los elementos que nos ha devuelto el selector. Y, en ocasiones, sobre todo si la página se genera automáticamente a partir de fuentes de datos externas, no podemos saber cuántos elementos nos va a devolver el selector.

Para dar solución a este tipo de situaciones **jQuery** pone a nuestra disposición el método _**.each()**_ y el objeto _**\$(this)**_.

Lo que expresamos en el ejemplo lo podremos expresar, de un manera más eficiente y sin saber el número de elemento que nos va a devolver el selector, de la siguiente manera:

```js
    $(function() {

        $("some_selector").each(funcion(index) {
            //Acción que dependerá del elemento
            $(this).accion_particular...
        });
    });

```

En este ejemplo destacamos:

- **.each(..)** recibe como parámetro una función que se ejecutará una vez para cada una de los elementos que nos devuelva el selector.
- **index** es un parámetro opcional de la función. Indica la posición que ocupa cada elemento dentro del conjunto de elementos devueltos (empezando en cero).
- **\$(this)** hace referencia cada vez que se ejecuta la función. Al objeto que se está tratando actualmente de entre los devueltos por la selección.

Podemos concretar esto con un ejemplo concreto.

```js
$(function() {
    ...
    $(“li”).each(function(index) {
        console.log("El elemento  "+index+"contiene "+$(this).text());
        $(this).text("HOLA");
    }
}
```

En este ejemplo la función se ejecutará tanta veces como etiquetas \<li\> tenga en mi página sacando por consola el contenido de las mismas y modificándolo por un texto nuevo _"HOLA"_.

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
