# Ejercicio Integrador: Diseño de Software del Gestor de Turnos

## Objetivo

Aplicar los conceptos de Arquitectura en Capas, Modularidad, Acoplamiento y Cohesión, Principios SOLID y Patrones de Diseño al sistema Gestor de Turnos.

---

# 1. Arquitectura en Capas

## Capas del Sistema

### Presentación

Responsabilidad:

* Mostrar la interfaz al usuario.
* Recibir solicitudes.
* Mostrar respuestas.

Componentes:

* Frontend Web.

---

### Aplicación

Responsabilidad:

* Recibir las solicitudes HTTP.
* Coordinar el flujo de ejecución.

Componentes:

* Routes.
* Controllers.

---

### Negocio

Responsabilidad:

* Implementar las reglas del negocio.
* Validar disponibilidad.
* Gestionar citas.
* Gestionar clientes.
* Gestionar servicios.

Componentes:

* AppointmentService.
* ClientService.
* ServiceService.
* UserService.

---

### Datos

Responsabilidad:

* Acceder a la base de datos.
* Guardar y recuperar información.

Componentes:

* AppointmentRepository.
* ClientRepository.
* ServiceRepository.
* UserRepository.

---

# 2. Modularidad

El sistema se divide en módulos según el dominio del negocio.

## appointments

Responsabilidades:

* Crear citas.
* Cancelar citas.
* Reprogramar citas.
* Consultar agenda.

---

## clients

Responsabilidades:

* Registrar clientes.
* Consultar clientes.
* Actualizar información.

---

## services

Responsabilidades:

* Crear servicios.
* Actualizar servicios.
* Consultar servicios.

---

## users

Responsabilidades:

* Gestionar empleados.
* Gestionar administradores.
* Controlar permisos.

---

# 3. Acoplamiento y Cohesión

## Cohesión

Cada módulo contiene únicamente funcionalidades relacionadas con su responsabilidad.

Ejemplo:

appointments/

* Crear cita.
* Cancelar cita.
* Reprogramar cita.
* Consultar disponibilidad.

Alta cohesión.

---

## Acoplamiento

Los módulos interactúan mediante servicios e interfaces claramente definidas.

Ejemplo:

AppointmentController

↓

AppointmentService

↓

AppointmentRepository

Cada componente conoce únicamente la capa inmediata inferior.

Esto reduce el acoplamiento entre módulos.

---

# 4. Aplicación de SOLID

## Single Responsibility Principle (SRP)

AppointmentService administra únicamente la lógica relacionada con las citas.

EmailService administra únicamente el envío de correos.

---

## Open/Closed Principle (OCP)

El sistema puede incorporar nuevos métodos de notificación (SMS o WhatsApp) sin modificar AppointmentService.

---

## Liskov Substitution Principle (LSP)

Administrador y Empleado pueden utilizar el sistema respetando el comportamiento esperado de un Usuario.

---

## Interface Segregation Principle (ISP)

Se utilizan interfaces específicas para cada responsabilidad.

Ejemplo:

IAppointmentService

IUserService

INotificationService

---

## Dependency Inversion Principle (DIP)

AppointmentService depende de la abstracción INotificationService y no de una implementación concreta.

---

# 5. Patrones de Diseño

## Repository

Utilizado para encapsular el acceso a la base de datos.

Ejemplo:

AppointmentRepository.

---

## Strategy

Permite utilizar distintos mecanismos de notificación.

* Email.
* SMS.
* WhatsApp.

---

## State

Representa los estados por los que pasa una cita.

* Pendiente.
* Confirmada.
* Cancelada.
* Completada.

---

# 6. Arquitectura General del Proyecto

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

# 7. Organización Modular

src/

├── appointments/
│   ├── appointment.controller.ts
│   ├── appointment.service.ts
│   ├── appointment.repository.ts
│   └── appointment.routes.ts
│
├── clients/
│
├── services/
│
├── users/

Cada módulo mantiene sus propias responsabilidades y colabora con los demás mediante interfaces bien definidas.

---

# Conclusión

El Gestor de Turnos aplica una arquitectura en capas para separar responsabilidades técnicas y una organización modular para dividir el sistema por dominios del negocio.

El diseño favorece una alta cohesión, un bajo acoplamiento y utiliza principios SOLID junto con patrones de diseño para construir una aplicación flexible, mantenible y preparada para futuras ampliaciones.
