# Modelado del Negocio del Gestor de Turnos

## 1. Proceso de Negocio

### Nombre

Reserva de Turno.

### Objetivo

Permitir que un cliente reserve una cita disponible sin generar conflictos de horario.

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
3. Seleccionar horario.
4. Validar disponibilidad.
5. Registrar cita.
6. Confirmar reserva.

### Salidas

* Cita registrada.
* Confirmación enviada al cliente.

---

## 2. Reglas de Negocio

* Un horario solo puede estar asociado a una cita activa.
* Toda cita debe pertenecer a un cliente registrado.
* Un servicio debe existir antes de ser reservado.
* Una cancelación libera automáticamente el horario.
* Solo los empleados autorizados pueden modificar citas.
* No pueden existir dos citas activas para el mismo horario.

---

## 3. Casos de Uso

### Cliente

* Reservar Turno.
* Consultar Horarios.
* Cancelar Turno.
* Reprogramar Turno.

### Empleado

* Consultar Agenda.
* Confirmar Cita.
* Registrar Servicio Realizado.

### Administrador

* Gestionar Usuarios.
* Gestionar Servicios.
* Consultar Reportes.

---

## 4. Escenarios

### Caso de Uso: Reservar Turno

#### Escenario Principal

1. El cliente consulta horarios disponibles.
2. Selecciona un horario.
3. El sistema valida disponibilidad.
4. El sistema registra la cita.
5. El sistema confirma la reserva.

Resultado:

* Reserva exitosa.

---

#### Escenario Alternativo

1. El cliente selecciona un horario ocupado.
2. El sistema muestra horarios alternativos.
3. El cliente selecciona otro horario.
4. El sistema registra la cita.

Resultado:

* Reserva exitosa utilizando otro horario.

---

#### Escenario de Excepción

1. El cliente intenta reservar un servicio inexistente.
2. El sistema detecta el error.
3. El sistema muestra un mensaje informativo.

Resultado:

* La reserva no puede completarse.

---

## 5. Flujo de Trabajo

### Reserva de Turno

Inicio

↓

Cliente consulta horarios disponibles.

↓

Selecciona servicio y horario.

↓

Sistema valida disponibilidad.

↓

¿Horario disponible?

├── Sí
│
├── Registrar cita.
│
├── Confirmar reserva.
│
└── Fin.

└── No
│
├── Mostrar horarios alternativos.
│
├── Cliente selecciona nuevo horario.
│
└── Volver a validar disponibilidad.

---

## Conclusión

El Gestor de Turnos modela un proceso de negocio orientado a la gestión eficiente de citas.

Las reglas de negocio garantizan la integridad de las reservas, los casos de uso representan las funcionalidades disponibles para cada actor, los escenarios describen situaciones concretas de ejecución y el flujo de trabajo muestra la secuencia completa de actividades necesarias para completar una reserva.
