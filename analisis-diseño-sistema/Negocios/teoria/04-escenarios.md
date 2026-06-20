# Escenarios

## Definición

Un escenario es una secuencia específica de eventos que describe cómo se ejecuta un caso de uso en una situación determinada.

Los escenarios representan ejemplos concretos de interacción entre un actor y el sistema.

Un mismo caso de uso puede tener múltiples escenarios dependiendo de las condiciones que se presenten durante su ejecución.

---

## Importancia

Los escenarios permiten:

* Comprender mejor el comportamiento del sistema.
* Identificar situaciones normales y excepcionales.
* Detectar requisitos faltantes.
* Facilitar la validación de casos de uso.
* Servir como base para pruebas de software.

---

## Relación con los Casos de Uso

Un caso de uso describe una funcionalidad general.

Un escenario describe una ejecución específica de esa funcionalidad.

Ejemplo:

### Caso de Uso

Reservar Turno.

### Escenarios

* Reserva exitosa.
* Horario ocupado.
* Cliente no registrado.
* Servicio inexistente.

---

## Tipos de Escenarios

### Escenario Principal

Describe el flujo normal o esperado.

Ejemplo:

El cliente reserva una cita correctamente.

---

### Escenario Alternativo

Describe una variación válida del flujo principal.

Ejemplo:

El cliente selecciona un horario diferente al inicialmente previsto.

---

### Escenario de Excepción

Describe una situación de error o condición inesperada.

Ejemplo:

El horario ya se encuentra ocupado.

---

## Explicación Feynman

Un caso de uso es como una película.

Un escenario es una escena específica de esa película.

La película completa muestra la funcionalidad.

Cada escena muestra una situación concreta que puede ocurrir.

---

## Ejemplo: Gestor de Turnos

### Caso de Uso

Reservar Turno.

---

### Escenario Principal

1. El cliente consulta horarios disponibles.
2. Selecciona un horario.
3. El sistema valida la disponibilidad.
4. El sistema registra la cita.
5. El sistema confirma la reserva.

Resultado:

* Cita registrada correctamente.

---

### Escenario Alternativo

1. El cliente consulta horarios.
2. Selecciona un horario.
3. El horario ya no está disponible.
4. El sistema muestra horarios alternativos.
5. El cliente selecciona otro horario.
6. El sistema registra la cita.

Resultado:

* Cita registrada correctamente.

---

### Escenario de Excepción

1. El cliente intenta reservar una cita.
2. El servicio seleccionado no existe.
3. El sistema muestra un mensaje de error.

Resultado:

* La cita no puede registrarse.

---

## Relación con las Pruebas

Los escenarios suelen convertirse en casos de prueba.

Ejemplo:

Escenario:

* Horario ocupado.

Caso de prueba:

* Verificar que el sistema impida registrar dos citas en el mismo horario.

---

## Diferencia entre Caso de Uso y Escenario

### Caso de Uso

Describe una funcionalidad.

Ejemplo:

* Reservar Turno.

### Escenario

Describe una situación concreta dentro de esa funcionalidad.

Ejemplo:

* Reserva exitosa.
* Horario ocupado.
* Servicio inexistente.

Un caso de uso puede contener múltiples escenarios.
