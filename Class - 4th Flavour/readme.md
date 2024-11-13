### **Módulo 1: Introducción a las Bases de Datos y a DBeaver**

1. **Ejercicio 1**: Conecta la Sample Database en DBeaver y explora la estructura de las tablas. Anota cuántas tablas hay y el nombre de cada columna en las tablas `Album`, `Artist`, `Track`, y `Customer`.
2. **Ejercicio 2**: Identifica las relaciones entre las tablas `Invoice` e `InvoiceLine`. Describe qué tipo de relación existe entre estas tablas y otras como `Customer` y `Track`.

---

### **Módulo 2: Conceptos Básicos de SQL**

1. **Ejercicio 1**: Crea una nueva tabla llamada `Promotions` con las columnas `id`, `description`, `discount_percent`, y `start_date`.
2. **Ejercicio 2**: Inserta tres registros en la tabla `Promotions` con valores ficticios para cada columna.
3. **Ejercicio 3**: Actualiza el porcentaje de descuento de una promoción específica en la tabla `Promotions`.
4. **Ejercicio 4**: Borra una promoción de la tabla `Promotions` cuyo `id` coincida con un valor dado.

---

### **Módulo 3: Consultas Básicas con SELECT**

1. **Ejercicio 1**: Selecciona todos los datos de la tabla `Customer`.
2. **Ejercicio 2**: Muestra solo el `FirstName` y `LastName` de los clientes que viven en "Paris".
3. **Ejercicio 3**: Realiza una consulta para obtener los álbumes en la tabla `Album` cuyo `Title` contenga la palabra "Rock".
4. **Ejercicio 4**: Ordena los resultados de `Invoice` por `InvoiceDate`, de la más reciente a la más antigua.

---

### **Módulo 4: Funciones Agregadas y Agrupación de Datos**

1. **Ejercicio 1**: Obtén el número total de clientes en la tabla `Customer`.
2. **Ejercicio 2**: Calcula el precio promedio de las canciones en la tabla `Track`.
3. **Ejercicio 3**: Agrupa las canciones por `Genre` y muestra el número de canciones en cada género.
4. **Ejercicio 4**: Usando `HAVING`, muestra los géneros que tienen más de 20 canciones en la tabla `Track`.

---

### **Módulo 5: Consultas Complejas y Subconsultas**

1. **Ejercicio 1**: Encuentra los álbumes cuyo `Price` sea superior al precio promedio de todos los álbumes (usa una subconsulta en el `WHERE`).
2. **Ejercicio 2**: Lista todos los clientes que han realizado compras (facturas) y muestra sus nombres y el total de facturas que han pagado.
3. **Ejercicio 3**: Muestra las canciones que tienen el precio más alto dentro de cada género usando una subconsulta en el `FROM`.
4. **Ejercicio 4**: Encuentra las canciones en `Track` que no están en ninguna lista de reproducción (usa `NOT IN` con `PlaylistTrack`).

---

### **Módulo 6: Uniones de Tablas (JOINS)**

1. **Ejercicio 1**: Realiza un `INNER JOIN` entre `Invoice` e `InvoiceLine` para listar cada factura junto con los detalles de las canciones compradas.
2. **Ejercicio 2**: Usa un `LEFT JOIN` para mostrar todos los clientes y, si aplica, los pedidos asociados. Incluye a los clientes que no han realizado pedidos.
3. **Ejercicio 3**: Haz un `RIGHT JOIN` entre `Employee` y `Customer` para ver todos los empleados y los clientes que han atendido.
4. **Ejercicio 4**: Realiza un `FULL JOIN` entre `Playlist` y `PlaylistTrack` para listar todas las listas de reproducción y las canciones asociadas, incluyendo listas sin canciones.

---

### **Módulo 7: Vistas y Procedimientos Almacenados**

1. **Ejercicio 1**: Crea una vista llamada `TopSellingTracks` que muestre solo las canciones de la tabla `Track` que se han vendido más de 100 veces.
2. **Ejercicio 2**: Crea una vista que contenga el total de ventas por cliente usando las tablas `Invoice` y `Customer`.
3. **Ejercicio 3**: Modifica la vista para que solo incluya clientes con ventas superiores a $100.
4. **Ejercicio 4**: Elimina una de las vistas creadas y vuelve a crearla, esta vez con un filtro para mostrar solo las ventas de un país específico.

---

### **Módulo 8: Administración Avanzada de Bases de Datos**

1. **Ejercicio 1**: Crea un usuario ficticio en SQLite y otórgale permisos para realizar `SELECT` en la tabla `Track`.
2. **Ejercicio 2**: Usa `REVOKE` para retirar los permisos de modificación en la tabla `Invoice` a ese usuario.
3. **Ejercicio 3**: Realiza un backup de la base de datos y luego simula una pérdida de datos eliminando algunas filas de la tabla `InvoiceLine`. Restaura el backup para verificar que puedes recuperar los datos.
4. **Ejercicio 4**: Crea una tabla de auditoría para registrar cambios realizados en la tabla `Customer` (inserciones, actualizaciones y eliminaciones).

---

### **Módulo 9: Optimización de Consultas**

1. **Ejercicio 1**: Usa `EXPLAIN` en una consulta compleja que incluya `JOIN` y filtros en la base de datos y analiza el plan de ejecución.
2. **Ejercicio 2**: Crea un índice en la columna `Title` de la tabla `Album` y observa si mejora el rendimiento de las consultas que filtran por el nombre del álbum.
3. **Ejercicio 3**: Realiza una consulta que incluya un `JOIN` entre `Track` y `InvoiceLine` y compárala con el rendimiento de la misma consulta usando una subconsulta (verifica con `EXPLAIN`).
4. **Ejercicio 4**: Prueba con `DISTINCT` y sin `DISTINCT` en una consulta con múltiples `JOIN` para ver si hay diferencia en el tiempo de ejecución.

---

### **Módulo 10: Proyecto Final**

**Ejercicio**: Diseña un informe final usando la Sample Database. El informe debe incluir:
   - Una vista detallada de cada cliente y su historial de compras (con canciones, álbumes, fechas y montos).
   - Cálculo de ventas totales y promedio por cliente.
   - Listado de canciones menos vendidas.
   - Optimizaciones con índices y verificación de rendimiento con `EXPLAIN`.

---

Estos ejercicios te permitirán profundizar en los conceptos y aplicar SQL en escenarios reales con la estructura de datos de la Sample Database en DBeaver.
