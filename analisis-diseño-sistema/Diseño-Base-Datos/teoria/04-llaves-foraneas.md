# Llaves Foráneas (Foreign Keys)

## Definición

Una llave foránea (Foreign Key) es una columna o conjunto de columnas de una tabla que hace referencia a la llave primaria (Primary Key) de otra tabla.

Su objetivo es establecer relaciones entre tablas y garantizar la integridad referencial de la base de datos.

---

## Importancia

Las llaves foráneas permiten:

* Relacionar tablas entre sí.
* Evitar referencias a registros inexistentes.
* Garantizar la integridad de los datos.
* Mantener la consistencia de la información.
* Facilitar consultas mediante JOIN.

---

## ¿Cómo funcionan?

Una llave foránea almacena el identificador de un registro existente en otra tabla.

Por ejemplo:

Tabla:

clients

| id | nombre |
| -- | ------ |
| 1  | Bryant |
| 2  | Luis   |

Tabla:

appointments

| id | fecha | client_id |
| -- | ----- | --------- |
| 1  | 10/07 | 1         |

El valor `client_id = 1` hace referencia al cliente cuyo `id` también vale `1`.

---

## Integridad Referencial

La integridad referencial garantiza que una relación entre tablas siempre sea válida.

Por ejemplo, si un turno pertenece a un cliente, ese cliente debe existir.

La base de datos impedirá:

* Crear una cita para un cliente inexistente.
* Crear referencias inválidas.
* Romper las relaciones entre tablas.

---

## Explicación Feynman

Imagina una biblioteca.

Cada préstamo tiene escrito el número del libro que fue prestado.

Ese número debe corresponder a un libro que realmente exista.

No tendría sentido registrar un préstamo del libro número **500** si solo existen **100** libros.

La llave foránea funciona exactamente igual.

Solo permite hacer referencia a registros que ya existen.

---

## Ejemplo: Gestor de Turnos

### Tabla: clients

| id | nombre |
| -- | ------ |
| 1  | Bryant |

---

### Tabla: services

| id | nombre        |
| -- | ------------- |
| 3  | Corte Clásico |

---

### Tabla: appointments

| id | fecha | client_id | service_id |
| -- | ----- | --------- | ---------- |
| 8  | 15/07 | 1         | 3          |

En este ejemplo:

* `client_id` referencia a `clients.id`.
* `service_id` referencia a `services.id`.

---

## Relación entre Primary Key y Foreign Key

Primary Key

↓

Identifica un registro.

Foreign Key

↓

Hace referencia a ese registro desde otra tabla.

Una llave primaria identifica.

Una llave foránea relaciona.

---

## Relación con SQL

Ejemplo:

```sql
CREATE TABLE appointments (

    id UUID PRIMARY KEY,

    client_id UUID,

    service_id UUID,

    FOREIGN KEY (client_id)
        REFERENCES clients(id),

    FOREIGN KEY (service_id)
        REFERENCES services(id)

);
```

Con esta restricción la base de datos solo permitirá registrar citas asociadas a clientes y servicios existentes.

---

## ¿Qué ocurre si se rompe una relación?

Supongamos:

clients

| id |
| -- |
| 5  |

appointments

| client_id |
| --------- |
| 5         |

Si alguien intenta eliminar el cliente con `id = 5`, la base de datos puede aplicar distintas reglas:

* RESTRICT → Impide eliminar el registro.
* CASCADE → Elimina automáticamente las citas relacionadas.
* SET NULL → Establece el valor de la llave foránea en NULL.

La regla utilizada depende del diseño del sistema.

---

## Relación con el Modelo Relacional

Las llaves foráneas implementan físicamente las relaciones definidas durante el modelado de datos.

Modelo ER

Cliente

↓

Reserva

↓

Cita

Modelo Relacional

clients

↓

client_id

↓

appointments

La relación conceptual del modelo ER se convierte en una llave foránea dentro de la base de datos.

---

## Relación con el Desarrollo Backend

En aplicaciones backend, las llaves foráneas permiten relacionar entidades del dominio.

Ejemplo:

Client

↓

Appointment

↓

Service

Cuando un usuario crea una cita, el sistema guarda únicamente los identificadores (`client_id` y `service_id`), mientras que la base de datos garantiza que ambos registros existan antes de aceptar la operación.
