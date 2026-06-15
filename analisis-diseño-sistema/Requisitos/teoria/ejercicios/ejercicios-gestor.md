# Ejercicio Integrador: Análisis de Requisitos del Gestor de Turnos

## 1. Identificación del Problema

### Situación Actual

Los clientes solicitan citas manualmente mediante mensajes o llamadas.

### Problema

Se producen conflictos de horarios y dificultades para gestionar las reservas.

### Impacto

* Pérdida de tiempo.
* Mala experiencia para los clientes.
* Errores administrativos.
* Menor productividad.

### Causa Raíz

No existe un mecanismo centralizado para validar y gestionar las citas.

### Afectados

* Clientes.
* Empleados.
* Administradores del negocio.

---

## 2. Objetivos del Sistema

### Objetivo General

Desarrollar un sistema que permita gestionar clientes, servicios y turnos de manera organizada y eficiente.

### Objetivos Específicos

* Registrar clientes.
* Registrar servicios.
* Permitir reservas.
* Evitar conflictos de horarios.
* Gestionar cancelaciones.
* Gestionar reprogramaciones.
* Consultar historiales.

---

## 3. Actores

### Cliente

Objetivos:

* Consultar horarios.
* Reservar turnos.
* Cancelar turnos.
* Reprogramar turnos.

### Empleado

Objetivos:

* Consultar agenda.
* Gestionar citas.
* Confirmar servicios realizados.

### Administrador

Objetivos:

* Gestionar usuarios.
* Gestionar servicios.
* Consultar reportes.

---

## 4. Requisitos Funcionales

* El sistema debe permitir registrar clientes.
* El sistema debe permitir registrar servicios.
* El sistema debe permitir reservar turnos.
* El sistema debe permitir cancelar turnos.
* El sistema debe permitir reprogramar turnos.
* El sistema debe impedir reservas duplicadas.
* El sistema debe consultar historiales de citas.
* El sistema debe gestionar usuarios.

---

## 5. Requisitos No Funcionales

* El sistema debe responder en menos de 2 segundos.
* El sistema debe almacenar datos de forma segura.
* El sistema debe ser fácil de utilizar.
* El sistema debe soportar múltiples usuarios concurrentes.
* El sistema debe mantener la integridad de los datos.

---

## 6. Restricciones

### Técnicas

* Backend desarrollado con Node.js y Express.
* Base de datos relacional.

### Económicas

* Utilizar herramientas gratuitas durante la fase inicial.

### Organizacionales

* Solo empleados autorizados pueden gestionar citas.

### Temporales

* La primera versión debe estar disponible dentro del cronograma definido.

---

## 7. Reglas de Negocio

* Un horario solo puede estar asociado a una cita activa.
* Un servicio debe existir antes de ser reservado.
* Toda cita debe pertenecer a un cliente registrado.
* Una cancelación libera automáticamente el horario.
* No pueden existir dos citas activas en el mismo horario.
