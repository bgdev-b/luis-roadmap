# Arquitectura en Capas

## Definición

La arquitectura en capas es un patrón arquitectónico que organiza un sistema en distintos niveles o capas, donde cada capa tiene una responsabilidad específica.

Cada capa proporciona servicios a la capa superior y utiliza los servicios de la capa inferior.

Su objetivo es separar responsabilidades y reducir la complejidad del sistema.

---

## Importancia

La arquitectura en capas permite:

* Separar responsabilidades.
* Facilitar el mantenimiento.
* Reducir el acoplamiento.
* Mejorar la reutilización de código.
* Facilitar la evolución del sistema.

---

## Principio Fundamental

Cada capa debe enfocarse en una única responsabilidad.

Ejemplo:

Presentación

↓

Lógica de Negocio

↓

Acceso a Datos

---

## Capas Comunes

### Capa de Presentación

Se encarga de la interacción con el usuario.

Ejemplos:

* Página web.
* Aplicación móvil.
* Interfaz gráfica.

---

### Capa de Negocio

Contiene las reglas y procesos del negocio.

Ejemplos:

* Validar disponibilidad de citas.
* Calcular precios.
* Aplicar reglas de negocio.

---

### Capa de Datos

Gestiona el almacenamiento y recuperación de información.

Ejemplos:

* Consultas SQL.
* Repositorios.
* Bases de datos.

---

## Explicación Feynman

Imagina un restaurante.

Cliente

↓

Mesero

↓

Cocina

El cliente no entra directamente a la cocina.

El mesero recibe la solicitud y la transmite.

Cada parte tiene una responsabilidad específica.

La arquitectura en capas funciona de forma similar.

---

## Ejemplo: Gestor de Turnos

### Capa de Presentación

* Frontend Web.
* Formularios.
* Pantallas de reserva.

---

### Capa de Negocio

* Validar disponibilidad.
* Crear citas.
* Cancelar citas.
* Aplicar reglas de negocio.

---

### Capa de Datos

* Base de datos.
* Repositorios.
* Persistencia de información.

---

## Arquitectura del Proyecto

Frontend

↓

Routes

↓

Controllers

↓

Services

↓

Repositories

↓

Database

---

## Ventajas

* Código más organizado.
* Mayor mantenibilidad.
* Mayor reutilización.
* Facilita pruebas.
* Menor dependencia entre componentes.

---

## Desventajas

* Puede aumentar la complejidad en proyectos pequeños.
* Puede introducir capas innecesarias.
* Puede generar más código de infraestructura.

---

## Relación con el Desarrollo Backend

La mayoría de aplicaciones backend modernas utilizan arquitecturas en capas.

Por ejemplo:

Node.js + Express

↓

Routes

↓

Controllers

↓

Services

↓

Repositories

↓

Database

Cada capa tiene una responsabilidad específica y colabora con las demás para cumplir los objetivos del sistema.
