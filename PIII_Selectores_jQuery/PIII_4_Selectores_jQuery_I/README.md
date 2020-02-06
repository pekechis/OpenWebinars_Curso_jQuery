## Parte III.4 Selectores jQuery I

Como ya hablamos en capítulos anteriores, a la hora de seleccionar elementos usando **jQuery** podemos usar los selectores CSS3 o también una serie de selectores propios.

De igual manera que CSS con sus selectores, **jQuery** tiene bastantes selectores propios (pseudoselectores en su mayoría,en realidad). En éste y en el próximo capítulo únicamente vamos a ver los más comunes o destacados.

Entre ellos:

- **:eq(index)** : Para seleccionar el elemento que está en la posición _index_ de entre todos los seleccionados con el selector del que es sufijo. Actualmente está depreciado y se usa la función _.eq()_ que ya ha sido tratada previamente.
- **:has("...)** : Para elementos que contienen dentro al menos un elemento del selector que le paso como parámetro.
- **:contains()** : Todos los elementos que contienen un texto en concreto.
- **:even o :odd** : Para elementos que dentro del padre están en la posición para o impar. Son selectores depreciados pero siguen siendo muy usados.
- **:input** : Para seleccionar cualquier elemento de un formulario, ya sea un _input_, _textarea_,_select_ o _button_.
- **:gt(index) o :lt(index)**: Para seleccionar elementos cuya posición entre los elementos seleccionados es mayor(gt) o menor(lt) que la posición expresada en index.
- **:first o :last** : Para seleccionar el primero o el último de los elementos seleccionados por el sufijo selector. Están también depreciadas y en su lugar se usan las funciones _.first()_ o _.last()_ haciendo **chaining**.

Recordad también dos conceptos que habíamos destacado:

- La _iteración Selección-Acción o Selección-Captura de evento_ que será nuestra formá típica de trabajar cuando estemos dando vida a nuestra página web con _jQuery_.
- El concepto de **CHAINING**.

Repositorio del Curso de jQuery desarrollado por @pekechis para @OpenWebinars.
