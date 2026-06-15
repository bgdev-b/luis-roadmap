# Actores

## Definición

Identificar actores es uno de los primeros pasos en el análisis de casos de uso.

Cada tipo de entidad externa con la que el sistema debe interactuar está representada por un actor.

Un actor especifica un rol desempeñado por un usuario, dispositivo, sistema externo u otra entidad que interactúa con el sistema.

Los actores son externos al sistema y participan intercambiando información, solicitudes o respuestas.

---

## Características de los Actores

* Representan roles, no personas específicas.
* Pueden ser usuarios humanos, dispositivos o sistemas externos.
* Una misma persona puede desempeñar varios actores.
* Un mismo actor puede ser representado por múltiples personas.
* Siempre son externos al sistema.

---

## Tipos de Actores

### Usuarios

Personas que interactúan directamente con el sistema.

**Ejemplos:**

* Cliente
* Empleado
* Administrador

---

### Sistemas Externos

Aplicaciones o servicios que intercambian información con el sistema.

**Ejemplos:**

* Sistema de pagos
* Servicio de correo electrónico
* API externa

---

### Bases de Datos

Repositorios externos utilizados para almacenar o consultar información.

---

### Dispositivos

Equipos físicos que interactúan con el sistema.

**Ejemplos:**

* Impresora
* Escáner
* Terminal de pago

---

### Plataformas y Servicios en la Nube

Infraestructuras o servicios externos utilizados por el sistema.

**Ejemplos:**

* AWS
* Azure
* Google Cloud

---

## Explicación Feynman

Los actores son los participantes de la historia del sistema.

Si el sistema fuera una película, los actores serían todos los personajes que interactúan con él.

Lo importante es recordar que los actores están fuera del sistema.

El sistema responde a las acciones de los actores o intercambia información con ellos.

---

## Ejemplo: Gestor de Turnos

### Cliente

Objetivos:

* Consultar horarios.
* Reservar turnos.
* Cancelar turnos.

---

### Empleado

Objetivos:

* Gestionar agenda.
* Confirmar citas.
* Registrar servicios.

---

### Administrador

Objetivos:

* Gestionar usuarios.
* Configurar servicios.
* Consultar reportes.

---

### Servicio de Correo Electrónico

Objetivos:

* Enviar confirmaciones.
* Enviar recordatorios.

---

## Relación con Casos de Uso

Los actores permiten identificar las funcionalidades que debe ofrecer el sistema.

Ejemplo:

Cliente:

* Reservar turno.
* Cancelar turno.
* Consultar disponibilidad.

Empleado:

* Gestionar agenda.
* Confirmar citas.

Estas funcionalidades serán modeladas posteriormente mediante casos de uso UML.

---

## Diferencia entre Actor y Usuario

### Usuario

Persona que utiliza el sistema.

### Actor

Rol o entidad que interactúa con el sistema.

Todo usuario es un actor, pero no todo actor es una persona.

Un actor también puede ser:

* Un sistema externo.
* Un dispositivo.
* Una base de datos.
* Un servicio en la nube.
