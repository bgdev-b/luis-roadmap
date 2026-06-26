# Entidades

## Definición

Una entidad es un elemento, objeto o concepto identificable sobre el cual una organización necesita almacenar información.

Las entidades representan elementos del mundo real que son relevantes para el negocio y constituyen la base del modelado de datos.

Cada entidad posee atributos que describen sus características y puede relacionarse con otras entidades dentro del sistema.

---

## Importancia

Las entidades permiten:

* Representar elementos importantes del negocio.
* Organizar la información de manera estructurada.
* Diseñar bases de datos correctamente.
* Modelar relaciones entre objetos del mundo real.

Identificar correctamente las entidades es uno de los primeros pasos en el diseño de datos.

---

## Características

Las entidades:

* Representan objetos, personas, lugares, eventos o conceptos.
* Poseen atributos propios.
* Pueden relacionarse con otras entidades.
* Deben tener identidad propia dentro del sistema.

---

## Explicación Feynman

Una entidad es cualquier "cosa" importante sobre la que necesitamos guardar información.

Por ejemplo, en una universidad:

* Estudiante.
* Profesor.
* Asignatura.

No son acciones ni procesos.

Son elementos que existen y sobre los cuales queremos almacenar datos.

---

## Ejemplos Generales

### Biblioteca

Entidades:

* Libro.
* Usuario.
* Préstamo.

---

### Tienda Online

Entidades:

* Cliente.
* Producto.
* Pedido.

---

### Hospital

Entidades:

* Paciente.
* Médico.
* Consulta.

---

## Ejemplo: Gestor de Turnos

Las principales entidades del sistema son:

### Cliente

Representa a la persona que solicita una cita.

### Servicio

Representa el servicio ofrecido por el negocio.

### Cita

Representa una reserva realizada por un cliente.

### Usuario

Representa a los empleados o administradores que utilizan el sistema.

---

## Relación con el Diseño de Bases de Datos

Las entidades suelen transformarse posteriormente en tablas.

Ejemplo:

Entidad:

* Cliente

↓

Tabla:

* clients

Entidad:

* Cita

↓

Tabla:

* appointments

Por esta razón las entidades constituyen el punto de partida para el diseño de bases de datos.

---

## Preguntas de Reflexión

* ¿Qué elementos del negocio necesitan almacenarse?
* ¿Qué información debo conservar sobre ellos?
* ¿Tienen identidad propia dentro del sistema?
* ¿Se relacionan con otras entidades?
