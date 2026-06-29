# Llaves Primarias (Primary Keys)

## Definición

Una llave primaria (Primary Key) es un atributo o conjunto de atributos que identifica de manera única cada registro de una tabla.

Ningún valor de la llave primaria puede repetirse ni ser nulo.

La llave primaria permite diferenciar un registro de todos los demás dentro de la misma tabla.

---

## Importancia

Las llaves primarias permiten:

* Identificar cada registro de forma única.
* Evitar registros duplicados.
* Establecer relaciones entre tablas.
* Garantizar la integridad de los datos.
* Facilitar las búsquedas y consultas.

Toda tabla debería poseer una llave primaria.

---

## Características

Una llave primaria debe cumplir las siguientes propiedades:

* Ser única.
* No aceptar valores nulos (NULL).
* Permanecer estable durante la vida del registro.
* Identificar un único registro de la tabla.

---

## Explicación Feynman

Imagina un salón de clases.

Puede haber varios estudiantes llamados Juan.

Pero cada estudiante posee un número de matrícula único.

Aunque dos estudiantes tengan el mismo nombre, su matrícula los identifica de manera inequívoca.

La llave primaria cumple exactamente esa función dentro de una base de datos.

---

## Ejemplos

### Tabla: clients

| id | nombre | telefono |
| -- | ------ | -------- |
| 1  | Bryant | 809...   |
| 2  | Luis   | 829...   |

La llave primaria es:

id

Cada cliente posee un identificador diferente.

---

### Tabla: services

| id | nombre | precio |
| -- | ------ | ------ |
| 1  | Corte  | 500    |
| 2  | Barba  | 300    |

La llave primaria vuelve a ser:

id

---

## Ejemplo: Gestor de Turnos

### Clients

Primary Key:

id

---

### Services

Primary Key:

id

---

### Users

Primary Key:

id

---

### Appointments

Primary Key:

id

Cada entidad posee su propio identificador único.

---

## Tipos de Llaves Primarias

### Llave Natural

Proviene de un dato que ya existe en el mundo real.

Ejemplos:

* Número de cédula.
* Pasaporte.
* Número de matrícula.

---

### Llave Artificial (Surrogate Key)

Es creada exclusivamente para identificar registros.

Ejemplos:

* id INT AUTO_INCREMENT
* UUID

En aplicaciones modernas es muy común utilizar identificadores artificiales para evitar depender de datos del negocio.

---

## Relación con SQL

Ejemplo:

```sql
CREATE TABLE clients (
    id UUID PRIMARY KEY,
    nombre VARCHAR(100),
    telefono VARCHAR(20)
);
```

La restricción `PRIMARY KEY` garantiza que el campo `id` sea único y no admita valores nulos.

---

## Relación con las Llaves Foráneas

Las llaves primarias permiten establecer relaciones entre tablas.

Por ejemplo:

clients

↓

id (PRIMARY KEY)

↓

appointments

↓

client_id (FOREIGN KEY)

La llave foránea hace referencia a la llave primaria de otra tabla.

---

## Relación con el Desarrollo Backend

En aplicaciones backend, la llave primaria suele convertirse en el identificador principal de una entidad.

Ejemplo:

Cliente

↓

id

↓

ClientRepository

↓

GET /clients/{id}

PUT /clients/{id}

DELETE /clients/{id}

Las operaciones más comunes de una API utilizan la llave primaria para localizar un recurso específico.
