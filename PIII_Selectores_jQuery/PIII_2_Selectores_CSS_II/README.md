## Parte III.2 Selectores CSS II

Además de los vistos en el apartado anterior otros selectores CSS (pseudoselectores o pseudoelementos en este caso) que son muy usados son los siguientes:

- **:hover** : Para seleccionar el elemento sobre el cuál paso el cursor del ratón.
- **:visited** : Para seleccionar los enlaces visitados.
- **:first-of-type o :first-child**: Para seleccionar el elemento de un tipo determinado que es el primero de ese tipo dentro del padre o para seleccionar el elemento determinado que es el primer hijo de un padre determinado.
- **:last-of-type o :last-child**: Análogo al anterior pero haciendo referencia al último y no al primero.
- **:nth-child(pos) o :nth-of-type(pos)** : Análogo a los anteriores pero especificando la posición en la que se encuentra el elemento o el hijo como parámetro (pos).
- **:required** : Para seleccionar cualquier elemento de un formulario que sea requerido.
- **::after** : Usado para añadir algo (con la propiedad content) después de algún elemento determinado.
- **::before** : Usado para añadir algo (con la propiedad content) antes de algún elemento determinado.

Recordad que este tipo de selectores, a los que se llama _pseudoselectores_ o _pseudoelementos_ son añadidos a los selectores que hemos visto en el apartado anterior. Por ejemplo para **:hover** podríamos usarlo de la siguiente manera:

```js
    ...
    //Al pasar el ratón por la etiqueta h1
    $("h1:hover")...
    ...
```

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
