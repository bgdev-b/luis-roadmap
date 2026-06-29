# Casos de Prueba

## Definición

Un caso de prueba (Test Case) es un conjunto de condiciones, datos de entrada, pasos de ejecución y resultados esperados que permiten verificar que una funcionalidad del software se comporta correctamente.

Los casos de prueba ayudan a comprobar que el sistema cumple los requisitos definidos y facilitan la detección temprana de errores.

---

# Importancia

Los casos de prueba permiten:

* Verificar el cumplimiento de los requisitos.
* Detectar defectos antes de que el software llegue a producción.
* Facilitar las pruebas manuales y automatizadas.
* Reducir regresiones al modificar el sistema.
* Documentar el comportamiento esperado del software.

---

# Componentes de un Caso de Prueba

Un caso de prueba suele contener la siguiente información:

* **ID:** Identificador único.
* **Nombre:** Descripción breve de la prueba.
* **Objetivo:** Qué funcionalidad se desea verificar.
* **Precondiciones:** Estado necesario antes de ejecutar la prueba.
* **Datos de entrada:** Información que utilizará la prueba.
* **Pasos:** Acciones que deben realizarse.
* **Resultado esperado:** Comportamiento correcto del sistema.
* **Resultado obtenido:** Resultado real (al ejecutar la prueba).
* **Estado:** Aprobado (Pass) o Fallido (Fail).

---

# Explicación Feynman

Imagina que un chef crea una nueva receta.

Antes de abrir el restaurante, prueba la receta varias veces siguiendo siempre los mismos pasos.

Cada prueba responde preguntas como:

* ¿Se utilizaron los ingredientes correctos?
* ¿El tiempo de cocción fue el adecuado?
* ¿El resultado fue el esperado?

En software ocurre lo mismo.

Un caso de prueba define exactamente cómo comprobar que una funcionalidad funciona correctamente.

---

# Estructura General

| Campo              | Descripción                              |
| ------------------ | ---------------------------------------- |
| ID                 | Identificador del caso de prueba         |
| Nombre             | Funcionalidad que se evaluará            |
| Objetivo           | Qué se desea comprobar                   |
| Precondiciones     | Estado previo necesario                  |
| Datos de Entrada   | Información utilizada durante la prueba  |
| Pasos              | Acciones a realizar                      |
| Resultado Esperado | Comportamiento esperado                  |
| Resultado Obtenido | Resultado obtenido al ejecutar la prueba |
| Estado             | Pass o Fail                              |

---

# Ejemplo: Gestor de Turnos

## Caso de Prueba 001

**Nombre**

Crear una cita correctamente.

**Objetivo**

Verificar que un cliente pueda reservar una cita cuando el horario está disponible.

**Precondiciones**

* Cliente registrado.
* Servicio existente.
* Horario libre.

**Datos de Entrada**

* Cliente: Bryant.
* Servicio: Corte.
* Fecha: 20/07/2026.
* Hora: 10:00.

**Pasos**

1. Acceder al formulario de citas.
2. Seleccionar el servicio.
3. Elegir fecha y hora.
4. Confirmar la reserva.

**Resultado Esperado**

* La cita se registra correctamente.
* El estado inicial es "Pendiente".
* Se devuelve un código HTTP 201.

---

# Caso de Prueba 002

**Nombre**

Intentar reservar un horario ocupado.

**Objetivo**

Comprobar que el sistema impida reservar una cita en un horario ya ocupado.

**Resultado Esperado**

* La cita no se crea.
* Se muestra un mensaje indicando que el horario no está disponible.
* La API devuelve un código HTTP 409 (Conflict).

---

# Caso de Prueba 003

**Nombre**

Cancelar una cita.

**Resultado Esperado**

* El estado cambia a "Cancelada".
* La base de datos se actualiza correctamente.
* La API devuelve HTTP 200.

---

# Tipos de Casos de Prueba

Existen distintos tipos de casos de prueba según el objetivo que persigan.

## Casos Positivos

Comprueban que el sistema funciona correctamente cuando recibe datos válidos.

Ejemplo:

Reservar una cita con toda la información correcta.

---

## Casos Negativos

Comprueban que el sistema maneja adecuadamente entradas inválidas o situaciones inesperadas.

Ejemplo:

Reservar una cita sin seleccionar una fecha.

---

## Casos de Límite

Evalúan valores extremos o situaciones cercanas a los límites permitidos.

Ejemplo:

Reservar la última cita disponible del día.

---

## Casos de Regresión

Verifican que una modificación reciente no haya afectado funcionalidades que ya funcionaban correctamente.

Ejemplo:

Después de agregar la opción de reprogramar citas, comprobar que la cancelación sigue funcionando.

---

# Buenas Prácticas

Un buen caso de prueba debe ser:

* Claro y fácil de entender.
* Repetible.
* Independiente de otros casos.
* Basado en requisitos.
* Fácil de automatizar cuando sea posible.

Cada caso debe verificar una única funcionalidad o comportamiento específico.

---

# Relación con la Verificación

Los casos de prueba son una de las principales herramientas utilizadas durante la verificación del software.

Permiten comprobar que la implementación cumple con las especificaciones definidas durante el análisis y el diseño.

---

# Relación con el Desarrollo Backend

En el Gestor de Turnos, los casos de prueba pueden implementarse mediante pruebas automatizadas utilizando herramientas como Vitest y Supertest.

Por ejemplo:

* Crear una cita.
* Cancelar una cita.
* Reprogramar una cita.
* Consultar disponibilidad.
* Validar errores cuando un horario ya está ocupado.

Estos casos permiten verificar continuamente que la API funciona como se espera.

---

# Conclusión

Los casos de prueba constituyen una parte fundamental del aseguramiento de la calidad del software.

Definen de forma estructurada cómo comprobar el comportamiento esperado del sistema y permiten detectar errores antes de que el software llegue a los usuarios finales.
