# Especificación de Requisitos (SRS)

## Definición

La Especificación de Requisitos de Software (Software Requirements Specification o SRS) es un documento que describe de manera clara y estructurada qué debe hacer un sistema, cuáles son sus requisitos y bajo qué condiciones debe funcionar.

El SRS sirve como un acuerdo entre los interesados del proyecto (clientes, analistas, desarrolladores y testers), proporcionando una referencia común durante todo el ciclo de vida del desarrollo del software.

---

# Importancia

Un SRS permite:

* Definir claramente el alcance del sistema.
* Reducir ambigüedades.
* Facilitar la comunicación entre los interesados.
* Servir como base para el diseño, desarrollo y pruebas.
* Reducir errores y retrabajos durante el proyecto.

Un buen SRS ayuda a que todos los participantes tengan la misma comprensión de lo que debe construirse.

---

# Objetivos

Una especificación de requisitos busca:

* Describir el propósito del software.
* Identificar a los usuarios del sistema.
* Documentar los requisitos funcionales.
* Documentar los requisitos no funcionales.
* Registrar restricciones y supuestos.
* Servir como referencia durante el desarrollo y mantenimiento.

---

# Estructura de un SRS

Aunque puede variar según la organización, un SRS suele incluir las siguientes secciones:

## 1. Introducción

Describe:

* Propósito del documento.
* Alcance del sistema.
* Público objetivo.
* Definiciones y acrónimos.

---

## 2. Descripción General

Presenta una visión de alto nivel del sistema.

Incluye:

* Problema a resolver.
* Objetivos.
* Actores.
* Contexto del negocio.
* Supuestos.
* Restricciones.

---

## 3. Requisitos del Sistema

Contiene todos los requisitos del software.

### Requisitos Funcionales

Describen las funcionalidades que debe proporcionar el sistema.

Ejemplo:

* Registrar clientes.
* Crear citas.
* Cancelar citas.
* Consultar disponibilidad.

---

### Requisitos No Funcionales

Describen cómo debe comportarse el sistema.

Ejemplos:

* Tiempo de respuesta menor a dos segundos.
* Disponibilidad del 99%.
* Uso de HTTPS.
* Contraseñas almacenadas mediante hash.

---

### Restricciones

Condiciones bajo las cuales debe desarrollarse el sistema.

Ejemplos:

* Utilizar PostgreSQL.
* Desarrollar en ASP.NET Core.
* Cumplir con la normativa de protección de datos.

---

## 4. Interfaces

Describe cómo interactúa el sistema con otros elementos.

Puede incluir:

* Interfaces de usuario.
* APIs.
* Bases de datos.
* Sistemas externos.

---

## 5. Criterios de Aceptación

Definen cuándo un requisito puede considerarse completado.

Ejemplo:

> El sistema permitirá crear una cita únicamente si el horario seleccionado se encuentra disponible.

---

# Características de un Buen SRS

Un SRS debe ser:

* Claro.
* Completo.
* Consistente.
* Correcto.
* Verificable.
* Sin ambigüedades.
* Fácil de mantener.

Cada requisito debe poder comprobarse mediante pruebas.

---

# Explicación Feynman

Imagina que un arquitecto va a construir una casa.

Antes de colocar un solo ladrillo necesita un plano que indique:

* Cuántas habitaciones tendrá.
* Dónde estará la cocina.
* Qué materiales se utilizarán.

Ese plano es el equivalente al SRS en un proyecto de software.

Sin él, cada persona construiría algo diferente.

---

# Ejemplo: Gestor de Turnos

## Propósito

Desarrollar un sistema que permita gestionar las citas de una barbería de forma organizada.

---

## Actores

* Cliente.
* Empleado.
* Administrador.

---

## Requisitos Funcionales

* Registrar clientes.
* Consultar servicios.
* Crear citas.
* Cancelar citas.
* Reprogramar citas.
* Consultar disponibilidad.

---

## Requisitos No Funcionales

* Tiempo de respuesta inferior a dos segundos.
* Comunicación mediante HTTPS.
* Contraseñas protegidas mediante hash.
* Base de datos PostgreSQL.

---

## Restricciones

* Backend desarrollado en ASP.NET Core.
* Base de datos PostgreSQL.
* API REST.
* Arquitectura Cliente-Servidor.

---

# Relación con el Ciclo de Desarrollo

El SRS constituye el punto de partida para las siguientes etapas del desarrollo.

```text
Análisis de Requisitos

↓

Especificación de Requisitos (SRS)

↓

Diseño

↓

Implementación

↓

Pruebas

↓

Despliegue
```

Cada fase utiliza el SRS como referencia para garantizar que el sistema cumple los requisitos definidos.

---

# Relación con el Desarrollo Backend

Antes de comenzar a implementar una API, el equipo backend consulta el SRS para conocer:

* Qué funcionalidades debe implementar.
* Qué reglas de negocio debe respetar.
* Qué restricciones técnicas existen.
* Qué criterios de aceptación deben cumplirse.

De esta forma, el desarrollo se realiza siguiendo una especificación previamente acordada.

---

# Conclusión

La Especificación de Requisitos de Software (SRS) es uno de los documentos más importantes de un proyecto.

Define de forma precisa qué debe hacer el sistema y sirve como guía para analistas, desarrolladores, testers y clientes durante todo el ciclo de vida del software.

Un SRS bien elaborado reduce la ambigüedad, mejora la comunicación entre los equipos y disminuye el riesgo de errores durante el desarrollo.
