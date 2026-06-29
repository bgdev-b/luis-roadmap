# Manejo de Errores

## Definición

El manejo de errores (Error Handling) es el proceso de detectar, gestionar y responder adecuadamente a los errores o situaciones inesperadas que pueden ocurrir durante la ejecución de un programa.

Su objetivo es evitar que la aplicación falle de forma inesperada, proteger los datos y proporcionar información útil tanto al usuario como al desarrollador.

---

# Importancia

Un buen manejo de errores permite:

* Mantener la estabilidad del sistema.
* Evitar pérdidas o corrupción de datos.
* Mejorar la experiencia del usuario.
* Facilitar el mantenimiento y la depuración.
* Reducir riesgos de seguridad.

Una aplicación robusta no es aquella que nunca presenta errores, sino aquella que sabe cómo responder cuando ocurren.

---

# ¿Por qué ocurren los errores?

Durante la ejecución de un programa pueden ocurrir situaciones como:

* Datos de entrada inválidos.
* Archivos inexistentes.
* Fallos de conexión a la base de datos.
* Problemas de red.
* Errores en servicios externos.
* Excepciones inesperadas.

El software debe estar preparado para manejar estas situaciones sin detener su funcionamiento de forma abrupta.

---

# Tipos de Errores

## Errores de Validación

Se producen cuando el usuario envía información inválida.

Ejemplos:

* Correo electrónico con formato incorrecto.
* Contraseña demasiado corta.
* Fecha obligatoria no seleccionada.

Generalmente se responden con un código HTTP **400 Bad Request**.

---

## Errores de Negocio

Se producen cuando una regla del negocio impide realizar una operación.

Ejemplos:

* Reservar un horario ya ocupado.
* Cancelar una cita que ya fue atendida.
* Registrar un correo electrónico que ya existe.

Generalmente se responden con códigos como **409 Conflict** o **422 Unprocessable Entity**.

---

## Errores del Sistema

Son errores internos de la aplicación o de su infraestructura.

Ejemplos:

* Base de datos fuera de servicio.
* Error de conexión con un servicio externo.
* Excepción inesperada.

Generalmente se responden con **500 Internal Server Error**.

---

# Estrategias de Manejo de Errores

Un buen manejo de errores suele seguir estos pasos:

1. Detectar el error.
2. Registrar información para facilitar el diagnóstico.
3. Informar al usuario mediante un mensaje claro.
4. Recuperarse cuando sea posible o finalizar la operación de forma segura.

No todos los errores pueden resolverse automáticamente, pero todos deben gestionarse de forma controlada.

---

# Explicación Feynman

Imagina un ascensor.

Si alguien intenta sobrepasar el peso máximo, el ascensor no se rompe.

En su lugar:

* Detecta el problema.
* Muestra un mensaje.
* Impide iniciar el viaje hasta que el peso sea seguro.

El manejo de errores funciona de la misma manera.

El objetivo no es evitar que existan problemas, sino responder correctamente cuando ocurren.

---

# Ejemplo: Gestor de Turnos

Supongamos que un cliente intenta reservar una cita en un horario ocupado.

Solicitud:

```http
POST /appointments
```

Respuesta:

```http
409 Conflict
```

```json
{
  "message": "El horario seleccionado ya se encuentra ocupado."
}
```

El sistema continúa funcionando normalmente y el usuario recibe una explicación clara del problema.

---

# Ejemplo en Código

C#:

```csharp
try
{
    appointmentService.Create(request);
}
catch (AppointmentConflictException ex)
{
    return Conflict(new
    {
        message = ex.Message
    });
}
```

El programa captura la excepción y devuelve una respuesta apropiada sin finalizar inesperadamente.

---

# Buenas Prácticas

* Validar la información antes de procesarla.
* Utilizar mensajes claros para el usuario.
* Registrar errores mediante logs.
* No revelar información sensible en los mensajes de error.
* Utilizar códigos HTTP adecuados.
* Manejar las excepciones más cerca posible de donde puedan recuperarse.

---

# Qué NO hacer

## Ignorar errores

Nunca se deben capturar excepciones sin hacer nada.

Ejemplo incorrecto:

```csharp
try
{
    SaveAppointment();
}
catch
{
}
```

Esto dificulta encontrar la causa del problema y puede ocultar fallos importantes.

---

## Mostrar información técnica al usuario

Incorrecto:

```text
NullReferenceException at AppointmentService.cs line 52
```

Correcto:

```text
Ha ocurrido un error al procesar la solicitud. Inténtelo nuevamente más tarde.
```

Los detalles técnicos deben registrarse en los logs, no mostrarse al usuario.

---

# Relación con la Verificación

Durante la verificación no solo se comprueba que el sistema funcione correctamente, sino también que responda adecuadamente cuando ocurren errores.

Por ejemplo:

* ¿Qué ocurre si el cliente no existe?
* ¿Qué ocurre si el horario ya está ocupado?
* ¿Qué ocurre si la base de datos no responde?

Estas situaciones también deben probarse.

---

# Relación con el Desarrollo Backend

En una API REST, el manejo de errores suele expresarse mediante códigos HTTP y respuestas estructuradas.

Ejemplos:

| Código | Significado                |
| ------ | -------------------------- |
| 400    | Solicitud inválida         |
| 401    | No autenticado             |
| 403    | Acceso denegado            |
| 404    | Recurso no encontrado      |
| 409    | Conflicto de negocio       |
| 500    | Error interno del servidor |

Una API bien diseñada devuelve siempre respuestas claras y consistentes para que los clientes puedan reaccionar correctamente.

---

# Conclusión

El manejo de errores es un componente esencial de la calidad del software.

Permite que el sistema continúe siendo estable, seguro y fácil de mantener incluso cuando ocurren situaciones inesperadas.

Una aplicación de calidad no evita todos los errores, sino que los gestiona de forma controlada, informa adecuadamente al usuario y proporciona a los desarrolladores la información necesaria para diagnosticar y corregir los problemas.
