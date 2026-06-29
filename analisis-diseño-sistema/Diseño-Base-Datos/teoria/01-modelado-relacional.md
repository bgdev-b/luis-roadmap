# Modelado Relacional

## Definición

El modelado relacional es una técnica utilizada para organizar y representar los datos de una base de datos mediante relaciones, las cuales se implementan como tablas.

Cada tabla representa una entidad del negocio y está compuesta por filas (registros o tuplas) y columnas (atributos). Las relaciones entre tablas se establecen mediante llaves primarias y llaves foráneas.

---

## Importancia

El modelo relacional permite:

* Organizar los datos de forma estructurada.
* Reducir la redundancia de información.
* Garantizar la integridad de los datos.
* Facilitar las consultas mediante SQL.
* Representar correctamente las relaciones del negocio.

Actualmente es el modelo más utilizado para el diseño e implementación de bases de datos.

---

## Componentes Principales

### Tabla (Relación)

Representa una entidad del negocio.

Ejemplos:

* clients
* services
* appointments
* users

---

### Fila (Tupla o Registro)

Representa una instancia de la entidad.

Ejemplo:

Cliente

| id | nombre | telefono     |
| -- | ------ | ------------ |
| 1  | Bryant | 809-555-1234 |

---

### Columna (Atributo)

Representa una característica de la entidad.

Ejemplo:

Cliente

* id
* nombre
* telefono
* email

---

## Explicación Feynman

Imagina una hoja de Excel.

Cada hoja representa un tipo de información.

Una hoja puede contener clientes.

Otra servicios.

Otra citas.

Cada fila representa un elemento diferente y cada columna almacena una característica de ese elemento.

Las hojas pueden conectarse entre sí mediante identificadores comunes.

Eso es precisamente una base de datos relacional.

---

## Del Modelo ER al Modelo Relacional

Modelo Entidad-Relación:

Cliente

↓

Modelo Relacional:

Tabla:

clients

---

Entidad:

Servicio

↓

Tabla:

services

---

Entidad:

Cita

↓

Tabla:

appointments

Cada entidad del modelo ER suele transformarse en una tabla del modelo relacional.

---

## Ejemplo: Gestor de Turnos

### Tabla: clients

| id | nombre | telefono | email |
| -- | ------ | -------- | ----- |

---

### Tabla: services

| id | nombre | precio | duracion |
| -- | ------ | ------ | -------- |

---

### Tabla: appointments

| id | fecha | hora | estado | client_id | service_id |
| -- | ----- | ---- | ------ | --------- | ---------- |

---

### Tabla: users

| id | nombre | email | rol |
| -- | ------ | ----- | --- |

---

## Relación con SQL

El modelo relacional se implementa utilizando sistemas gestores de bases de datos relacionales (RDBMS) como:

* PostgreSQL
* MySQL
* SQL Server
* SQLite

En estos sistemas, las relaciones se representan mediante tablas y se consultan utilizando SQL.

---

## Relación con el Diseño de Datos

En la sección anterior se identificaron:

* Entidades.
* Atributos.
* Relaciones.
* Cardinalidades.
* Modelo ER.

El modelado relacional toma ese diseño conceptual y lo transforma en una estructura de tablas lista para ser implementada en una base de datos.
