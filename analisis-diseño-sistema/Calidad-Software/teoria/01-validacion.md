# Validación

## Definición

La validación es el proceso mediante el cual se comprueba que el software satisface las necesidades del usuario y cumple con los requisitos para los cuales fue desarrollado.

Su objetivo principal es responder a la pregunta:

> **¿Estamos construyendo el producto correcto?**

La validación se centra en verificar que el sistema realmente resuelve el problema del negocio y cumple las expectativas del cliente.

---

# Importancia

La validación permite:

* Confirmar que el software cumple las necesidades del usuario.
* Detectar diferencias entre lo solicitado y lo implementado.
* Reducir el riesgo de entregar un producto que no aporte valor.
* Incrementar la satisfacción del cliente.

Un sistema puede estar perfectamente programado y aun así fracasar si no resuelve el problema correcto.

---

# ¿Cuándo se realiza?

La validación suele realizarse cuando el sistema ya puede ser utilizado o probado por usuarios.

Puede llevarse a cabo mediante:

* Pruebas de aceptación del usuario (UAT).
* Pruebas funcionales.
* Prototipos.
* Demostraciones.
* Entornos de preproducción.

---

# Actividades de Validación

Algunas actividades comunes son:

* Comprobar que los requisitos funcionales se cumplen.
* Verificar que el comportamiento coincide con las expectativas del usuario.
* Ejecutar escenarios reales de uso.
* Obtener retroalimentación del cliente.
* Confirmar que el sistema aporta la solución esperada.

---

# Explicación Feynman

Imagina que un cliente te pide construir una casa.

Puedes construir una casa perfecta.

Sin errores.

Con excelentes materiales.

Pero…

¿Tiene tres habitaciones como pidió?

¿Tiene garaje?

¿Tiene jardín?

Si no cumple lo que el cliente necesitaba, la casa está bien construida, pero no es la casa correcta.

Eso mismo ocurre con el software.

---

# Ejemplo: Gestor de Turnos

El cliente solicita:

* Reservar citas online.
* Evitar conflictos de horarios.
* Mostrar disponibilidad en tiempo real.

Durante la validación se comprueba que:

* El cliente puede reservar una cita.
* No pueden existir dos citas para el mismo horario.
* La disponibilidad se actualiza correctamente.
* La experiencia de uso satisface al usuario.

Si todo esto ocurre, el sistema ha sido validado correctamente.

---

# Ejemplo de Validación

## Requisito

El sistema debe permitir reservar una cita.

### Escenario

Entrada:

* Cliente registrado.
* Servicio existente.
* Horario disponible.

Resultado esperado:

* La cita se crea correctamente.

Si el usuario puede realizar esta operación y considera que satisface su necesidad, el requisito queda validado.

---

# Relación con el Análisis de Requisitos

Durante el análisis se definieron:

* Problema.
* Objetivos.
* Requisitos funcionales.
* Requisitos no funcionales.

La validación comprueba que todos esos requisitos realmente se cumplen.

---

# Relación con el Desarrollo Backend

En el Gestor de Turnos, la validación consistiría en comprobar que los endpoints implementados permiten realizar correctamente las operaciones solicitadas por el negocio.

Por ejemplo:

* Crear una cita.
* Cancelar una cita.
* Consultar disponibilidad.
* Registrar clientes.

No basta con que los endpoints funcionen técnicamente; también deben resolver las necesidades reales de la barbería.

---

# Diferencia con la Verificación

La validación responde a la pregunta:

> **¿Estamos construyendo el producto correcto?**

La verificación responde a una pregunta diferente:

> **¿Estamos construyendo correctamente el producto?**

Aunque ambos procesos buscan garantizar la calidad del software, tienen objetivos distintos y se complementan durante el desarrollo.
