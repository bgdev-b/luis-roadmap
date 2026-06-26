# Modularidad

## Definición

La modularidad es un principio de diseño de software que consiste en dividir un sistema en componentes independientes llamados módulos.

Cada módulo agrupa funcionalidades relacionadas y posee una responsabilidad específica dentro del sistema.

El objetivo de la modularidad es reducir la complejidad del software y facilitar su desarrollo, mantenimiento y evolución.

---

## Importancia

La modularidad permite:

* Organizar mejor el código.
* Facilitar el mantenimiento.
* Reducir el impacto de los cambios.
* Favorecer la reutilización.
* Mejorar la comprensión del sistema.

Un sistema modular es más fácil de desarrollar y escalar que un sistema donde todo el código se encuentra mezclado.

---

## Características

Un módulo debe:

* Tener una responsabilidad clara.
* Ser relativamente independiente.
* Encapsular su funcionalidad.
* Comunicarse con otros módulos mediante interfaces definidas.

---

## Explicación Feynman

Imagina que construyes una computadora.

No fabricas todo como una única pieza gigante.

La divides en componentes:

* Procesador.
* Memoria RAM.
* Disco duro.
* Tarjeta gráfica.

Cada componente tiene una función específica.

En software ocurre exactamente lo mismo.

Dividimos el sistema en módulos para que cada uno se encargue de una parte concreta del trabajo.

---

## Ejemplo General

Sistema de Comercio Electrónico

Módulos:

* Clientes.
* Productos.
* Pedidos.
* Pagos.
* Inventario.

Cada módulo resuelve una necesidad específica del negocio.

---

## Ejemplo: Gestor de Turnos

El sistema puede dividirse en los siguientes módulos:

### Clientes

Responsabilidades:

* Registrar clientes.
* Consultar clientes.
* Actualizar información.

---

### Servicios

Responsabilidades:

* Crear servicios.
* Consultar servicios.
* Actualizar precios.

---

### Citas

Responsabilidades:

* Crear citas.
* Cancelar citas.
* Reprogramar citas.
* Consultar agenda.

---

### Usuarios

Responsabilidades:

* Gestionar empleados.
* Gestionar administradores.
* Controlar permisos.

---

## Organización de Carpetas

Ejemplo:

```text
src/

├── clients/
├── services/
├── appointments/
├── users/
```

Cada carpeta representa un módulo del sistema.

---

## Ventajas

* Mayor organización.
* Mejor mantenibilidad.
* Reutilización de código.
* Menor complejidad.
* Facilita el trabajo en equipo.

---

## Desventajas

* Puede aumentar la cantidad de archivos.
* Requiere una buena planificación inicial.
* Una mala división puede generar dependencias innecesarias.

---

## Relación con la Arquitectura en Capas

La arquitectura en capas divide el sistema por responsabilidades técnicas.

La modularidad divide el sistema por responsabilidades funcionales.

Ejemplo:

Arquitectura en capas:

* Controllers
* Services
* Repositories

Modularidad:

* Clients
* Appointments
* Services
* Users

Ambos enfoques suelen utilizarse conjuntamente.

---

## Relación con el Desarrollo Backend

En aplicaciones backend modernas es común combinar modularidad y arquitectura en capas.

Ejemplo:

appointments/

├── appointment.controller.ts
├── appointment.service.ts
├── appointment.repository.ts
└── appointment.routes.ts

Todo lo relacionado con las citas se encuentra agrupado dentro del mismo módulo.
