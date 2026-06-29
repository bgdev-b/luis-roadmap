# Diagramas UML en la Documentación

## Definición

Los diagramas UML (Unified Modeling Language) son representaciones gráficas estandarizadas utilizadas para documentar, visualizar y comunicar el diseño de un sistema de software.

Complementan la documentación escrita mostrando de forma visual la estructura, el comportamiento y las interacciones entre los diferentes componentes del sistema.

---

# Importancia

La documentación basada en UML permite:

* Facilitar la comunicación entre desarrolladores.
* Representar visualmente sistemas complejos.
* Mejorar la comprensión del diseño.
* Reducir ambigüedades.
* Servir como apoyo durante el mantenimiento y la evolución del software.

Los diagramas permiten comprender relaciones e interacciones que serían difíciles de explicar únicamente mediante texto.

---

# ¿Por qué utilizar UML?

Durante el desarrollo de un proyecto intervienen diferentes personas:

* Analistas.
* Arquitectos.
* Desarrolladores.
* Testers.
* Clientes técnicos.

Los diagramas UML proporcionan un lenguaje visual común que facilita la comunicación entre todos ellos.

---

# Tipos de Diagramas UML más utilizados

## Diagrama de Casos de Uso

Representa las funcionalidades del sistema desde el punto de vista de los actores.

Permite responder preguntas como:

* ¿Qué puede hacer el usuario?
* ¿Qué servicios ofrece el sistema?

**Ejemplo:**

* Reservar cita.
* Cancelar cita.
* Consultar disponibilidad.

---

## Diagrama de Actividad

Describe el flujo de una operación o proceso.

Permite visualizar:

* Decisiones.
* Secuencias de acciones.
* Flujos alternativos.

**Ejemplo:**

Proceso para reservar una cita.

---

## Diagrama de Secuencia

Muestra cómo interactúan los distintos objetos del sistema a lo largo del tiempo.

Permite comprender:

* El orden de los mensajes.
* La colaboración entre componentes.

**Ejemplo:**

Cliente

↓

API

↓

AppointmentService

↓

Repository

↓

Base de Datos

---

## Diagrama de Clases

Representa la estructura estática del sistema.

Describe:

* Clases.
* Atributos.
* Métodos.
* Relaciones.

Es uno de los diagramas más utilizados durante el diseño del software.

---

## Diagrama de Estados

Representa los diferentes estados por los que puede pasar un objeto durante su ciclo de vida.

**Ejemplo:**

Cita

↓

Pendiente

↓

Confirmada

↓

Cancelada

↓

Completada

---

# Explicación Feynman

Imagina que quieres explicar el plano de una ciudad.

Podrías escribir varias páginas describiendo dónde está cada calle.

O podrías mostrar un mapa.

El mapa transmite la información de forma mucho más rápida.

Los diagramas UML cumplen esa misma función dentro del desarrollo de software.

---

# Ejemplo: Gestor de Turnos

Durante el desarrollo del Gestor de Turnos se utilizaron distintos diagramas UML.

| Diagrama     | Propósito                                                           |
| ------------ | ------------------------------------------------------------------- |
| Casos de Uso | Identificar las funcionalidades disponibles para cada actor.        |
| Actividad    | Representar el proceso de reserva de una cita.                      |
| Secuencia    | Mostrar la interacción entre el cliente, la API y la base de datos. |
| Clases       | Modelar las entidades principales del sistema.                      |
| Estados      | Representar el ciclo de vida de una cita.                           |

Cada diagrama documenta un aspecto diferente del sistema.

---

# Relación con la Documentación Técnica

Los diagramas UML forman parte de la documentación técnica del software.

Mientras el texto describe el sistema, los diagramas permiten comprender rápidamente:

* La arquitectura.
* Las relaciones entre componentes.
* Los flujos de ejecución.
* La estructura del dominio.

Por este motivo suelen incluirse junto con la documentación técnica del proyecto.

---

# Herramientas

Algunas herramientas utilizadas para crear diagramas UML son:

* PlantUML.
* diagrams.net (Draw.io).
* StarUML.
* yEd.
* Visual Paradigm.

PlantUML destaca por permitir definir diagramas mediante código, facilitando su integración con proyectos de desarrollo y sistemas de control de versiones.

---

# Buenas Prácticas

* Mantener los diagramas actualizados.
* Representar únicamente la información relevante.
* Utilizar la notación UML estándar.
* Evitar diagramas excesivamente complejos.
* Complementar siempre los diagramas con documentación escrita.

Los diagramas deben facilitar la comprensión del sistema, no aumentar su complejidad.

---

# Relación con el Desarrollo Backend

En un proyecto backend, los diagramas UML ayudan a documentar:

* La arquitectura del sistema.
* Las entidades del dominio.
* Los flujos de ejecución.
* Las interacciones entre servicios.
* La organización del código.

Esto facilita que nuevos desarrolladores comprendan rápidamente el funcionamiento de la aplicación.

---

# Conclusión

Los diagramas UML constituyen una herramienta fundamental para documentar sistemas de software.

Su principal objetivo es complementar la documentación escrita mediante representaciones visuales que facilitan la comunicación, el diseño, el mantenimiento y la evolución del sistema a lo largo de su ciclo de vida.
