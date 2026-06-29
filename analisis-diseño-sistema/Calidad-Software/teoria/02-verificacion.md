# Verificación

## Definición

La verificación es el proceso mediante el cual se comprueba que el software ha sido construido correctamente de acuerdo con los requisitos, especificaciones y diseños definidos durante el desarrollo.

Su objetivo principal es responder a la pregunta:

> **¿Estamos construyendo correctamente el producto?**

Mientras la validación comprueba si el sistema satisface las necesidades del usuario, la verificación comprueba que cada etapa del desarrollo cumple con las especificaciones establecidas.

---

# Importancia

La verificación permite:

* Detectar errores lo antes posible.
* Comprobar que el código cumple las especificaciones.
* Reducir el costo de corregir defectos.
* Aumentar la confiabilidad del software.
* Mejorar la calidad del producto final.

Corregir un error durante el desarrollo suele ser mucho menos costoso que descubrirlo cuando el software ya está en producción.

---

# ¿Cuándo se realiza?

La verificación se lleva a cabo durante todo el ciclo de vida del desarrollo de software (SDLC).

No es una actividad exclusiva de la fase de pruebas.

Se realiza desde que se definen los requisitos hasta que el software es desplegado.

---

# Actividades de Verificación

Algunas actividades comunes son:

* Revisión de requisitos.
* Revisión de diseños.
* Revisiones de código (Code Review).
* Análisis estático.
* Pruebas unitarias.
* Pruebas de integración.
* Pruebas funcionales.

Cada una busca comprobar que el producto se está construyendo correctamente según las especificaciones.

---

# Explicación Feynman

Imagina que estás construyendo un puente.

Antes de permitir que los vehículos lo crucen, revisas:

* Que los planos se hayan seguido correctamente.
* Que los materiales sean los adecuados.
* Que las medidas sean correctas.
* Que la estructura soporte el peso esperado.

Todavía no estás comprobando si el puente conecta las ciudades correctas.

Solo verificas que fue construido conforme al diseño.

Eso es exactamente la verificación en software.

---

# Ejemplo: Gestor de Turnos

Supongamos el siguiente requisito:

> El sistema debe impedir reservar dos citas en el mismo horario.

Durante la verificación se comprueba que:

* La regla de negocio fue implementada.
* La validación de disponibilidad funciona correctamente.
* El código devuelve un error cuando el horario ya está ocupado.
* La base de datos mantiene la consistencia de la información.

Si todas estas comprobaciones son correctas, el requisito ha sido verificado.

---

# Ejemplo de Verificación

## Requisito

El sistema debe permitir cancelar una cita.

### Implementación

Se desarrolla el endpoint:

```http
PATCH /appointments/{id}/cancel
```

### Verificación

Se realizan pruebas para comprobar que:

* El endpoint existe.
* Cambia correctamente el estado de la cita.
* Devuelve el código HTTP adecuado.
* Actualiza la base de datos.

Si el comportamiento coincide con la especificación, la implementación queda verificada.

---

# Verificación durante el SDLC

La verificación puede realizarse en distintas etapas del desarrollo:

| Etapa          | Actividad de Verificación                |
| -------------- | ---------------------------------------- |
| Requisitos     | Revisar que sean claros y completos      |
| Diseño         | Revisar diagramas y arquitectura         |
| Implementación | Revisiones de código y pruebas unitarias |
| Integración    | Pruebas entre componentes                |
| Pruebas        | Pruebas funcionales y de integración     |

La calidad no depende únicamente de las pruebas finales; debe verificarse continuamente durante todo el desarrollo.

---

# Relación con el Desarrollo Backend

En el Gestor de Turnos, la verificación incluye comprobar que:

* Los endpoints funcionan correctamente.
* Las reglas de negocio fueron implementadas.
* Las consultas a la base de datos devuelven la información esperada.
* Los códigos HTTP son correctos.
* Las validaciones impiden operaciones inválidas.

Herramientas como Vitest y Supertest permiten automatizar muchas de estas verificaciones.

---

# Diferencia con la Validación

La verificación responde a la pregunta:

> **¿Estamos construyendo correctamente el producto?**

La validación responde a una pregunta diferente:

> **¿Estamos construyendo el producto correcto?**

Ambos procesos son complementarios y forman parte de la calidad del software.

---

# Validación vs Verificación

| Validación                                                      | Verificación                                                        |
| --------------------------------------------------------------- | ------------------------------------------------------------------- |
| Comprueba que el sistema satisface las necesidades del usuario. | Comprueba que el sistema fue construido correctamente.              |
| Se centra en el problema del negocio.                           | Se centra en la implementación.                                     |
| Pregunta: ¿Construimos el producto correcto?                    | Pregunta: ¿Construimos correctamente el producto?                   |
| Participan principalmente usuarios y clientes.                  | Participan principalmente desarrolladores, QA y revisores técnicos. |

---

# Conclusión

La verificación garantiza que cada componente del software cumple con las especificaciones definidas durante el desarrollo.

Al realizar verificaciones continuas mediante revisiones, pruebas y análisis, es posible detectar defectos tempranamente, reducir costos de mantenimiento y aumentar la calidad del producto antes de que llegue a los usuarios.
