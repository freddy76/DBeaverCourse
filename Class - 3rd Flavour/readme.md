### **Módulo 1: Introducción a las Bases de Datos y a DBeaver**

1. **Ejercicio 1**: Conecta DBeaver a la base de datos de ejemplo proporcionada y explora la estructura de las tablas. Haz una lista de los nombres de las tablas y sus columnas.
2. **Ejercicio 2**: Identifica las relaciones entre las tablas en la base de datos de ejemplo (por ejemplo, relación entre clientes y pedidos).

---

### **Módulo 2: Conceptos Básicos de SQL**

1. **Ejercicio 1**: Crea una tabla llamada `Producto` con las columnas `id_producto` (PRIMARY KEY), `nombre`, `precio`, y `stock`.
2. **Ejercicio 2**: Inserta tres registros en la tabla `Producto` con valores ficticios.
3. **Ejercicio 3**: Actualiza el precio de un producto específico.
4. **Ejercicio 4**: Borra un producto cuyo `id_producto` coincida con un valor dado.

---

### **Módulo 3: Consultas Básicas con SELECT**

1. **Ejercicio 1**: Selecciona todos los productos de la tabla `Producto`.
2. **Ejercicio 2**: Muestra solo el nombre y el precio de los productos que tienen un `stock` mayor a 50.
3. **Ejercicio 3**: Realiza una consulta para obtener los productos cuyo nombre contenga la palabra "Pro".
4. **Ejercicio 4**: Ordena los productos de menor a mayor precio.

---

### **Módulo 4: Funciones Agregadas y Agrupación de Datos**

1. **Ejercicio 1**: Obtén la cantidad total de productos en la tabla `Producto`.
2. **Ejercicio 2**: Calcula el precio promedio de todos los productos.
3. **Ejercicio 3**: Agrupa los productos por categorías y muestra la cantidad de productos en cada categoría.
4. **Ejercicio 4**: Muestra las categorías que tienen más de 5 productos usando `HAVING`.

---

### **Módulo 5: Consultas Complejas y Subconsultas**

1. **Ejercicio 1**: Encuentra los productos cuyo precio sea superior al precio promedio de todos los productos (usa una subconsulta en el `WHERE`).
2. **Ejercicio 2**: Lista todos los clientes que han realizado pedidos y muestra sus nombres y el total de sus pedidos.
3. **Ejercicio 3**: Usa una subconsulta en el `FROM` para listar productos con el precio más alto de cada categoría.
4. **Ejercicio 4**: Encuentra productos disponibles que no se hayan vendido en ningún pedido (usa `NOT IN`).

---

### **Módulo 6: Uniones de Tablas (JOINS)**

1. **Ejercicio 1**: Realiza una `INNER JOIN` entre las tablas de productos y pedidos para listar los productos pedidos junto con la cantidad solicitada.
2. **Ejercicio 2**: Usa un `LEFT JOIN` para mostrar todos los productos y, si aplicable, los pedidos asociados.
3. **Ejercicio 3**: Haz un `RIGHT JOIN` entre la tabla de pedidos y la tabla de clientes para ver todos los clientes y sus pedidos, incluyendo aquellos que no han hecho pedidos.
4. **Ejercicio 4**: Realiza un `FULL JOIN` entre productos y proveedores para listar todos los productos y sus proveedores, si existen.

---

### **Módulo 7: Vistas y Procedimientos Almacenados**

1. **Ejercicio 1**: Crea una vista llamada `ProductosEnAlmacen` que muestre solo los productos con stock superior a 10.
2. **Ejercicio 2**: Crea una vista que contenga el total de ventas por cada producto (usa una combinación de tablas y agregaciones).
3. **Ejercicio 3**: Modifica la vista para que solo muestre productos con ventas superiores a una cantidad específica.
4. **Ejercicio 4**: Elimina una de las vistas creadas y vuelve a crearla con un filtro adicional.

---

### **Módulo 8: Administración Avanzada de Bases de Datos**

1. **Ejercicio 1**: Crea un usuario ficticio en SQLite y otórgale permisos para realizar `SELECT` en la tabla de productos.
2. **Ejercicio 2**: Usa `REVOKE` para retirar los permisos de modificación en la tabla de productos a ese usuario.
3. **Ejercicio 3**: Realiza un backup de la base de datos y luego simula una pérdida de datos eliminando algunas filas de la tabla `Producto`. Restaura el backup para verificar que puedes recuperar los datos.
4. **Ejercicio 4**: Crea una tabla de auditoría para registrar cambios realizados en la tabla de `Producto` (inserciones, actualizaciones y eliminaciones).

---

### **Módulo 9: Optimización de Consultas**

1. **Ejercicio 1**: Usa `EXPLAIN` en una consulta compleja de la base de datos y analiza el plan de ejecución.
2. **Ejercicio 2**: Crea un índice en la columna `nombre` de la tabla `Producto` y observa si mejora el rendimiento de las consultas que usan filtros en esta columna.
3. **Ejercicio 3**: Realiza una consulta que incluya un `JOIN` y compárala con el rendimiento de la misma consulta usando una subconsulta (verifica con `EXPLAIN`).
4. **Ejercicio 4**: Prueba con `DISTINCT` y sin `DISTINCT` en una consulta con `JOIN` para ver si hay diferencia en el tiempo de ejecución.

---

### **Módulo 10: Proyecto Final**

**Ejercicio**: Diseña y construye una base de datos que gestione un sistema de inventarios. La base de datos debe incluir tablas de productos, categorías, proveedores, órdenes de compra, y clientes. Los requisitos son:
   - Crear relaciones entre las tablas usando claves foráneas.
   - Generar vistas que resuman los datos de inventario, ventas y clientes.
   - Implementar consultas para calcular las ganancias, analizar los productos más vendidos y listar las órdenes pendientes.
   - Optimizar las consultas de inventario con índices y `EXPLAIN`.

---
