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
