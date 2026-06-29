# Ejercicio Integrador: Diseño de Base de Datos del Gestor de Turnos

## Objetivo

Diseñar la base de datos del sistema Gestor de Turnos aplicando los conceptos de modelado relacional, normalización, llaves primarias, llaves foráneas e índices.

---

# Modelo Relacional

La base de datos está compuesta por cuatro entidades principales:

* Clients
* Users
* Services
* Appointments

## Clients

| Columna    | Tipo    |
| ---------- | ------- |
| id         | UUID    |
| first_name | VARCHAR |
| last_name  | VARCHAR |
| email      | VARCHAR |
| phone      | VARCHAR |

---

## Users

| Columna    | Tipo    |
| ---------- | ------- |
| id         | UUID    |
| first_name | VARCHAR |
| last_name  | VARCHAR |
| email      | VARCHAR |
| role       | VARCHAR |

---

## Services

| Columna  | Tipo    |
| -------- | ------- |
| id       | UUID    |
| name     | VARCHAR |
| duration | INTEGER |
| price    | DECIMAL |

---

## Appointments

| Columna          | Tipo    |
| ---------------- | ------- |
| id               | UUID    |
| appointment_date | DATE    |
| appointment_time | TIME    |
| status           | VARCHAR |
| client_id        | UUID    |
| service_id       | UUID    |
| user_id          | UUID    |

---

# Normalización

Inicialmente la información podía almacenarse de la siguiente forma:

| Cliente | Teléfono | Servicio | Precio | Fecha | Hora |
| ------- | -------- | -------- | ------ | ----- | ---- |

Este diseño presenta varios problemas:

* Duplicación de información.
* Dificultad para actualizar datos.
* Inconsistencias.
* Baja escalabilidad.

Aplicando la normalización, la información se divide en las tablas:

* Clients
* Services
* Users
* Appointments

Cada dato se almacena una sola vez y las relaciones se realizan mediante identificadores.

---

# Llaves Primarias

Cada tabla posee una llave primaria de tipo UUID.

| Tabla        | Primary Key |
| ------------ | ----------- |
| Clients      | id          |
| Users        | id          |
| Services     | id          |
| Appointments | id          |

Los UUID permiten identificar cada registro de forma única y facilitan futuras integraciones entre sistemas.

---

# Llaves Foráneas

Las relaciones entre tablas son las siguientes:

Appointments

* client_id → Clients(id)
* service_id → Services(id)
* user_id → Users(id)

Estas llaves foráneas garantizan la integridad referencial del sistema.

---

# Índices

Se crearán índices sobre las columnas más consultadas.

| Tabla        | Columna          | Motivo                      |
| ------------ | ---------------- | --------------------------- |
| Clients      | email            | Búsqueda e inicio de sesión |
| Clients      | phone            | Localizar clientes          |
| Services     | name             | Buscar servicios            |
| Appointments | appointment_date | Agenda diaria               |
| Appointments | status           | Filtrar citas               |
| Appointments | client_id        | Historial del cliente       |
| Appointments | user_id          | Agenda de empleados         |

---

# Integridad Referencial

Si un cliente posee citas registradas, el sistema utilizará la política **RESTRICT**.

De esta forma se evita eliminar clientes que aún poseen información histórica asociada.

---

# Relaciones

Clients (1)

↓

Appointments (N)

Services (1)

↓

Appointments (N)

Users (1)

↓

Appointments (N)

---

# Modelo Final

```text
clients
──────────────
id (PK)
first_name
last_name
email
phone

        │
        │
        ▼

appointments
────────────────────
id (PK)
appointment_date
appointment_time
status

client_id (FK)
service_id (FK)
user_id (FK)

       ▲
       │
       │

services
────────────
id (PK)
name
price
duration

       ▲
       │
       │

users
────────────
id (PK)
first_name
last_name
email
role
```

---

# Conclusión

La base de datos del Gestor de Turnos sigue el modelo relacional, se encuentra normalizada para evitar redundancias, utiliza llaves primarias para identificar de forma única cada entidad, llaves foráneas para establecer relaciones e índices para optimizar las consultas más frecuentes. Este diseño proporciona una estructura consistente, escalable y preparada para el desarrollo de la aplicación.
