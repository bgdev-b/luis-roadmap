# Índices

## Definición

Un índice es una estructura de datos utilizada por un sistema gestor de bases de datos para acelerar la búsqueda y recuperación de información.

En lugar de recorrer todas las filas de una tabla, el índice permite localizar los registros de forma mucho más eficiente.

Los índices mejoran el rendimiento de las consultas, aunque también consumen espacio adicional y deben mantenerse cuando los datos cambian.

---

## Importancia

Los índices permiten:

* Acelerar búsquedas.
* Mejorar el rendimiento de las consultas.
* Optimizar operaciones de filtrado.
* Optimizar ordenamientos.
* Mejorar el rendimiento de los JOIN.

Son especialmente útiles en tablas con una gran cantidad de registros.

---

## ¿Cómo funcionan?

Sin índice:

La base de datos revisa cada fila hasta encontrar el dato solicitado.

Con índice:

La base de datos utiliza una estructura auxiliar para localizar rápidamente la ubicación del registro.

---

## Explicación Feynman

Imagina un libro de 800 páginas.

Si quieres encontrar el capítulo "Bases de Datos" tienes dos opciones.

### Sin índice

Lees las 800 páginas una por una.

---

### Con índice

Vas directamente al índice del libro.

Buscas:

Bases de Datos → Página 542

Y llegas inmediatamente a la información.

Los índices de una base de datos funcionan exactamente igual.

---

## Ejemplo

Supongamos una tabla:

clients

| id | nombre | email |
| -- | ------ | ----- |

Si buscamos:

```sql
SELECT *
FROM clients
WHERE email = 'bryant@mail.com';
```

Sin un índice, el motor puede tener que revisar todos los registros.

Con un índice sobre la columna `email`, la búsqueda será mucho más rápida.

---

## Creación de un Índice

Ejemplo:

```sql
CREATE INDEX idx_clients_email
ON clients(email);
```

A partir de ese momento, las consultas que utilicen la columna `email` podrán aprovechar el índice.

---

## Ventajas

* Consultas más rápidas.
* Mejor rendimiento en búsquedas.
* Mayor eficiencia en filtros.
* Mejor rendimiento en operaciones JOIN.
* Mejor rendimiento en ORDER BY.

---

## Desventajas

Los índices también tienen un costo.

* Ocupan espacio adicional.
* Hacen más lentas las inserciones.
* Hacen más lentas las actualizaciones.
* Hacen más lentas las eliminaciones.

Cada vez que cambian los datos, el índice también debe actualizarse.

---

## Ejemplo: Gestor de Turnos

Tablas:

clients

appointments

services

users

Podrían existir índices sobre:

appointments

* fecha
* client_id
* service_id

clients

* email

Estos índices permitirían localizar información mucho más rápido.

---

## Relación con Primary Keys

Las llaves primarias suelen tener un índice creado automáticamente por el sistema gestor de bases de datos.

Esto permite localizar registros mediante su identificador de forma muy eficiente.

---

## Relación con Foreign Keys

En muchas aplicaciones también resulta recomendable crear índices sobre las llaves foráneas.

Esto mejora el rendimiento de consultas que relacionan tablas mediante JOIN.

---

## ¿Cuándo crear un índice?

Es recomendable cuando una columna:

* Se utiliza frecuentemente en búsquedas.
* Se utiliza en cláusulas WHERE.
* Participa en JOIN.
* Se utiliza en ORDER BY.
* Se utiliza en GROUP BY.

No todas las columnas necesitan un índice.

Crear índices innecesarios puede reducir el rendimiento de escritura.

---

## Relación con el Desarrollo Backend

En aplicaciones backend, las consultas más frecuentes suelen realizarse mediante identificadores o campos de búsqueda.

Ejemplos:

* Buscar un cliente por email.
* Obtener las citas de un cliente.
* Consultar citas por fecha.
* Buscar un servicio por nombre.

Un buen diseño de índices permite que estas consultas sean rápidas incluso cuando la base de datos contiene millones de registros.

## Tipos de Índices

Existen distintos tipos de índices, cada uno diseñado para optimizar diferentes escenarios de consulta.

### Índice Primario (Primary Index)

Se crea automáticamente al definir una llave primaria (`PRIMARY KEY`).

Garantiza la unicidad de los registros y permite localizar cada fila de forma eficiente.

**Ejemplo:**

```sql
CREATE TABLE clients (
    id UUID PRIMARY KEY,
    nombre VARCHAR(100),
    email VARCHAR(100)
);
```

En este caso, el motor de la base de datos crea automáticamente un índice sobre la columna `id`, permitiendo localizar rápidamente un cliente por su identificador.

---

### Índice Agrupado (Clustered Index)

Organiza físicamente los datos de la tabla siguiendo el orden del índice.

Como los datos solo pueden almacenarse físicamente en un único orden, una tabla solo puede tener un índice agrupado.

Este tipo de índice es especialmente eficiente para consultas por rangos.

**Ejemplo:**

Supongamos una tabla de citas ordenada por fecha:

| fecha      | cliente |
| ---------- | ------- |
| 2026-07-20 | Bryant  |
| 2026-07-21 | Luis    |
| 2026-07-22 | Ana     |

Si un usuario consulta todas las citas entre el 20 y el 22 de julio, la base de datos podrá recorrer los registros de forma secuencial y muy eficiente.

---

### Índice No Agrupado (Non-Clustered Index)

Es una estructura independiente de la tabla.

Almacena los valores indexados junto con una referencia hacia la ubicación real de cada registro.

Una tabla puede tener múltiples índices no agrupados.

**Ejemplo:**

```sql
CREATE INDEX idx_clients_email
ON clients(email);
```

Cuando un usuario inicia sesión utilizando su correo electrónico, el motor utiliza este índice para localizar rápidamente el registro correspondiente sin recorrer toda la tabla.

---

### Índice Compuesto (Composite Index)

Se construye utilizando dos o más columnas.

Es útil cuando las consultas filtran información utilizando varias columnas al mismo tiempo.

**Ejemplo:**

```sql
CREATE INDEX idx_appointments_date_status
ON appointments(fecha, estado);
```

Consulta optimizada:

```sql
SELECT *
FROM appointments
WHERE fecha = '2026-07-20'
AND estado = 'Confirmada';
```

El índice permite localizar únicamente las citas confirmadas de esa fecha sin revisar todos los registros.

---

### Índice Único (Unique Index)

Garantiza que los valores almacenados en la columna indexada no se repitan.

Se utiliza para atributos que deben ser únicos, como un correo electrónico o un nombre de usuario.

**Ejemplo:**

```sql
CREATE UNIQUE INDEX idx_clients_email
ON clients(email);
```

Ahora la base de datos impedirá insertar dos clientes con el mismo correo electrónico.

Por ejemplo:

```text
✔ bryant@email.com

✘ bryant@email.com
```

El segundo registro será rechazado porque violaría la restricción de unicidad.


## Buenas Prácticas

Al diseñar índices es recomendable:

* Crear índices en columnas utilizadas frecuentemente en `WHERE`, `JOIN` y `ORDER BY`.
* Evitar crear índices innecesarios, ya que incrementan el costo de las operaciones `INSERT`, `UPDATE` y `DELETE`.
* Utilizar índices compuestos cuando las consultas filtren por varias columnas.
* Analizar el uso real de los índices antes de crear nuevos.

Un buen diseño de índices busca equilibrar el rendimiento de lectura con el costo adicional que supone mantener los índices actualizados.

## ¿Cuándo crear un Índice?

Es recomendable crear un índice cuando una columna se utiliza frecuentemente para buscar, filtrar o relacionar información.

### Casos comunes

* Columnas utilizadas en cláusulas `WHERE`.
* Columnas utilizadas en `JOIN`.
* Columnas utilizadas en `ORDER BY`.
* Columnas utilizadas en `GROUP BY`.
* Llaves foráneas (`FOREIGN KEY`).
* Columnas con muchos valores distintos (alta cardinalidad).

**Ejemplos:**

Buscar un cliente por correo electrónico.

```sql
SELECT *
FROM clients
WHERE email = 'bryant@email.com';
```

---

Consultar las citas de un cliente.

```sql
SELECT *
FROM appointments
WHERE client_id = '123';
```

---

Obtener las citas ordenadas por fecha.

```sql
SELECT *
FROM appointments
ORDER BY fecha;
```

En todos estos casos un índice puede mejorar considerablemente el rendimiento de la consulta.

---

## ¿Cuándo NO crear un Índice?

No todas las columnas necesitan un índice.

Crear índices innecesarios consume espacio y hace más lentas las operaciones de escritura (`INSERT`, `UPDATE` y `DELETE`).

Evita crear índices cuando:

* La tabla contiene muy pocos registros.
* La columna casi nunca se utiliza en búsquedas.
* La columna tiene muy pocos valores distintos (por ejemplo: `activo`, `estado`, `sexo`).
* La columna cambia constantemente de valor.
* El índice no aporta mejoras reales al rendimiento.

**Ejemplo:**

Supongamos una tabla:

```text
users

activo

Sí
No
```

Si casi todos los registros contienen únicamente "Sí" o "No", un índice sobre esa columna probablemente no ofrecerá ventajas, ya que el motor de la base de datos preferirá recorrer la tabla completa.

---

## Regla General

Antes de crear un índice, pregúntate:

* ¿Esta columna se consulta frecuentemente?
* ¿La consulta es lenta?
* ¿El índice reducirá realmente el tiempo de búsqueda?
* ¿El beneficio en lectura compensa el costo en escritura?

Un buen diseño de bases de datos busca el equilibrio entre el rendimiento de las consultas y el costo de mantener los índices actualizados.
