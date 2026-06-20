# Reglas de Negocio

## Definición

Las reglas de negocio son políticas, restricciones, condiciones o decisiones que gobiernan el funcionamiento de una organización.

Estas reglas determinan qué acciones pueden realizarse, bajo qué condiciones deben ejecutarse y cuáles son los resultados esperados.

Las reglas de negocio existen independientemente del software y reflejan la forma en que opera el negocio en el mundo real.

---

## Importancia

Las reglas de negocio permiten:

* Estandarizar la toma de decisiones.
* Garantizar que los procesos produzcan resultados correctos.
* Mantener la coherencia de las operaciones.
* Reducir errores e inconsistencias.
* Servir como base para la automatización de procesos.

---

## Características

Las reglas de negocio:

* Son independientes de la tecnología utilizada.
* Reflejan políticas y decisiones organizacionales.
* Controlan el comportamiento de los procesos.
* Pueden cambiar cuando cambian las políticas del negocio.
* Deben ser claras y verificables.

---

## Estructura General

Muchas reglas de negocio pueden expresarse mediante una lógica condicional:

```text
SI ocurre una condición
ENTONCES debe ejecutarse una acción
```

Ejemplo:

```text
SI un cliente cancela una cita
ENTONCES el horario queda disponible nuevamente.
```

IBM destaca que muchas reglas pueden formalizarse mediante estructuras del tipo IF-THEN para facilitar su automatización.

---

## Explicación Feynman

Las reglas de negocio son las reglas del juego.

Si un negocio fuera un partido de fútbol, las reglas indicarían:

* Qué acciones están permitidas.
* Qué acciones están prohibidas.
* Qué ocurre cuando sucede una situación específica.

El software simplemente hace cumplir esas reglas.

---

## Ejemplos Generales

### Banco

* Una transferencia no puede superar el saldo disponible.
* Solo el titular puede autorizar determinadas operaciones.

### Biblioteca

* Un usuario no puede tener más de tres préstamos activos.

### Universidad

* Un estudiante debe aprobar los prerrequisitos antes de inscribir una asignatura.

---

## Ejemplo: Gestor de Turnos

### Reglas de Negocio

* Un horario solo puede estar reservado por un cliente a la vez.
* Una cita debe estar asociada a un cliente registrado.
* Un servicio debe existir antes de ser reservado.
* Una cita cancelada libera automáticamente el horario.
* No pueden existir dos citas activas para el mismo horario.
* Solo los empleados autorizados pueden modificar citas.

---

## Diferencia entre Regla de Negocio y Restricción

### Regla de Negocio

Describe cómo funciona la organización.

Ejemplo:

* Un horario solo puede estar reservado por un cliente.

La regla seguiría existiendo aunque las citas se gestionaran con papel y lápiz.

### Restricción

Describe una limitación del proyecto o sistema.

Ejemplo:

* El sistema debe desarrollarse utilizando Node.js.

La organización puede seguir funcionando aunque cambie la tecnología utilizada.

---

## Relación con el Desarrollo de Software

Las reglas de negocio influyen directamente en:

* Procesos de negocio.
* Casos de uso.
* Requisitos funcionales.
* Validaciones del sistema.
* Lógica de negocio.

Por esta razón, gran parte del trabajo del analista consiste en descubrir, documentar y validar las reglas que gobiernan el negocio antes de diseñar el software.
