## Parte VI.5. Borrando Elementos

Para acabar con este capítulo....más funciones de **jQuery**, esta vez para borrar elementos del DOM y para reemplazar nodos del mismo.

Para el borrado de nodos destacamos las siguiente funciones:

- **.remove() y .detach()**

Para reemplazar nodos destacamos:

- **.replaceAll() y .replaceWith()**

### Borrando nodos con .remove() y .detach()

Ls funciones o métodos _.remove() y .detach()_ tienen comportamiento similares. Ambos sirven para borrar elementos seleccionados del DOM. La diferencia entre ambos es que usando _.detach()_ puedo guardarme esos elementos (con eventos incluidos) para reponerlos luego.

La síntaxis general es:

```js
//Borra del DOM los elementos seleccionados
$("some_selector").remove();
//Aplicando un filtro a los seleccionados
$("some_selector").remove("filter_selector");

//Guardando lo borrado
var result = $("some_selector").detach();
//Guardando y filtrando"
var result = $("some_selector").detach("filter_selector");
```

Y podemos poner varios ejemplos:

```js
//Borra todas las imágenes
$("img").remove();

//Borra todas las imágenes de la clase logo
$("img").remove(".logo");

//Borra todas las imágenes y las recupera
var imagenes = $("img").remove();
$("body").append(imagenes);
```

### Reemplazando nodos con .replaceAll() y .replaceWidth()

Ambas son muy similares, sirven para reemplazar elementos. La primera reemplaza el objetivo con el conjunto de los elementos seleccionados y la segunda funciona al revés.

La síntaxis y un ejemplo para cada una de ellas las podemos ver en el siguiente cuadro de código:

```js
//Reemplaza el elemento objetivo con el conjunto de los seleccionado
$("some_selector").replaceAll(target);

//Se sustituyen todas las celdas td por celdas td que contienen X
$("<td>X</td>").replaceAll("td");

//Igual que el anterior pero el origen y el objetivo están al revés
$(target).replaceWith("some_selector");
//Se sustituyen todas las celdas td por celdas td que contienen X
$("td").replaceWith("<td>X</td>");
```

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
