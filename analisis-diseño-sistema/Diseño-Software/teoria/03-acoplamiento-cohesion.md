# Acoplamiento y Cohesión

## Definición

El acoplamiento y la cohesión son dos métricas fundamentales utilizadas para evaluar la calidad del diseño de software.

Ambos conceptos ayudan a determinar qué tan bien organizado está un sistema y qué tan fácil será mantenerlo, modificarlo y ampliarlo en el futuro.

El objetivo de un buen diseño es lograr:

* Alta cohesión.
* Bajo acoplamiento.

---

## Cohesión

### Definición

La cohesión mide qué tan relacionadas están las responsabilidades dentro de un mismo módulo, clase o componente.

Un módulo posee alta cohesión cuando todos sus elementos trabajan juntos para cumplir un único propósito.

---

### Ejemplo de Alta Cohesión

Módulo:

appointments/

Responsabilidades:

* Crear citas.
* Cancelar citas.
* Reprogramar citas.
* Consultar agenda.

Todas las funcionalidades están relacionadas con la gestión de citas.

---

### Ejemplo de Baja Cohesión

Módulo:

utils/

Responsabilidades:

* Enviar correos.
* Calcular impuestos.
* Validar usuarios.
* Generar reportes.

Las responsabilidades no tienen relación directa entre sí.

---

## Acoplamiento

### Definición

El acoplamiento mide el grado de dependencia entre módulos o componentes diferentes.

Un sistema tiene bajo acoplamiento cuando los módulos pueden modificarse sin afectar significativamente al resto del sistema.

---

### Ejemplo de Bajo Acoplamiento

appointments/

↓

client.service.ts

↓

user.service.ts

Cada módulo se comunica mediante interfaces claras y responsabilidades definidas.

Los cambios internos de un módulo tienen poco impacto sobre los demás.

---

### Ejemplo de Alto Acoplamiento

appointments/

Accede directamente a:

* users database
* clients database
* services database

Además modifica estructuras internas de otros módulos.

Cualquier cambio puede provocar errores en múltiples partes del sistema.

---

## Explicación Feynman

Imagina un equipo de una banda de metal.

### Cohesión

Los integrantes de la batería trabajan juntos para tocar la batería.

Todos cumplen el mismo propósito.

Eso es alta cohesión.

### Acoplamiento

Ahora imagina que el baterista necesita modificar la guitarra para poder tocar.

Cada músico depende constantemente de los demás.

Eso sería alto acoplamiento.

---

## Regla Fundamental

Un buen diseño busca:

Alta Cohesión

↓

Responsabilidades bien agrupadas.

Bajo Acoplamiento

↓

Dependencias mínimas entre módulos.

---

## Ejemplo: Gestor de Turnos

### Alta Cohesión

appointments/

* Crear cita.
* Cancelar cita.
* Reprogramar cita.
* Consultar disponibilidad.

Todas las funciones pertenecen al mismo dominio.

---

### Bajo Acoplamiento

appointments/

Se comunica con:

* clients
* services
* users

mediante servicios o interfaces definidas.

No accede directamente a la lógica interna de otros módulos.

---

## Relación con la Modularidad

La modularidad divide el sistema en módulos.

La cohesión evalúa la calidad interna de cada módulo.

El acoplamiento evalúa la calidad de las dependencias entre módulos.

Por esta razón los tres conceptos están estrechamente relacionados.

---

## Relación con SOLID

Muchos principios SOLID buscan:

* Incrementar la cohesión.
* Reducir el acoplamiento.

Por esta razón el estudio de acoplamiento y cohesión suele preceder al aprendizaje de SOLID.
