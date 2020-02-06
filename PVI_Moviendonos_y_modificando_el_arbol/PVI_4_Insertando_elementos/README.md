## Parte VI.4. Insertando Elementos

En capítulos anteriores hemos hablado de varias funcionesd de **jQuery** que nos permitían añadir contenidos. Pues bien, hay aún más funciones para ello, incluso algunas que nos permiten mover elementos.

Destacaremos las siguientes:

- **.after() y .before()**
- **.insertAfter() e .insertBefore()**
- **.clone()**

### .after() y .before()

Son funciones que me permiten insertar contenido (uno o varios) justo antes (before) o después (after) de los elementos seleccionados. Ambas tienen el mismo uso. Únicamente cambia el nombre.

La forma más sencilla de usarlas sería la siguiente:

```js

    $("some_selector").after(content1,.....,contentN);
    $("some_selector").before(content1,.....,contentN);
```

Es importante destacar que ese contenido puede ser:

- HTML.
- Texto.
- Un objeto jQuery, lo que provoca que ese objeto se desplace por el DOM.
- Un array de varios elementos de los anteriormente citados.

También pueden usarse de otras maneras:

```js

    //Con función cuyo valor devuelto es lo que se añade.
    //Tengo disponible posición y $(this)
    $("some_selector").after(function(index) {
        ...
    });

    //Igual pero con el HTML del elemento disponible
    $("some_selector"”).after(function(index,html) {
        ...
    });

```

A continuación ejemplos de estas posibilidades:

```js
//Añado una fila más después de la última fila
$("tr")
  .last()
  .after("<tr><td>F</td></tr>");

//Muevo la primera fila al final
$("tr")
  .last()
  .after($("tr").first());

//Duplico las filas
$("tr").after(function(index, html) {
  return html;
});
```

### .insertAfter() e .insertBefore()

Son funciones similares a las anteriores pero en este caso lo seleccionado es lo que se añade a lo que se selecciona después como parámetro (el objetivo) antes (before) o después (after). Al revés que antes:

La síntaxis general es la siguiente:

```js
$("origin").insertAfter(target);
```

Ese _target_ puede ser:

- Un selector.
- HTML.
- Objeto jQuery ( se desplazará).
- Un array de los anteriores.

Por ejemplo:

```js

    //Añado una fila más después de la última fila
    $("<tr><td>F</td></tr>").inserAfter("tr:last");

    //Muevo la primera fila al final
    $("tr:fist").insertAfter($("tr"”).last());

```

Todo esto sería igual para **.insertBefore()**

### .clone()

Crea una copia profunda(con descendientes) de los elementos seleccionados. Y le puedo pasar como parámetros si quiero conservar sus handlers y los de sus descendientes.

```js

    //De manera general
    $("selector").clone(withEvents);
    $("selector").clone(withEvents,whithDeepEvents);

    //Clono la primera fila y la añado al final
    $("tr").first().clone(false).appendTo(“table”);


```

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
