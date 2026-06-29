# Arquitectura Cliente-Servidor

## Definición

La arquitectura cliente-servidor es un modelo de diseño de software en el que un sistema se divide en dos componentes principales:

* Cliente (Client)
* Servidor (Server)

El cliente solicita recursos o servicios y el servidor procesa esas solicitudes y devuelve una respuesta.

Ambos se comunican a través de una red, normalmente utilizando protocolos como HTTP o HTTPS.

---

## Importancia

La arquitectura cliente-servidor permite:

* Separar responsabilidades entre cliente y servidor.
* Centralizar la lógica de negocio y el acceso a los datos.
* Facilitar el mantenimiento y la escalabilidad.
* Permitir que múltiples clientes utilicen el mismo servidor.

Actualmente, la mayoría de aplicaciones web y móviles utilizan este modelo.

---

## Componentes

### Cliente

Es la aplicación utilizada por el usuario.

Su responsabilidad es:

* Mostrar la interfaz.
* Capturar acciones del usuario.
* Enviar solicitudes al servidor.
* Mostrar las respuestas recibidas.

Ejemplos:

* Navegador web.
* Aplicación móvil.
* Aplicación de escritorio.

---

### Servidor

Es la aplicación encargada de procesar las solicitudes de los clientes.

Sus responsabilidades incluyen:

* Aplicar la lógica del negocio.
* Acceder a la base de datos.
* Validar información.
* Enviar respuestas al cliente.

Ejemplos:

* API REST.
* Servidor web.
* Servidor de aplicaciones.

---

## Funcionamiento

El proceso de comunicación sigue generalmente estos pasos:

1. El cliente realiza una solicitud al servidor.
2. El servidor recibe la solicitud.
3. El servidor procesa la petición.
4. Si es necesario, consulta la base de datos.
5. El servidor genera una respuesta.
6. El cliente recibe la respuesta y la muestra al usuario.

---

## Explicación Feynman

Imagina un restaurante.

* Tú eres el cliente.
* El mesero representa la comunicación.
* La cocina representa el servidor.

Tú no cocinas la comida.

Solo haces un pedido.

La cocina prepara el plato y el mesero te entrega el resultado.

La arquitectura cliente-servidor funciona de la misma manera.

---

## Ejemplo: Gestor de Turnos

Cliente:

* Página web de la barbería.

Servidor:

* API REST desarrollada en Node.js o ASP.NET.

Base de datos:

* PostgreSQL.

Cuando un cliente reserva una cita ocurre lo siguiente:

Cliente

↓

POST /appointments

↓

Servidor

↓

AppointmentService

↓

AppointmentRepository

↓

PostgreSQL

↓

Respuesta

↓

Cliente

---

## Ventajas

* Separación clara de responsabilidades.
* Centralización de los datos.
* Fácil mantenimiento.
* Mayor escalabilidad.
* Permite múltiples clientes conectados simultáneamente.

---

## Desventajas

* Dependencia del servidor.
* Si el servidor falla, los clientes no pueden acceder al servicio.
* Puede convertirse en un cuello de botella si recibe demasiadas solicitudes.
* Requiere una infraestructura de red para la comunicación.

---

## Relación con la Arquitectura en Capas

En el servidor suele utilizarse una arquitectura en capas.

Cliente

↓

Servidor

* Routes
* Controllers
* Services
* Repositories

↓

Base de Datos

La arquitectura cliente-servidor define cómo se comunican los sistemas.

La arquitectura en capas organiza internamente el servidor.

---

## Relación con el Desarrollo Backend

En el Gestor de Turnos:

Cliente

* Aplicación web.

Servidor

* API REST.

Base de Datos

* PostgreSQL.

El frontend envía solicitudes HTTP a la API y esta procesa la información antes de acceder a la base de datos y devolver una respuesta al usuario.
