## Parte IV.2 Jugando con clases 

Si ya tenemos nuestra hoja de estilos perfectamente definida podemos usar las clases de esa hoja de estilos para , con funciones **jQuery**, cambiar la apariencia de los elementos de mi página web.

Las funciones más comunes para este tipo de acciones son:

* **_.addClass()_**: Para añadir clases CSS a los elementos seleccionados.
* **_.removeClass()_**: Para eleminar clases CSS de los elementos seleccionados.
* **_.toggleClass()_**: Para alternar que una clase esté o no esté en los elementos seleccionados.
* **_.hasClass()_**: Para saber si una clase está en **CUALQUIERA** de los elementos seleccionados.

### .addClass()

Esta función de **jQuery** nos permite añadir una o varias clases a los elementos seleccionados.

Tenemos varias posibilidades:

```js

//Le pasamos uno o varios nombre de clases a añadir a los elementos seleccionados
$("some_selector").addClass("clase1 clase2 ...claseN");

//Le pasamos una función que se aplica a cada elemento seleccionado.
// Disponemos de la posición del elemento (index) y de $(this) para hacer referencia al elemento tratado
// El valor devuelto será el nombre de la clase que se va añadir al elementos en concreto
$("some_selector").addClass(function(index) {
    ...
    return "some_className";
    ...
});

```

Un ejemplo para cada uno de estos casos:

```js
    
    //Añade las clases btn y btn-error a todos los elementos <button>
    $("button").addClass("btn btn-error");

    //Le añade a cada elemento <section> la clase section-X (según su posición en el conjunto de los elementos seleccionados)
    $("selection").addClass(funcion(index) {
        return "section-"+index;
    });
```

### .removeClass()

Esta función de **jQuery** nos permite borrar una o varias clases de los elementos seleccionados. Evidentemente es necesario que los elementos tengan esa clase o clases para poder eliminarlas.

Tenemos varias posibilidades:

```js

    //Le pasamos uno o varios nombres de clases a borrar
    $("some_selector").removeClass("clase1, clase2,...,claseN");

    //Le pasamos una función que se aplica a cada elemento de entre los elementos seleccionados
    // y cuyo valor devuelto será la clase que se pretende borrar en cada elemento. 
    //Le pasamos la posición y tendremos disponible $(this).
    $("some_selector").removeClass(function(index) {
        ...
        return "someClassName";        

    });

```

Un ejemplo para cada uno de estos casos:

```js

    //Borra las clases btn y btn-error de los elementos <button> en caso de que las tengan
    $("button").removeClass("btn btn-error");

    //Borra de cada elemento section la clase "section-index" en caso de que la tengan. Index es la posición que ocupan dentro del conjunto de elementos que devuelve el selector.
    $("button").removeClass(function(index) {
        return "section-"+index;
    });
```

### .toggleClass()

Esta función sirve para añadir o quitar clases dependiendo de si esas clases están presentes o no o dependiendo de parámetros que se le pasan.

Tenemos varias posibilidades:

```js

    //Le pasamos el nombre de las clases de las que queremos alternar el estado. Es decir se añaden si no están o se quitan si están
    $("some_selector").toggleClass("clase1 clase2 ...claseN");

    //Igual que el anterior pero con un parámetro boleano (que puede ser el resultado de una función) que nos dice si hay que añadirla (true) si no está o quitarla si está (false)
    $("some_selector").toggleClass("clase1 clase2 ..claseN",booleano);

    //Pasándole una función cuyo valor de retorno será el nombre de la clase cuyo estado queremos alternar. Esa función recibe como parámetros la posición de cada elemento dentro del conjunto de elementos seleccionados.Tengo acceso a $(this).
    $("some_selecto").toggleClass(funcion(index) {
        ...
    });

    //Análoga a la anterior pero con un parámetro booleano adicional que indica si hay que añadirla (true) si no está o quitarla si está (false). Tengo acceso a $(this).
    $("some_selecto").toggleClass(funcion(index) {

    },booleano);

```

Algunos ejemplos para estos casos:

```js
    
    //Quita las clases si están en los elementos seleccionados o las añade si no están.
    $(“button”).toggleClass(“btn btn-error”);

    //Quita las clases en los elementos seleccionados si no están.
    $(“button”).toggleClass(“btn btn-error”,false);

    //Quita las clases "section-1...section-2..." en los elementos seleccionados si están o las añade si no están.
    $(“section”).toggleClass(function(index) {
        return “section-”+index;
    });

```

### .hasClass()

Esta función de **jQuery** devuelve _TRUE_ si **CUALQUIERA** de los elementos seleccionado tiene esa clase y _FALSE_ en caso de que ninguno de ellos la tenga.

```js
    
    $(“some_selector”).hasClass(“clase1”);

    //Ejemplo
    $(“.btn”).hassClass(“btn-error”);

```

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
