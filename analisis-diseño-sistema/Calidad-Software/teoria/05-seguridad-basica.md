# Seguridad Básica

## Definición

La seguridad del software es el conjunto de prácticas, mecanismos y controles destinados a proteger un sistema, sus datos y sus usuarios frente a accesos no autorizados, modificaciones indebidas o ataques.

Su objetivo es garantizar que la información permanezca protegida durante todo el ciclo de vida de la aplicación.

La seguridad constituye uno de los atributos fundamentales de la calidad del software.

---

# Importancia

Aplicar medidas básicas de seguridad permite:

* Proteger la información de los usuarios.
* Evitar accesos no autorizados.
* Reducir vulnerabilidades.
* Mantener la disponibilidad del sistema.
* Incrementar la confianza de los usuarios.

La seguridad debe considerarse desde las primeras etapas del desarrollo y no únicamente al finalizar el proyecto.

---

# Principios Básicos de Seguridad

## Confidencialidad

Solo las personas autorizadas deben acceder a la información.

Ejemplo:

Solo un administrador puede visualizar todos los clientes registrados.

---

## Integridad

La información no debe modificarse sin autorización.

Ejemplo:

Un cliente no debe poder modificar el precio de un servicio.

---

## Disponibilidad

El sistema debe estar disponible cuando los usuarios lo necesiten.

Ejemplo:

El Gestor de Turnos debe continuar funcionando incluso cuando reciba múltiples solicitudes.

---

# Medidas Básicas de Seguridad

## Validación de Entradas

Toda la información enviada por el usuario debe validarse antes de procesarse.

Ejemplos:

* Campos obligatorios.
* Formato del correo electrónico.
* Longitud de la contraseña.
* Valores permitidos.

Nunca se debe confiar en los datos enviados por el cliente.

---

## Autenticación

Consiste en verificar la identidad del usuario.

Ejemplos:

* Usuario y contraseña.
* Inicio de sesión con Google.
* Autenticación mediante tokens (JWT).

---

## Autorización

Una vez autenticado el usuario, el sistema debe comprobar qué acciones tiene permitido realizar.

Ejemplo:

* Un cliente puede reservar una cita.
* Un administrador puede eliminar usuarios.
* Un empleado puede gestionar únicamente sus propias citas.

---

## Hash de Contraseñas

Las contraseñas nunca deben almacenarse en texto plano.

En su lugar, se almacena un hash generado mediante algoritmos seguros como:

* Argon2
* bcrypt
* PBKDF2

De esta forma, aunque la base de datos sea comprometida, las contraseñas reales no quedan expuestas.

---

## Uso de HTTPS

Toda la comunicación entre cliente y servidor debe realizarse mediante HTTPS.

Esto protege la información durante su transmisión evitando que pueda ser interceptada.

---

# Vulnerabilidades Comunes

## SQL Injection

Ocurre cuando un atacante introduce código SQL malicioso a través de una entrada del usuario.

Prevención:

* Consultas parametrizadas.
* ORM.
* Validación de entradas.

---

## Cross-Site Scripting (XSS)

Consiste en insertar código JavaScript malicioso que posteriormente ejecutará el navegador de otro usuario.

Prevención:

* Escapar correctamente la salida.
* Validar entradas.
* Aplicar políticas de seguridad del navegador.

---

## Fuerza Bruta

Consiste en intentar múltiples combinaciones de contraseñas hasta encontrar la correcta.

Prevención:

* Limitar intentos de inicio de sesión.
* Utilizar contraseñas seguras.
* Implementar autenticación multifactor cuando sea posible.

---

# Explicación Feynman

Imagina una biblioteca.

La seguridad no consiste únicamente en cerrar la puerta.

También incluye:

* Identificar quién entra.
* Determinar qué salas puede visitar.
* Proteger los libros para que no sean modificados.
* Mantener la biblioteca abierta durante el horario establecido.

La seguridad del software sigue exactamente el mismo principio.

---

# Ejemplo: Gestor de Turnos

El sistema implementa las siguientes medidas:

* Validar todos los formularios antes de procesarlos.
* Almacenar las contraseñas mediante hash.
* Utilizar HTTPS para todas las comunicaciones.
* Permitir únicamente a los administradores eliminar usuarios.
* Utilizar consultas parametrizadas para evitar SQL Injection.

---

# Relación con el Desarrollo Backend

En una API REST es habitual aplicar medidas como:

* Validación de datos con Zod o FluentValidation.
* Hash de contraseñas con bcrypt o Argon2.
* Autenticación mediante JWT.
* Control de acceso basado en roles.
* Uso de HTTPS.
* Manejo adecuado de errores sin revelar información sensible.

Estas prácticas incrementan considerablemente la seguridad de la aplicación.

---

# Relación con la Calidad del Software

La seguridad forma parte de la calidad del software.

Un sistema no puede considerarse de alta calidad si expone información sensible, permite accesos indebidos o presenta vulnerabilidades que comprometan la información de los usuarios.

Por ello, la seguridad debe integrarse durante todo el ciclo de vida del desarrollo y no añadirse únicamente al finalizar el proyecto.

---

# Conclusión

La seguridad básica constituye un conjunto de prácticas esenciales para desarrollar aplicaciones confiables.

Medidas como la validación de entradas, la autenticación, la autorización, el almacenamiento seguro de contraseñas y el uso de HTTPS permiten reducir significativamente los riesgos y proteger tanto a los usuarios como a la información del sistema.
