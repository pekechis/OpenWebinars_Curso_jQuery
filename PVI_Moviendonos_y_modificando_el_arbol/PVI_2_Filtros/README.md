## Parte VI.2. Filtros

Cuando los selectores me devuelven muchos elementos puedo estar interesado en filtralos para ajustar mi acción posterior a ciertas condiciones.

**jQuery**, al igual que otras muchas cosas, nos proporciona funciones para realizar filtrados. Algunas ya las hemos ido viendo pero para profundizar en este apartado nos vamos a centrar en:

- **.find()**
- **.filter()**
- **.slice()**

Iremos viendo las aplicaciones generales para cada una, y además un ejemplo:

```js

    //.find() Descendientes (hijos, nietos etc..) que encajan con el segundo selector
    $("some_selector").find("otro_selector");

    //Todos los descencientes con esas clase (td/td/….)
    $("table").find(".celda_verde");

    //.filter() Reduce los seleccionados a los
    //que encajan con el segundo selector
    $("some_selector").filter("otro_selector");

    //Todos los descencientes con esas clase (td/td/….)
    $("ul").filter(".lista_menu");

    //Con una función para cada uno de los resultantes del filtro
    //Tengo el índice dentro de los seleccionado y $(this)
    //Modifico si la función es TRUE
    $("some_selector").filter(function(index) {
    })...

    $("li").filter(function(index) {
        return index ===9
    }).text("SOY YO");

    //.slice() Selecciono un rango de entre los elegiods 0-based()
    $("some_selector").slice(inicio);
    $("some_selector").slice(inicio,fin);

    //De la primera fila la segunda y la tercera
    $("table tr").children().slice(1,3).text("");


´´´


Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
```
