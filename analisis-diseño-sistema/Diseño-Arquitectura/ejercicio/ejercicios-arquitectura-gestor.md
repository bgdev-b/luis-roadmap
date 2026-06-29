# Ejercicio Integrador: Diseño de Arquitectura del Gestor de Turnos

## Objetivo

Diseñar la arquitectura del Gestor de Turnos aplicando los conceptos de Cliente-Servidor, Arquitectura Monolítica, Microservicios, APIs e Integraciones.

---

# Arquitectura Cliente-Servidor

El sistema seguirá una arquitectura Cliente-Servidor.

## Cliente

El cliente será una aplicación web utilizada por:

- Clientes.
- Empleados.
- Administradores.

Sus responsabilidades son:

- Mostrar la interfaz.
- Capturar acciones del usuario.
- Enviar solicitudes HTTP.
- Mostrar las respuestas del servidor.

---

## Servidor

El servidor será una API REST desarrollada en ASP.NET Core (o Node.js).

Sus responsabilidades son:

- Validar las solicitudes.
- Aplicar la lógica del negocio.
- Acceder a la base de datos.
- Devolver respuestas al cliente.

---

## Base de Datos

La información será almacenada en PostgreSQL.

Las principales tablas son:

- Clients
- Users
- Services
- Appointments

---

# Arquitectura Monolítica

La primera versión del sistema será un monolito.

Toda la aplicación se desplegará como una única unidad.

```text
GestorTurnos/

├── clients/
├── users/
├── services/
├── appointments/
├── controllers/
├── services/
├── repositories/
├── database/
└── Program.cs
```

Todos los módulos compartirán:

- La misma aplicación.
- La misma base de datos.
- El mismo despliegue.

Esta arquitectura es adecuada para una barbería con una única sucursal.

---

# Evolución hacia Microservicios

Si el negocio creciera considerablemente, el sistema podría dividirse en microservicios.

Por ejemplo:

```text
Client Service

Appointment Service

Service Catalog

Notification Service

Payment Service
```

Cada servicio sería responsable únicamente de una capacidad del negocio.

Cada uno podría desplegarse y escalarse de forma independiente.

---

# APIs

La comunicación entre el cliente y el servidor se realizará mediante una API REST.

## Endpoints

### Clientes

```http
GET    /clients
GET    /clients/{id}
POST   /clients
PUT    /clients/{id}
DELETE /clients/{id}
```

### Servicios

```http
GET    /services
POST   /services
```

### Citas

```http
GET    /appointments
GET    /appointments/{id}
POST   /appointments
PATCH  /appointments/{id}
DELETE /appointments/{id}
```

Todas las respuestas utilizarán JSON.

---

# Integraciones

Aunque la primera versión del sistema será sencilla, la arquitectura permitirá integrar servicios externos.

## WhatsApp Business API

Cuando una cita sea creada:

Gestor de Turnos

↓

WhatsApp API

↓

Mensaje de confirmación.

---

## Google Calendar

Cada cita creada podrá sincronizarse automáticamente con Google Calendar.

---

## Stripe

Los pagos online podrán procesarse mediante Stripe.

Después de un pago exitoso:

Stripe

↓

Webhook

↓

Gestor de Turnos

↓

Actualizar estado de la cita.

---

## Servicio de Correo

Después de reservar una cita:

Gestor de Turnos

↓

Email Service

↓

Correo de confirmación.

---

# Arquitectura General

```text
                    Cliente

                        │

                   HTTP / JSON

                        │

                API REST (Servidor)

                        │

      ┌─────────────────┼─────────────────┐

      │                 │                 │

  Clients         Appointments        Services

      │                 │                 │

      └─────────────────┼─────────────────┘

                        │

                  PostgreSQL

                        │

        ┌───────────────┼────────────────┐

        │               │                │

   WhatsApp API      Stripe      Google Calendar
```

---

# Justificación de la Arquitectura

Se eligió una arquitectura Cliente-Servidor porque separa claramente la interfaz del usuario de la lógica del negocio.

La aplicación se implementará inicialmente como un monolito debido a su menor complejidad y facilidad de despliegue.

Las APIs REST permitirán la comunicación entre el frontend y el backend mediante HTTP y JSON.

Finalmente, el sistema queda preparado para futuras integraciones con plataformas externas como WhatsApp, Stripe y Google Calendar, así como para evolucionar hacia una arquitectura basada en microservicios si el crecimiento del negocio lo requiere.

---

# Conclusión

El Gestor de Turnos ha sido diseñado utilizando una arquitectura moderna y escalable.

La solución combina:

- Arquitectura Cliente-Servidor.
- Arquitectura Monolítica.
- API REST.
- Integraciones con servicios externos.

Además, el diseño permite evolucionar hacia una arquitectura de microservicios sin necesidad de rediseñar completamente el sistema, facilitando el crecimiento futuro de la aplicación.