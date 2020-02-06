## Parte IV.3 Jugando con atributos

Continuando con el capítulo, **jQuery** también nos proporciona una serie de funciones que nos van a permitir modificar atributos y propiedades de los distintos elementos de mi página web.

### Atributos vs Propiedades

Antes continuar examinando la diferentes funciones hay que aclarar las diferencias que hay entre un atributo y una propiedad.

Los **atributos** nos dan información adicional sobre un elemento o etiqueta que está incluida en el HTML. Cuando lo obtenemos o modificamos hacemos referencia al **valor o estado original**.

**LOS ATRIBUTOS ESTÁN EN EL HTML**

En relación a la **propiedades**, son características de una instancia concreta de esa etiqueta en el DOM. Al obtenerlas o modificarlas estamos haciendo referencia al **valor o estado actual**.

**NO ES NECESARIO QUE LAS PROPIEDADES ESTÉN EL HTML** ya que los objetos al ser instanciados en el DOM tienen una serie de propiedades por defecto.

Para poder aclarar esto de una mejor manera vamos a ver un ejemplo:

```js

    //Si tenemos el siguiente elemento en la página
    // <input id="ej" type="text" value="Pepe">

    console.log($("#ej").attr("value"));
    //Salida -> Pepe

    console.log($("#ej").prop("value"));
    //Salida -> Pepe

    console.log($("#ej").attr("disable"));
    //Salida -> undefined -> No está en el HTML

    console.log($("#ej").attr("disable"));
    //Salida -> false . No está pero es una propiedad del DOM

    //Modificamos el valo del elemento del DOM
    $("#ej").val("Manuel");

    console.log($("#ej").attr("value"));
    //Salida -> Pepe, el valor que tengo en el HTML

    console.log($("#ej").prop("value"));
    //Salida -> Manuel, el valor actual de la propiedad

```

En conclusión y para que no tengamos problemas:

* No usar versiones anteriores a jQuery 1.6.
* Usar siempre que sea posible las funciones que hacen referencia a propiedades. Aunque muchas veces nos vayan a dar resultados iguales.
* Usar .attr() únicamente cuando sean atributos _custom_, es decir que no van a tener propiedades asociadas.
* Tener en cuenta que en los atributos siempre tenemos cadenas de caracteres pero que en las propiedades podemos tener otro tipo de datos.

Una vez ha quedado claro vamos a ver ejemplos de uso de las funciones más comunes en jQuery para trabajar con attributos y propiedades.

### .attr()

Esta función de **jQuery** sirve para obtener o establecer el valor de uno o varios atributos.

Vamos a ilustrar su uso con varios ejemplos.

```js
    
    //Obtengo la dirección del PRIMER ENLACE
    //Obtengo el valor del atributo href
    var url = $("a").attr("href");

    //Todos los enlaces se abrirán en una nueva ventana
    //Establezco ese atributo para TODOS LOS enlaces
    $("a").attr("target","_blank");

    //Establezco dos atributos a la vez para 
    //el elemento con ese id (el selector podría devolver más elementos)
    $("#miprofile").attr({
        alt:"Foto de mi cara",
        title:"Foto hecha por mí")
    });


```

### .removeAttr()

Esta función de **jQuery** sirve para borrar atributos de los elementos seleccionados (en caso de que existan en los elementos)

Su sintaxis y un ejemplo:

```js
    //Eliminar un atributo dado de los los elementos seleccionados
    $("some_selector").removeAttr("some_attribute");

    //Ejemplo
    //Quita el atributo required de todos los inputs (si es que lo tenían)
    $("input").removeAttr("required");

```

### .prop()

Esta función de **jQuery** sirve para obtener o  modificar el valor de una o varias propiedades.


Su es uso es análogo a _.attr()_ y lo podemos ver en el siguiente ejemplo:

```js
    //Obtengo propiedad href del primer enlace
    var url = $("a").prop("href");

    //Todos los enlaces se abrirán en una nueva ventana
    //Pongo ese valor a la propiedad
    $("a").prop("target","_blank");

    //Establezco dos propiedades a la vez para una imagen que tiene un id
    $("#miprofile").prop({
        alt:"Foto de mi cara",
        title:"Foto hecha por mí")
    });

```

### .removeProp()

Esta función de **jQuery** sirve para eliminar propiedades de los elementos seleccionados.

Su uso es análogo a _.removeAttr()_ y lo podemos ver en el siguiente ejemplo:

```js
    //Eliminar una propiedad dada de los los elementos seleccionados
    $("some_selector").removeProp("some_attribute");

    //Ejemplo
    $("input").removeProp("required");

``

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars
