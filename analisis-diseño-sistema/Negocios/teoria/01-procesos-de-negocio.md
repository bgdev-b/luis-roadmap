# Procesos de Negocio

## Definición

Un proceso de negocio es un conjunto ordenado de actividades realizadas por personas, departamentos o sistemas con el propósito de alcanzar un objetivo específico dentro de una organización.

Los procesos transforman entradas en salidas que generan valor para el negocio y sus clientes.

El modelado del negocio se inserta en el contexto de la iteración de los flujos de trabajo,
básicamente en el de la implementación pruebas y despliegue, que se consideran flujos
fundamentales en el desarrollo de software. Uno de los flujos es el modelado de negocios,
que se aplica cuando no se ha obtenido del cliente una descripción detallada de los
requisitos del sistema que se desarrollará.

---

## Importancia

El modelado de procesos de negocio permite:

* Comprender cómo funciona una organización.
* Identificar actividades y participantes.
* Detectar problemas e ineficiencias.
* Descubrir oportunidades de mejora.
* Definir correctamente los requisitos del software.

Antes de construir un sistema, es necesario comprender los procesos del negocio que dicho sistema apoyará.

---

## Elementos de un Proceso de Negocio

Según el modelado de negocios, un proceso suele definir:

### Objetivo

La razón por la que existe el proceso.

### Entradas

Información o recursos necesarios para iniciar el proceso.

### Salidas

Resultados obtenidos al finalizar el proceso.

### Recursos

Elementos consumidos durante la ejecución.

### Actividades

Tareas realizadas para alcanzar el objetivo.

### Eventos

Situaciones que inician o modifican el proceso.

### Participantes

Personas, departamentos o sistemas involucrados.

---

## Explicación Feynman

Un proceso de negocio es como una receta.

Tiene un objetivo final, necesita ingredientes, sigue una serie de pasos y produce un resultado.

Si eliminamos o alteramos algunos pasos, el resultado puede cambiar o dejar de obtenerse.

---

## Identificación de Procesos

Para identificar un proceso de negocio se debe:

1. Observar cómo funciona la organización.
2. Identificar las actividades que generan valor.
3. Detectar quién participa.
4. Determinar entradas y salidas.
5. Documentar la secuencia de actividades.

Es importante no confundir módulos del sistema con procesos de negocio.

Por ejemplo:

- Catálogo de Productos. (No.)

- Atender Solicitud de Compra.

El primero es una funcionalidad.

El segundo es un proceso de negocio.

---

## Ejemplo: Gestor de Turnos

### Nombre del Proceso

Reserva de Turno.

### Objetivo

Asignar una cita a un cliente sin generar conflictos de horario.

### Entradas

* Cliente.
* Servicio solicitado.
* Fecha.
* Hora.

### Participantes

* Cliente.
* Empleado.
* Sistema.

### Actividades

1. Consultar horarios disponibles.
2. Seleccionar servicio.
3. Validar disponibilidad.
4. Registrar turno.
5. Confirmar reserva.

### Salidas

* Turno registrado.
* Confirmación de reserva.

### Evento de Inicio

El cliente solicita una cita.

---

## Relación con el Desarrollo de Software

Los procesos de negocio sirven como base para:

* Requisitos funcionales.
* Casos de uso.
* Diagramas UML.
* Reglas de negocio.

Por esta razón, comprender los procesos de negocio es uno de los primeros pasos antes de diseñar un sistema.
