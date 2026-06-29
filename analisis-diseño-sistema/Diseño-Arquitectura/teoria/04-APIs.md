# APIs (Application Programming Interfaces)

## Definición

Una API (Application Programming Interface) es un conjunto de reglas, protocolos y contratos que permite que diferentes aplicaciones intercambien información y funcionalidades de manera controlada.

Una API actúa como intermediaria entre dos sistemas, permitiendo que uno solicite servicios o datos al otro sin necesidad de conocer su implementación interna.

En una arquitectura cliente-servidor, la API representa el contrato de comunicación entre el cliente y el servidor.

---

# ¿Por qué existen las APIs?

Sin APIs, cada aplicación tendría que conocer el funcionamiento interno de las demás.

Las APIs solucionan este problema proporcionando una interfaz estándar para la comunicación.

Gracias a ellas es posible:

- Compartir información.
- Reutilizar funcionalidades.
- Integrar aplicaciones.
- Construir arquitecturas distribuidas.
- Separar clientes y servidores.

Actualmente prácticamente todas las aplicaciones modernas utilizan una o varias APIs.

---

# Componentes de una API

Una API suele estar formada por:

- Recursos (Resources).
- Endpoints.
- Métodos de comunicación.
- Solicitudes (Request).
- Respuestas (Response).
- Códigos de estado.
- Formato de intercambio de datos (JSON, XML, etc.).

---

# ¿Cómo funciona una API?

El flujo normalmente es el siguiente:

Cliente

↓

Solicitud HTTP

↓

API

↓

Lógica de negocio

↓

Base de datos

↓

Respuesta

↓

Cliente

El cliente nunca accede directamente a la base de datos.

Toda la comunicación pasa por la API.

---

# Explicación Feynman

Imagina un restaurante.

No entras a la cocina.

Hablas con el mesero.

El mesero lleva tu pedido.

La cocina prepara la comida.

El mesero regresa con el plato.

La API es el mesero.

No cocina.

No come.

Simplemente comunica ambas partes.

---

# Tipos de APIs

Existen diferentes estilos y protocolos para construir APIs.

Cada uno fue diseñado para resolver necesidades distintas.

## REST (Representational State Transfer)

REST es el estilo arquitectónico más utilizado actualmente para construir APIs web.

Se basa en recursos identificados mediante URLs y utiliza los métodos HTTP.

Ejemplo:

GET /appointments

POST /appointments

DELETE /appointments/15

Características:

- Usa HTTP.
- Generalmente intercambia información en JSON.
- Stateless.
- Fácil de consumir.
- Muy utilizado en aplicaciones web y móviles.

Ventajas:

- Sencillo.
- Escalable.
- Gran soporte.
- Fácil documentación.

Desventajas:

- Puede requerir múltiples peticiones.
- En algunos casos devuelve más información de la necesaria.

---

## SOAP (Simple Object Access Protocol)

SOAP es un protocolo de comunicación mucho más estricto que REST.

Utiliza XML como formato de intercambio y define reglas muy precisas sobre cómo deben enviarse los mensajes.

Características:

- Basado en XML.
- Muy estructurado.
- Altamente seguro.
- Muy utilizado en banca, seguros y sistemas empresariales.

Ventajas:

- Seguridad avanzada.
- Contratos estrictos.
- Alta confiabilidad.

Desventajas:

- Complejo.
- Verboso.
- Más lento que REST.

Ejemplo de uso:

- Bancos.
- Sistemas gubernamentales.
- ERP empresariales.

---

## RPC (Remote Procedure Call)

RPC permite ejecutar funciones de un servidor como si fueran funciones locales.

En lugar de trabajar con recursos, el cliente invoca procedimientos.

Ejemplo:

createAppointment()

cancelAppointment()

calculatePrice()

El cliente llama directamente a un procedimiento remoto.

Ventajas:

- Muy rápido.
- Fácil para operaciones específicas.

Desventajas:

- Alto acoplamiento.
- Menor flexibilidad.

Ejemplos modernos:

- gRPC.
- JSON-RPC.

---

## GraphQL

GraphQL fue desarrollado por Meta (Facebook).

En lugar de tener muchos endpoints, existe normalmente un único endpoint.

El cliente especifica exactamente qué datos necesita.

Ejemplo:

```graphql
query {

  appointment(id:1){

      date

      client{

          name

      }

  }

}