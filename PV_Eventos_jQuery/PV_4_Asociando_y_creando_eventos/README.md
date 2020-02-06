## Parte V.4. Asociando y creando eventos

Además de las operaciones que hemos visto anteriormente, que me permiten capturar eventos y darles respuesta, **jQuery** nos permite una serie de operaciones avanzadas con eventos:

* El control de la propagación de los eventos.
* Conectar y desconectar manejadores de eventos.
* Simular la ocurrencia de eventos.
* Crear mis propios eventos.

### Control de propagación de eventos

Una vez capturado un evento, y desde el objeto **event** que recibe la función del handler podemos controlar, con algunos de sus métodos, la propagación de dicho evento.

La funciones más importantes son las siguientes:

```js
    //Evita el comportamiento por defecto
    event.prevenDefault();

    //Para los propagación hacia arriba
    event.stopPropagation();

    //Para el resto de los handlers y la propagación hacia arriba
    event.stopImmediatePropagation();

```

Un ejemplo del uso de estas funciones sería el siguiente:

```js
    $("a").click(function (event) {
        event.preventDefault();
        alert("No me voy a ningún sitio");
        //Si algún padre tuviera algún handler no se ejecutaría
        event.stopImmediatePropagation();
    });

```


### Conectar y desconectar Handlers

La conexión de handlers a elementos ya la habíamos visto en capítulos anteriores usando métodoso como **.on()** y los métodos con nombre de eventos.

Para desconectar esos Handler **jQuery** nos proporciona principalmente la función **.off()** que se puede usar de varias maneras y hace el efecto contrario a **.on()**. Puede usarse de varias maneras y algunas de las más comunes vamos a ilustrarlas a continuación:

```js

    //Borra todos los handlers asociados a un selector
    $("some_selector").off();

    //Borra una serie de handlers asociados a un selector
    $("some_selector").off("event1 event2...eventN");

    //Borra una serie de handlers asociados a un selector
    //por asociación delegada.
    //Tiene que tener las misma definición que cuando habíamos hecho
    //un .on() delegado.
    //Tercer parámetro opcional “**” borra sólo los delegados 
    $("some_selector").off("event1 event2...eventN","selector2");


```

Un **PROBLEMA** con los **handlers** asociados con ***.on()** tal y como los habíamos usado hasta ahora es que no se asocian con elementos nuevos que se hayan añadido al DOM después de cargar la página.

En versiones antiguas de **jQuery** esto se solucionaba con los métodos o funciones **.live()** y **.die()** que conectaban o desconectaban handlers para todos los elementos seleccionados ahora o en un futuro.

En versiones actuales de **jQuery** este problema se soluciona usando una **ASIGNACIÓN DELEGADA** de la captura de eventos al padre. Vamos a verlo con un ejemplo:


```js
    //Handler únicamente para los elementos que ya EXISTEN (ASIGNACIÓN //DIRECTA)
    $("p").on("click", function (event) {
        alert("Click en párrafo");
        event.stopImmediatePropagation();
    });

    //Handler para los nuevos y los que voy a seguir creando
    //ASIGNACIÓN DELEGADA
    $("div.output").on("click", "p", function (event) {
        alert("Click en párrafo- DELEGADA");
        event.stopImmediatePropagation();
    });

```

### Disparando eventos

En ocasiones puede ser necesario **SIMULAR** que se ha producido un evento **LANZÁNDOLO** de manera artificial cuando me interesa.

Eso se consigue con las funciones **.trigger()** y **.triggerHandler()** cuyo uso más frecuente es el siguiente:

```js
    //Simulo que se ha producido un eventos en los elementos del selector
    $("some_selector").trigger("some_event");

    //El argumento puede ser un objeto Evento. Pasa toda la información
    $("some_selector").trigger(event);

    //Ejecuto todos los handlers asociados evento
    $("some_selector").triggerHandler("some_event");

    //Ejecuto todos los handlers asociados a un objeto del tipo evento
    $("some_selector").triggerHandler(event);


```

Aunque puede parece que el uso de ambos es idéntico hay varias diferencias importantes:

* Si uso **.trigger()** el comportamiento por defecto se sigue manteniendo y hay propagación.
* Si uso **.triggerHandler()** no se ejecuta el comportamiento por defecto del elemento, debo tener obligatoriamente un handler asociado para el evento concreto y no hay propagación del evento.

En ambos si uso handlers y quiero que se simule de manera efectiva debo pasar el objeto evento que lleva todas la información.

### Creando mis propios eventos

Para crear mis propios eventos usaré las funciones **.on()** y **.trigger() / .triggerHandler()**.

Algo así:

```js
    //Uso el nombre de “mi evento”
    $("some_selector").on("mi_evento"..........);

    //Lo utilizo con trigger
    $("........").trigger("mievento");
    $("........").triggerHandler("mievento");

```

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
