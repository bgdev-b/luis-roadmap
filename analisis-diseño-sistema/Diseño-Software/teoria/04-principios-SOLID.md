# Principios SOLID

## Definición

SOLID es un conjunto de cinco principios de diseño orientado a objetos que ayudan a crear software más mantenible, flexible y fácil de extender.

El nombre SOLID es un acrónimo formado por las iniciales de cinco principios fundamentales:

* S — Single Responsibility Principle
* O — Open/Closed Principle
* L — Liskov Substitution Principle
* I — Interface Segregation Principle
* D — Dependency Inversion Principle

Estos principios buscan reducir el acoplamiento, aumentar la cohesión y facilitar la evolución del software.

---

## Importancia

Aplicar SOLID permite:

* Crear código más limpio.
* Facilitar el mantenimiento.
* Reducir el impacto de los cambios.
* Mejorar la reutilización.
* Favorecer la escalabilidad.

---

# S — Single Responsibility Principle (SRP)

## Definición

Una clase o módulo debe tener una única razón para cambiar.

En otras palabras, cada componente debe encargarse de una sola responsabilidad.

---

## Ejemplo Incorrecto

AppointmentService:

* Crear citas.
* Enviar correos.
* Generar reportes.
* Exportar PDFs.

Tiene demasiadas responsabilidades.

---

## Ejemplo Correcto

AppointmentService

* Gestionar citas.

EmailService

* Enviar correos.

ReportService

* Generar reportes.

---

## Gestor de Turnos

appointments/

* Crear cita.
* Cancelar cita.
* Reprogramar cita.

email/

* Enviar confirmaciones.

Cada módulo posee una responsabilidad específica.

---

# O — Open/Closed Principle (OCP)

## Definición

Las entidades de software deben estar abiertas para extensión pero cerradas para modificación.

Debemos poder agregar comportamientos nuevos sin modificar constantemente el código existente.

---

## Ejemplo

Si en el futuro aparecen nuevos tipos de notificaciones:

* Email
* SMS
* WhatsApp

Lo ideal es agregar nuevas implementaciones sin modificar las ya existentes.

---

# L — Liskov Substitution Principle (LSP)

## Definición

Los objetos de una clase hija deben poder reemplazar a los de la clase padre sin alterar el comportamiento esperado del sistema.

---

## Ejemplo

Si tenemos:

Usuario

↓

Administrador

↓

Empleado

El sistema debe poder trabajar con cualquiera de ellos sin comportamientos inesperados.

---

# I — Interface Segregation Principle (ISP)

## Definición

Es mejor tener varias interfaces pequeñas y específicas que una interfaz gigante con métodos innecesarios.

---

## Ejemplo Incorrecto

IUserActions

* crearCita()
* cancelarCita()
* generarReporte()
* administrarUsuarios()

No todos los usuarios necesitan todas esas funciones.

---

## Ejemplo Correcto

IAppointmentActions

* crearCita()
* cancelarCita()

IReportActions

* generarReporte()

Cada cliente implementa únicamente lo que necesita.

---

# D — Dependency Inversion Principle (DIP)

## Definición

Los módulos de alto nivel no deben depender de implementaciones concretas.

Ambos deben depender de abstracciones.

---

## Ejemplo

Incorrecto:

AppointmentService

↓

EmailService

Dependencia directa.

---

Correcto:

AppointmentService

↓

INotificationService

↓

EmailService

WhatsAppService

SMSService

El servicio de citas no conoce la implementación concreta.

---

## Explicación Feynman

SOLID es un conjunto de reglas para evitar que el software se convierta en un monstruo difícil de mantener.

Cada principio intenta responder a una pregunta:

* SRP → ¿Tiene demasiadas responsabilidades?
* OCP → ¿Puedo agregar funcionalidades sin romper código existente?
* LSP → ¿Las clases hijas pueden sustituir a las clases padre?
* ISP → ¿Las interfaces son demasiado grandes?
* DIP → ¿Estoy dependiendo de implementaciones concretas?

---

## Relación con Acoplamiento y Cohesión

Los principios SOLID ayudan a:

* Incrementar la cohesión.
* Reducir el acoplamiento.

Por esta razón son considerados una continuación natural de los conceptos estudiados anteriormente.

---

## Relación con el Gestor de Turnos

Ejemplos prácticos:

* AppointmentService → SRP.
* NotificationService → OCP.
* User / Admin / Employee → LSP.
* Interfaces específicas → ISP.
* Repositories e Interfaces → DIP.

La aplicación de estos principios facilita que el sistema pueda crecer sin aumentar excesivamente su complejidad.
