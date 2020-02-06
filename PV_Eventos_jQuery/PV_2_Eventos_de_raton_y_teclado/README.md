## Parte V.2. Eventos de ratón y de teclado

Los eventos de ratón y teclado son los más comunes en la mayoría de las páginas. En este apartado vamos aprender a diferenciarlos, ya que hay algunos que pueden llevar a confusión, y vamos a conocer algunas propiedades interesantes del objeto evento que debemos de tener en cuenta en relación a estos eventos.

### Eventos de teclado

Son principalmente tres:

- **.keydown():** Evento que se dispara cuando presiono una tecla estando dentro de un elemento.
- **.keyup():** Evento que se dispara cuando libero la tecla presionada.
- **.keypress():** Evento que se dispara cuando presiono una tecla estando dentro de un elemento.

**IMPORTANTE:** Aunque pueden .keydown() y .keypress() pueden parecer lo mismo no son del todo iguales.

Para comprender un poquito mejor las diferencias entre ambas:

|       .keydown()       |         .keyup()         |
| :--------------------: | :----------------------: |
| Incluye "special keys" | No incluye "special keys |
|    Case Insensitive    |      Case sensitive      |

### Eventos de ratón

En relación a los eventos de ratón tenemos bastantes más:

- **.mousedown():** Al presionar el ratón estando dentro de un elemento.
- **.mouseup():** Cuando libero el ratón tras hacer click en alguno de sus botones.
- **.mousenter():** Cuando el ratón entra en un elemento.
- **.mouseleave():** Cuando el ratón sale de un elemento.
- **.mousemove():** Cuando muevo el ratón dentro de un elemento.
- **.mouseover():** Cuando el ratón entra en un elemento.
- **.mouseout():** Cuando el ratón sale de un elemento.
- **.click():** Cuando hago click sencillo de ratón dentro de un elemento.
- **.dblclick():** Cuando hago doble click de ratón detro de un elemento.

Puede parecer que **.mouseenter()** y **.mouseleave()** son similares a **.mouseover()** y **.mouseout()** pero los dos primeros son simulaciones de eventos propios de Internet Explorer que **jQuery** incluye para que puedan ser utilizado independientemente del navegador. Adicionalmente hay otras diferencias:

|      .mouseover()       |  .mouseenter()   |
| :---------------------: | :--------------: |
| El elemento y sus hijos | Sólo el elemento |

|       .mouseout()        |   .mouseleave()    |
| :----------------------: | :----------------: |
| Del elemento y sus hijos | Salgo del elemento |

Esto se puede apreciar claramente en el ejmplo incluido en este mismo capítulo.

### Propiedades de Event

En relación a estos eventos hay varias propiedades del objeto event que pueden resultar interesantes:

- **e.pageX:** Posición del ratón con respecto a la izquierda del documento.
- **epageY:** Posición del ratón con respecto a la zona superior del documento.
- **e.which:** Contiene el código de la tecla o del botón del ratón (1-izquierda,2-central,3-derecha).
- **e.type:** Nombre del evento que se ha producido. Especialmente útil si nuestro manejador es para más de un evento y queremos hacer cosas diferentes.
- **e.metaKey:** Es true si hemos presionado la tecla de Windows en Windows y la tecla de comando en Mac.

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
