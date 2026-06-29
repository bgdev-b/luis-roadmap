# Arquitectura de Microservicios

## Definición

La arquitectura de microservicios es un estilo arquitectónico que divide una aplicación en pequeños servicios independientes.

Cada microservicio implementa una capacidad específica del negocio, posee su propia lógica y puede desarrollarse, desplegarse y escalarse de manera independiente.

Los microservicios se comunican entre sí mediante mecanismos ligeros, generalmente APIs HTTP o sistemas de mensajería.

---

## Importancia

La arquitectura de microservicios permite:

* Dividir aplicaciones grandes en servicios pequeños.
* Escalar cada servicio de forma independiente.
* Desplegar nuevas funcionalidades sin afectar a toda la aplicación.
* Facilitar el trabajo de múltiples equipos.
* Incrementar la resiliencia del sistema.

---

## Características

Un sistema basado en microservicios se caracteriza por:

* Servicios independientes.
* Responsabilidad única por servicio.
* Despliegue independiente.
* Comunicación mediante APIs.
* Bajo acoplamiento.
* Alta cohesión.

Cada servicio representa una capacidad concreta del negocio.

---

## Explicación Feynman

Imagina un centro comercial.

En lugar de una única tienda enorme que vende de todo, existen muchas tiendas especializadas:

* Barbería.
* Farmacia.
* Restaurante.
* Librería.

Cada una funciona de manera independiente.

Si una tienda cierra temporalmente, las demás continúan funcionando.

Los microservicios siguen la misma idea.

Cada servicio realiza una única función del negocio.

---

## Ejemplo: Gestor de Turnos

En lugar de una única aplicación:

GestorTurnos

↓

Clients

↓

Appointments

↓

Services

↓

Users

Podemos dividir el sistema en varios microservicios.

---

## Arquitectura

Cliente

↓

API Gateway

↓

Client Service

Appointment Service

Service Catalog

Notification Service

↓

Base de Datos de Clientes

Base de Datos de Citas

Base de Datos de Servicios

Cada servicio posee su propia lógica y, normalmente, su propia base de datos.

---

## Ventajas

* Escalabilidad independiente.
* Mayor resiliencia.
* Despliegues independientes.
* Equipos de desarrollo autónomos.
* Posibilidad de utilizar tecnologías distintas en cada servicio.

---

## Desventajas

* Mayor complejidad de desarrollo.
* Mayor complejidad de despliegue.
* Comunicación distribuida.
* Observabilidad y monitoreo más complejos.
* Consistencia de datos más difícil de gestionar.

---

## ¿Cuándo utilizar Microservicios?

Son recomendables cuando:

* El sistema es muy grande.
* Existen múltiples equipos de desarrollo.
* Se requiere escalar partes específicas de la aplicación.
* El negocio evoluciona constantemente.

Para proyectos pequeños o medianos, un monolito bien diseñado suele ser una mejor opción.

---

## Comparación con un Monolito

### Monolito

Una única aplicación.

Un único despliegue.

Una única base de datos.

---

### Microservicios

Múltiples aplicaciones.

Cada servicio puede desplegarse de forma independiente.

Cada servicio puede tener su propia base de datos.

---

## Ejemplo de Evolución

Versión inicial:

Gestor de Turnos

↓

Una única API

↓

PostgreSQL

Cuando el negocio crece:

Cliente

↓

API Gateway

↓

Client Service

↓

Appointment Service

↓

Notification Service

↓

Payment Service

Cada servicio puede evolucionar sin afectar al resto del sistema.

---

## Relación con el Desarrollo Backend

La mayoría de proyectos comienzan como monolitos.

Cuando el sistema crece y aparecen nuevas necesidades de escalabilidad, resiliencia o independencia entre equipos, puede evolucionar hacia una arquitectura basada en microservicios.

Los microservicios no sustituyen al modelo cliente-servidor; representan una forma diferente de organizar el servidor.
