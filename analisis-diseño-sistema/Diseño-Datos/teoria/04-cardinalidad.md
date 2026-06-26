# Cardinalidad

## Definición

La cardinalidad describe la cantidad de instancias de una entidad que pueden relacionarse con instancias de otra entidad.

Permite definir las reglas numéricas de una relación y constituye uno de los elementos fundamentales del Modelo Entidad-Relación (ER).

La cardinalidad ayuda a representar correctamente la realidad del negocio y facilita el diseño posterior de bases de datos.

---

## Importancia

La cardinalidad permite:

* Comprender cómo se relacionan las entidades.
* Diseñar correctamente bases de datos.
* Evitar redundancia de información.
* Definir restricciones del negocio.
* Construir modelos ER precisos.

---

## Tipos de Cardinalidad

### Uno a Uno (1:1)

Cada instancia de una entidad se relaciona con una única instancia de la otra entidad.

Ejemplo:

Empleado ↔ Carnet de Identidad

Un empleado posee un único carnet y cada carnet pertenece a un único empleado.

---

### Uno a Muchos (1:N)

Una instancia de una entidad puede relacionarse con múltiples instancias de la otra entidad.

Ejemplo:

Departamento → Empleado

Un departamento tiene muchos empleados.

Cada empleado pertenece a un único departamento.

---

### Muchos a Muchos (N:M)

Varias instancias de una entidad pueden relacionarse con múltiples instancias de otra entidad.

Ejemplo:

Estudiante ↔ Asignatura

Un estudiante puede cursar varias asignaturas.

Una asignatura puede ser cursada por muchos estudiantes.

En bases de datos relacionales este tipo de relación suele resolverse mediante una tabla intermedia.

---

## Explicación Feynman

Las relaciones indican que dos entidades están conectadas.

La cardinalidad responde una pregunta adicional:

¿Cuántas veces pueden conectarse?

Por ejemplo:

Cliente → Cita

La relación es:

"El cliente reserva citas."

La cardinalidad responde:

"¿Cuántas citas puede reservar un cliente?"

---

## Ejemplo: Gestor de Turnos

### Cliente y Cita

Cardinalidad:

1:N

Un cliente puede tener muchas citas.

Cada cita pertenece a un único cliente.

---

### Servicio y Cita

Cardinalidad:

1:N

Un servicio puede aparecer en muchas citas.

Cada cita corresponde a un único servicio.

---

### Usuario y Cita

Cardinalidad:

1:N

Un usuario puede gestionar múltiples citas.

Cada cita es gestionada por un usuario específico.

---

## Representación Conceptual

Cliente (1) -------- (N) Cita

Servicio (1) ------- (N) Cita

Usuario (1) -------- (N) Cita

---

## Relación con el Modelo Entidad-Relación

La cardinalidad complementa las relaciones dentro del Modelo ER.

Relación:

Cliente reserva Cita.

Cardinalidad:

Cliente (1) -------- (N) Cita

La relación indica el vínculo.

La cardinalidad indica cuántas instancias participan en dicho vínculo.
