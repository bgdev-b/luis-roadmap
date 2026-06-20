# Casos de Uso

## Definición

Los casos de uso son descripciones de las tareas que los actores pueden realizar mediante el sistema para alcanzar un objetivo específico.

Se utilizan para refinar y organizar los requisitos funcionales a partir de roles o tareas concretas.

Un caso de uso representa una interacción entre un actor y el sistema.

---

## Importancia

Los casos de uso permiten:

* Organizar los requisitos funcionales.
* Comprender las necesidades de los usuarios.
* Facilitar la comunicación entre clientes y desarrolladores.
* Servir como base para diagramas UML.
* Definir el comportamiento esperado del sistema.

Los casos de uso ayudan a transformar necesidades de negocio en funcionalidades concretas del sistema.

---

## Relación con Procesos de Negocio

Un proceso de negocio describe:

**Cómo se realiza una actividad dentro de la organización.**

Un caso de uso describe:

**Qué hace un actor dentro del sistema para cumplir una tarea.**

Ejemplo:

### Proceso de Negocio

Gestión de Citas.

### Casos de Uso Relacionados

* Reservar Turno.
* Cancelar Turno.
* Reprogramar Turno.
* Consultar Agenda.

---

## Elementos de un Caso de Uso

### Nombre

Debe describir una tarea utilizando un verbo.

Ejemplos:

* Reservar Turno.
* Consultar Horarios.
* Cancelar Cita.

---

### Actor

Entidad que interactúa con el sistema.

Ejemplos:

* Cliente.
* Empleado.
* Administrador.

---

### Objetivo

Resultado que desea obtener el actor.

---

### Flujo Principal

Secuencia normal de interacción entre actor y sistema.

---

### Flujos Alternativos

Situaciones excepcionales o caminos alternativos.

---

## Explicación Feynman

Un caso de uso es una pequeña historia.

La historia cuenta:

* Quién participa.
* Qué quiere lograr.
* Qué pasos realiza.
* Qué responde el sistema.

Cada historia representa una funcionalidad del sistema desde el punto de vista del usuario.

---

## Ejemplo: Gestor de Turnos

### Caso de Uso: Reservar Turno

**Actor:**

* Cliente.

**Objetivo:**

* Obtener una cita.

**Flujo Principal:**

1. El cliente consulta horarios disponibles.
2. El cliente selecciona un horario.
3. El sistema verifica disponibilidad.
4. El sistema registra la reserva.
5. El sistema confirma la cita.

**Flujo Alternativo:**

1. El horario ya está ocupado.
2. El sistema informa el conflicto.
3. El sistema muestra alternativas.

---

## Identificación de Casos de Uso

Para identificar casos de uso:

1. Identificar actores.
2. Identificar objetivos de cada actor.
3. Identificar tareas realizadas para alcanzar esos objetivos.
4. Asociar cada tarea importante con un caso de uso.

---

## Relación con UML

Los casos de uso son la base de los Diagramas de Casos de Uso UML.

Actor:

* Cliente.

Casos de Uso:

* Reservar Turno.
* Cancelar Turno.
* Consultar Horarios.

Posteriormente estos elementos se representarán gráficamente mediante UML.
