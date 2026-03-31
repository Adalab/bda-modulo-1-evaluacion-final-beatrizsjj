# Evaluación Módulo 1 Beatriz San José

## 1. Estructura

### Crear inventario

En la creación del inventario he creado la función agregar_producto (nombre, precio, cantidad). Para ello:

- He usado un bucle for para recorrer la lista y comprobar si el producto indicado ya estaba o no en el inventario.

Aquí la dificultad que encontré y que tuve que buscar fue saber cómo sumar a la cantidad que ya había la nueva cantidad indicada (+=).

- Si no está en la lista, he usado un else y .append() para añadir el nuevo diccionario a la lista inventario.

En este ejercicio lo que más difícil me ha resultado es entender el distinto funcionamiento de una lista y un diccionario, al tener una lista de diccionarios. Lo más complicado ha sido averiguar cómo buscar una clave en un diccionario que a su vez está dentro de una lista.

### Ver inventario

Para ver el inventario, he creado la función def ver_inventario() con un bucle for que recorriera cada producto de la lista. 

En este caso, la mayor dificultad, como en el anterior, ha sido referenciar bien los valores del diccionario en el print.

### Buscar producto

Para buscar un producto en el inventario, he crado la función buscar_producto (nombre), que funciona de la siguiente forma:
- He creado un bucle for para que recorra el inventario y ver si el nombre indicado coincide con algún nombre que esté dentro del inventario.
    - Si coincide, imprime el nombre del producto, el precio y la cantidad.
        - Al final he añadido un break, porque si no, me devolvía tanto la impresión con el nombre, el precio y la cantidad, como "el producto no se encuentra en el inventario".
    - Si no coincide, con un else debajo del for, he pedido que imprima que el producto no está en el inventario.

### Actualizar stock
En este caso, la función es muy parecida a la primera para agregar un producto al inventario.
He creado la función actualizar_stock (nombre, cantidad) y he seguido los mismos pasos que en el primer ejercicio

### Eliminar stock
Empecé como en el resto de funciones, con un bucle for para identificar si el nombre indicado en la función coincide con algún nombre de los productos del inventario. 
A continuación, usé el condicional 'if' para aplicar un .remove() si se encontraba en el inventario.
El else, para imprimir el mensaje en caso de que no se encuentre en el inventario, está debajo del for para que no estuviera dentro del bucle y no se accionara en cada iteración que no coincidía.


### Calcular valor del inventario
Para calcular el valor del inventario, tenía que crear una función, y utilizar un bucle for para recorrer la lista. Dentro de ese bucle, había que multiplicar el precio por la cantidad de cada producto e ir acumulando esa cantidad para saber el valor total.

En este caso, la dificultad/aprendizaje ha residido en:
- Acordarme de que para ir sumando elementos, tenía que crear una variable vacía al principio donde ir acumulando la suma.
- Aprender que la acumulación de una suma o una resta, etc., se puede hacer así: +=





#### Dudas y errores 
1. Durante todo el ejercicio, me costó entender que el inventario era una lista de diccionarios, o sea, una lista, y no un diccionario. Y quería acceder al inventario por clave: inventario [nombre]. Hasta que comprendí que usando el bucle for para recorrer el inventario, tenía que acceder a cada elemento mediante producto ["nombre"], porque producto es cada elemento de la lista, en este caso, producto es cada diccionario que contiene los datos de cada elemento con su respectivo clave:valor.
2. Otro error que he cometido un par de veces, es este:
producto ["nombre"] in inventario
Me di cuenta de que estaba mal planteado porque lo que necesitaba ver realmente es si producto ["nombre"] coincidía con el nombre entre paréntesis de la función (```def eliminar_producto (nombre```)). O sea, que tenía que plantearlo así:
```producto ["nombre"]== nombre```
3. Para la función eliminar_producto, me ha costado aplicar las funciones que vimos en clase pop(), clear(), popitem(), remove(), etc. 
Al principio lo intenté con pop(): producto ["nombre"].pop(), pero me daba error. Al buscar información, encontré que con esa sintaxis estaba intentando borrar un string, y los string no se pueden modificar directamente. Lo que yo necesitaba era borrar un elemento de una lista (el producto completo), y ya averigüé que se hacía con remove().
Al respecto estuve buscando información sobre las diferentes aplicaciones de pop() en listas o en diccionarios, y me quedó claro que:
    - En listas, pop() se usa para eliminar un elemento según su posición en esa lista (0, 1, 2...)
    - En diccionarios, elimina un elemento en función de su clave (nombre, edad, precio....)

4. Sin duda, el ejercicio más complicado fue el 7 porque implicaba combinar todo. Algunas dificultades que he encontrado haciéndolo:
    1. La posición del while. Al final, tuve que hacerlo sin el while, y luego intentar encajarlo al final. No entendía muy bien cómo funcionaba, porque estaba intentando ``` while producto_selecionado in inventario```. Al final, cuando ya hice toda la función, fue cuando me di cuenta de que necesitaba saber si el usuario quería seguir comprando o no, y que ahí era donde tendría sentido el while, y ya entendí su sentido:  se aplica cuando se cumple una condición, no para comprobar si algo está en una lista o en un diccionario, para eso estaría el if y el for.
    2. En general, todo ha sido un poco más difícil porque estaba manejando una lista de diccionario, y no acaba de resultarme fácil buscar o seleccionar elementos de dentro. Busqué en internet, y probé a usar ```inventario.get(producto_elegido)```, hasta que entendí que tenía que usar el for:
    ```for producto in inventario: if producto["nombre"] == producto_elegido:```
    3. También tuve problemas para ver cómo actualizaba realmente el inventario. Primero creé una variable ```inventario_actualizado = producto["cantidad"] - cantidad_producto```, pero no modificaba el inventario, solo almacenaba el valor. Al final concluí que lo que tenía que modificar directaemnte era el valor de dentro del diccionario, que no necesitaba otra variable.
    4. Otras dificultades que fui resolviendo a medida que probaba cómo funcionaba la función:
        - Colocar el else dentro del bucle for para que funcionara bien y no se imprimieran las dos opciones.
        - Poner bien los breaks
        - Comprender bien el flujo de la compra para que todo tuviera lógica y los pasos estuvieran ordenados
        - Diferenciar entre "producto no encontrado" y "stock insuficiente"
        - Ubicar bien la indicación de que el producto indicado no existe.
        - Hacer las iteraciones correctamente 
