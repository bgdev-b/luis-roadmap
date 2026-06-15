# Requisitos Funcionales

## Definición

Los requisitos funcionales describen las acciones, comportamientos y funciones específicas que debe realizar un sistema. Definen lo que hará el sistema, desde las interacciones del usuario hasta las respuestas del sistema. 

## Características clave de los requisitos funcionales

Los requisitos funcionales se caracterizan por lo siguiente:

- Acciones especificas: Definen tareas claras y específicas que el sistema debe ser capaz de realizar. Por ejemplo, procesar un pago o recuperar datos de un usuario.

- Interacciones entre el usuario y el sistema:Los requisitos funcionales especifican cómo interactuarán los usuarios con el sistema, como enviar formularios, iniciar sesión o realizar transacciones.

- Respuestas y salidas del sistema:Detallan cómo debe responder el sistema a ciertas entradas o eventos, como mostrar mensajes de confirmación después de enviar un formulario o procesar una transacción.

- Manejo de datos:Estos requisitos incluyen la forma en que el sistema ingresará, procesará, almacenará y recuperará los datos, garantizando que fluyan de manera eficiente y precisa.

## Ejemplos de requisitos funcionales.

- Inicio de sesión de usuario:El sistema debe permitir a los usuarios iniciar sesión utilizando un nombre de usuario y contraseña válidos.

- Procesamiento de Negocios:El sistema debe procesar los pagos con tarjeta de crédito y proporcionar a los usuarios un recibo cuando las transacciones sean exitosas.

- Recuperación de datos:El sistema debe recuperar y mostrar datos específicos del usuario de la base de datos en función de las consultas de búsqueda.

## Explicación Feynman

Los requisitos funcionales describen las capacidades que debe tener el sistema.

Responden a la pregunta:

¿Qué debe hacer el sistema?

Por ejemplo, en un cajero automático:

* Permitir retirar dinero.
* Consultar saldo.
* Depositar fondos.

Si el sistema no puede realizar esas funciones, entonces no cumple su propósito.

Los requisitos funcionales describen acciones concretas que el sistema debe ejecutar.

---

## Ejemplo: Gestor de Turnos

### Actor: Cliente

* El sistema debe permitir consultar horarios disponibles.
* El sistema debe permitir reservar turnos.
* El sistema debe permitir cancelar turnos.
* El sistema debe permitir reprogramar una cita.

### Actor: Empleado

* El sistema debe permitir visualizar la agenda diaria.
* El sistema debe permitir confirmar citas.
* El sistema debe registrar servicios realizados.

### Actor: Administrador

* El sistema debe permitir gestionar usuarios.
* El sistema debe permitir gestionar servicios.
* El sistema debe generar reportes.

### Reglas Funcionales

* El sistema debe impedir reservas duplicadas.
* El sistema debe validar la disponibilidad antes de registrar una cita.
* El sistema debe almacenar el historial de turnos.

---

## Diferencia entre Objetivos y Requisitos Funcionales

### Objetivo

Describe el resultado que se desea alcanzar.

Ejemplo:

* Reducir conflictos de horarios.

### Requisito Funcional

Describe una capacidad específica del sistema.

Ejemplo:

* El sistema debe validar automáticamente la disponibilidad de horarios antes de crear una cita.

Los objetivos indican qué se quiere lograr.

Los requisitos funcionales describen qué debe hacer el sistema para lograrlo.

