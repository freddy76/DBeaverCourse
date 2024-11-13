Te presento una versión mejorada del curso, esta vez enfocada en PostgreSQL. A continuación, incluyo el esquema de una base de datos de ejemplo y los scripts SQL para crear y poblar las tablas. Este curso sigue una estructura similar a la versión anterior pero aprovecha las características de PostgreSQL, como tipos de datos avanzados, transacciones, y funciones de ventana.

---

## **Curso Completo de Bases de Datos con PostgreSQL**

### Base de Datos de Ejemplo: "MusicStore"

La base de datos **MusicStore** contiene información sobre artistas, álbumes, clientes, facturas y canciones, similar a la base de datos en DBeaver pero con optimizaciones específicas para PostgreSQL.

---

### Esquema de la Base de Datos

**Tablas:**
1. **Artist**: Información de cada artista.
2. **Album**: Álbumes de música de los artistas.
3. **Track**: Canciones de los álbumes.
4. **Genre**: Géneros musicales.
5. **Customer**: Información de los clientes.
6. **Invoice**: Facturas de las compras realizadas por clientes.
7. **InvoiceLine**: Detalle de cada factura, con canciones compradas.

### Script de Creación y Población

A continuación, el script SQL para crear el esquema y poblar las tablas con datos de muestra.

```sql
-- Creación de la base de datos
CREATE DATABASE MusicStore;
\c MusicStore;

-- Creación de tablas

CREATE TABLE Artist (
    ArtistID SERIAL PRIMARY KEY,
    Name VARCHAR(100) NOT NULL
);

CREATE TABLE Album (
    AlbumID SERIAL PRIMARY KEY,
    Title VARCHAR(100) NOT NULL,
    ArtistID INT REFERENCES Artist(ArtistID)
);

CREATE TABLE Genre (
    GenreID SERIAL PRIMARY KEY,
    Name VARCHAR(50) NOT NULL
);

CREATE TABLE Track (
    TrackID SERIAL PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    AlbumID INT REFERENCES Album(AlbumID),
    GenreID INT REFERENCES Genre(GenreID),
    Milliseconds INT NOT NULL,
    UnitPrice DECIMAL(5, 2) NOT NULL
);

CREATE TABLE Customer (
    CustomerID SERIAL PRIMARY KEY,
    FirstName VARCHAR(40) NOT NULL,
    LastName VARCHAR(40) NOT NULL,
    Email VARCHAR(100),
    Country VARCHAR(40)
);

CREATE TABLE Invoice (
    InvoiceID SERIAL PRIMARY KEY,
    CustomerID INT REFERENCES Customer(CustomerID),
    InvoiceDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    Total DECIMAL(10, 2) NOT NULL
);

CREATE TABLE InvoiceLine (
    InvoiceLineID SERIAL PRIMARY KEY,
    InvoiceID INT REFERENCES Invoice(InvoiceID),
    TrackID INT REFERENCES Track(TrackID),
    Quantity INT NOT NULL,
    UnitPrice DECIMAL(5, 2) NOT NULL
);

-- Insertando datos de ejemplo

INSERT INTO Artist (Name) VALUES ('The Beatles'), ('Led Zeppelin'), ('Queen');
INSERT INTO Album (Title, ArtistID) VALUES ('Abbey Road', 1), ('Led Zeppelin IV', 2), ('A Night at the Opera', 3);
INSERT INTO Genre (Name) VALUES ('Rock'), ('Pop'), ('Jazz');
INSERT INTO Track (Name, AlbumID, GenreID, Milliseconds, UnitPrice) VALUES
    ('Come Together', 1, 1, 259200, 1.29),
    ('Stairway to Heaven', 2, 1, 480000, 1.29),
    ('Bohemian Rhapsody', 3, 1, 354000, 1.49);
INSERT INTO Customer (FirstName, LastName, Email, Country) VALUES 
    ('John', 'Doe', 'johndoe@example.com', 'USA'),
    ('Jane', 'Smith', 'janesmith@example.com', 'Canada');
INSERT INTO Invoice (CustomerID, Total) VALUES (1, 2.58), (2, 1.49);
INSERT INTO InvoiceLine (InvoiceID, TrackID, Quantity, UnitPrice) VALUES 
    (1, 1, 1, 1.29), (1, 2, 1, 1.29), (2, 3, 1, 1.49);
```

---

## Contenido del Curso y Ejercicios

### **Módulo 1: Introducción a PostgreSQL y PGAdmin**

1. **Ejercicio 1**: Conecta a la base de datos **MusicStore** en PostgreSQL y explora la estructura de las tablas.
2. **Ejercicio 2**: Describe las relaciones entre `Album` y `Artist` y entre `InvoiceLine` y `Invoice`. Identifica el tipo de relación que representan.

---

### **Módulo 2: Conceptos Básicos de SQL**

1. **Ejercicio 1**: Crea una nueva tabla `Promotion` con las columnas `id`, `description`, `discount_percent`, y `start_date`.
2. **Ejercicio 2**: Inserta tres promociones ficticias en la tabla `Promotion`.
3. **Ejercicio 3**: Actualiza el porcentaje de descuento de una promoción específica.
4. **Ejercicio 4**: Elimina una promoción cuyo `id` coincida con un valor específico.

---

### **Módulo 3: Consultas Básicas con SELECT**

1. **Ejercicio 1**: Selecciona todos los datos de la tabla `Customer`.
2. **Ejercicio 2**: Muestra solo el `FirstName` y `LastName` de los clientes en el país "Canada".
3. **Ejercicio 3**: Filtra los álbumes cuyo `Title` contenga la palabra "Rock".
4. **Ejercicio 4**: Ordena los resultados de `Invoice` por `InvoiceDate` de más reciente a más antigua.

---

### **Módulo 4: Funciones Agregadas y Agrupación de Datos**

1. **Ejercicio 1**: Obtén el número total de clientes en `Customer`.
2. **Ejercicio 2**: Calcula el precio promedio de las canciones en `Track`.
3. **Ejercicio 3**: Agrupa las canciones por `Genre` y muestra el número de canciones en cada género.
4. **Ejercicio 4**: Usa `HAVING` para mostrar géneros que tengan más de 1 canción.

---

### **Módulo 5: Consultas Complejas y Subconsultas**

1. **Ejercicio 1**: Encuentra los álbumes cuyo `UnitPrice` es mayor al precio promedio de todos los álbumes.
2. **Ejercicio 2**: Lista todos los clientes que han realizado compras, mostrando el total de facturas pagadas.
3. **Ejercicio 3**: Muestra las canciones con el precio más alto dentro de cada género.
4. **Ejercicio 4**: Encuentra canciones en `Track` que no estén en ninguna factura.

---

### **Módulo 6: Uniones de Tablas (JOINS)**

1. **Ejercicio 1**: Realiza un `INNER JOIN` entre `Invoice` e `InvoiceLine` para listar cada factura junto con los detalles de las canciones compradas.
2. **Ejercicio 2**: Usa un `LEFT JOIN` para mostrar todos los clientes y los pedidos asociados.
3. **Ejercicio 3**: Haz un `RIGHT JOIN` entre `Customer` y `Invoice` para ver todos los clientes y los pedidos.
4. **Ejercicio 4**: Realiza un `FULL JOIN` entre `Track` y `InvoiceLine` para listar todas las canciones y los detalles de las compras.

---

### **Módulo 7: Vistas y Procedimientos Almacenados**

1. **Ejercicio 1**: Crea una vista `TopSellingTracks` que muestre solo las canciones que se han vendido más de 2 veces.
2. **Ejercicio 2**: Crea una vista que contenga el total de ventas por cliente.
3. **Ejercicio 3**: Modifica la vista para incluir solo clientes con ventas superiores a $3.
4. **Ejercicio 4**: Elimina y vuelve a crear la vista con un filtro específico para un país.

---

### **Módulo 8: Administración Avanzada de Bases de Datos**

1. **Ejercicio 1**: Crea un usuario ficticio en PostgreSQL y otórgale permisos para realizar `SELECT` en la tabla `Track`.
2. **Ejercicio 2**: Usa `REVOKE` para retirar permisos de modificación en la tabla `Invoice`.
3. **Ejercicio 3**: Realiza un backup de la base de datos y elimina datos de `InvoiceLine`. Restaura el backup para verificar.
4. **Ejercicio 4**: Crea una tabla de auditoría para registrar cambios en `Customer`.

---

### **Módulo 9: Optimización de Consultas**

1. **Ejercicio 1**: Usa `EXPLAIN` en una consulta compleja para analizar el plan de ejecución.
2. **Ejercicio 2**: Crea un índice en `Name` de `Artist` y observa mejoras en rendimiento.
3. **Ejercicio 3**: Realiza una consulta con `JOIN` entre `Track` e `InvoiceLine`, usando `EXPLAIN`.
4. **Ejercicio 4**: Compara consultas con y sin `DISTINCT`.

---

### **Módulo 10: Proyecto Final**

**Ejercicio**: Diseña un informe final sobre la **MusicStore** que incluya:
   - Historial detallado de compras por cliente.
   - Cálculo de ventas

 totales y promedio por cliente.
   - Listado de canciones menos vendidas.
   - Optimizaciones con índices y verificación de rendimiento con `EXPLAIN`.

---

Estos ejercicios aplican conceptos avanzados y prácticas de PostgreSQL en una base de datos realista para una comprensión más profunda.
