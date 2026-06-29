# Normalización

## Definición

La normalización es un proceso de diseño de bases de datos que organiza la información en tablas para reducir la redundancia, evitar inconsistencias y mejorar la integridad de los datos.

Consiste en dividir los datos en estructuras más pequeñas y relacionadas, de manera que cada dato se almacene una única vez.

---

## Importancia

La normalización permite:

* Reducir la duplicación de datos.
* Evitar inconsistencias.
* Facilitar el mantenimiento de la información.
* Mejorar la integridad de los datos.
* Facilitar las actualizaciones y eliminaciones.

Una base de datos correctamente normalizada es más fácil de mantener y menos propensa a errores.

---

## Problema de una Base de Datos No Normalizada

Supongamos la siguiente tabla:

| Cliente | Teléfono | Servicio 1 | Servicio 2 | Servicio 3 |
| ------- | -------- | ---------- | ---------- | ---------- |
| Bryant  | 809...   | Corte      | Barba      | Tinte      |

Problemas:

* Se repite información.
* Existe un límite en la cantidad de servicios.
* Si cambia el teléfono del cliente, debe actualizarse en múltiples registros.
* Es difícil agregar nuevos servicios.

---

## Explicación Feynman

Imagina un archivador.

Si escribes el mismo dato en diez hojas diferentes, cuando cambie tendrás que corregir las diez.

Es mucho más sencillo escribir esa información una sola vez y que las demás hojas hagan referencia a ella.

Eso es precisamente lo que busca la normalización.

---

# Formas Normales

## Primera Forma Normal (1NF)

Una tabla cumple la Primera Forma Normal cuando:

* Cada columna contiene un único valor.
* No existen grupos repetidos.
* Cada fila es única.

### Incorrecto

| Cliente | Servicios    |
| ------- | ------------ |
| Bryant  | Corte, Barba |

### Correcto

Clientes

| id | nombre |
| -- | ------ |

Servicios

| id | nombre |
| -- | ------ |

---

## Segunda Forma Normal (2NF)

Una tabla cumple la Segunda Forma Normal cuando:

* Ya cumple la 1NF.
* Todos los atributos dependen completamente de la clave primaria.
* Se eliminan dependencias parciales.

---

## Tercera Forma Normal (3NF)

Una tabla cumple la Tercera Forma Normal cuando:

* Ya cumple la 2NF.
* Ningún atributo depende de otro atributo que no sea la clave primaria.

Todos los atributos deben depender únicamente de la clave primaria.

---

## Ejemplo: Gestor de Turnos

### Sin Normalizar

appointments

| Cliente | Teléfono | Servicio | Precio |
| ------- | -------- | -------- | ------ |

Problemas:

* El teléfono se repite.
* El precio del servicio se repite.
* Cambiar un precio implica modificar muchas filas.

---

### Normalizado

clients

| id | nombre | telefono |

services

| id | nombre | precio |

appointments

| id | fecha | hora | client_id | service_id |

Cada dato se almacena una única vez y las tablas se relacionan mediante identificadores.

---

## Ventajas

* Menor redundancia.
* Mayor consistencia.
* Mejor mantenimiento.
* Actualizaciones más sencillas.
* Mayor integridad de los datos.

---

## Desventajas

* Puede aumentar el número de tablas.
* Algunas consultas requieren más JOINs.
* En ciertos escenarios de alto rendimiento puede ser conveniente aplicar desnormalización.

---

## Relación con el Modelado Relacional

El modelado relacional organiza la información en tablas.

La normalización ayuda a diseñar esas tablas de forma eficiente, reduciendo redundancias y asegurando la integridad de los datos.

Ambos conceptos trabajan conjuntamente durante el diseño de una base de datos.
