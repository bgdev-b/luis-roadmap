# Arquitectura Monolítica

## Definición

La arquitectura monolítica es un estilo de arquitectura de software en el que toda la aplicación se desarrolla, ejecuta y despliega como una única unidad.

Todos los componentes del sistema, como la interfaz, la lógica de negocio y el acceso a datos, forman parte de una misma aplicación y comparten el mismo proceso de ejecución.

---

## Importancia

La arquitectura monolítica permite:

* Desarrollar aplicaciones de forma sencilla.
* Facilitar el despliegue en proyectos pequeños y medianos.
* Simplificar las pruebas iniciales.
* Reducir la complejidad de la infraestructura.

Es una arquitectura ampliamente utilizada en aplicaciones que aún no requieren una gran escalabilidad.

---

## Características

Una aplicación monolítica se caracteriza por:

* Un único proyecto o aplicación.
* Un único proceso de ejecución.
* Un único despliegue.
* Comunicación interna mediante llamadas directas entre módulos.
* Generalmente una única base de datos compartida.

---

## Explicación Feynman

Imagina una navaja suiza.

Tiene cuchillo, tijeras, destornillador y abrebotellas.

Todas las herramientas están integradas en un solo objeto.

Si necesitas cambiar una herramienta, normalmente debes reemplazar toda la navaja.

Una aplicación monolítica funciona de manera similar: todas sus funcionalidades forman parte de una única aplicación.

---

## Ejemplo: Gestor de Turnos

El Gestor de Turnos puede implementarse como una aplicación monolítica.

Todos los módulos se encuentran dentro del mismo proyecto:

```text
GestorTurnos/

├── clients/
├── users/
├── services/
├── appointments/
├── controllers/
├── repositories/
├── database/
└── app
```

Todos los módulos comparten la misma aplicación y la misma base de datos.

---

## Funcionamiento

Cliente

↓

Aplicación Monolítica

* Clientes
* Usuarios
* Servicios
* Citas

↓

Base de Datos

Cuando un usuario solicita una cita, la aplicación procesa toda la lógica internamente sin necesidad de comunicarse con otros servicios.

---

## Ventajas

* Desarrollo más sencillo.
* Despliegue simple.
* Comunicación interna rápida.
* Menor complejidad de infraestructura.
* Fácil depuración durante las primeras etapas del proyecto.

---

## Desventajas

* A medida que crece, el código puede volverse difícil de mantener.
* Un cambio requiere desplegar toda la aplicación.
* Escalar una sola funcionalidad implica escalar toda la aplicación.
* Un fallo importante puede afectar al sistema completo.

---

## ¿Cuándo utilizar una Arquitectura Monolítica?

Es una buena opción cuando:

* El proyecto es pequeño o mediano.
* El equipo de desarrollo es reducido.
* El dominio del negocio no es muy complejo.
* Se desea desarrollar un MVP (Producto Mínimo Viable) rápidamente.

---

## Relación con el Gestor de Turnos

Actualmente, el Gestor de Turnos puede implementarse como un monolito.

Todos los módulos:

* Clients
* Users
* Services
* Appointments

forman parte de la misma aplicación, comparten la misma base de datos y se despliegan conjuntamente.

---

## Relación con los Microservicios

La arquitectura monolítica y la arquitectura de microservicios buscan resolver problemas diferentes.

Un monolito concentra todas las funcionalidades en una única aplicación.

Los microservicios dividen el sistema en múltiples servicios independientes que se comunican entre sí.

Muchos proyectos comienzan como monolitos y evolucionan hacia microservicios cuando aumentan su tamaño, complejidad o necesidades de escalabilidad.

---

## Relación con el Desarrollo Backend

El Appointment Manager desarrollado en Node.js es un ejemplo de arquitectura monolítica.

Aunque internamente utiliza:

* Arquitectura en capas.
* Modularidad.
* Principios SOLID.

Toda la aplicación se ejecuta y despliega como una única unidad.
