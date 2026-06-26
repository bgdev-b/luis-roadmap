# Modelo Entidad-Relación (ER)

## Definición

El Modelo Entidad-Relación (ER) es una técnica de modelado utilizada para representar la estructura de los datos de un sistema.

Permite identificar:

* Entidades.
* Atributos.
* Relaciones.
* Cardinalidades.

Su objetivo es describir de forma visual y conceptual cómo se organizan los datos antes de construir la base de datos.

---

## Importancia

El Modelo ER permite:

* Comprender la estructura de los datos.
* Detectar errores de diseño tempranamente.
* Facilitar la comunicación entre analistas y desarrolladores.
* Servir como base para el diseño de bases de datos relacionales.

---

## Componentes Principales

### Entidades

Representan los elementos importantes del negocio.

Ejemplos:

* Cliente
* Servicio
* Cita
* Usuario

---

### Atributos

Describen las características de una entidad.

Ejemplo:

Cliente

* id
* nombre
* telefono
* email

---

### Relaciones

Representan asociaciones entre entidades.

Ejemplos:

* Cliente reserva Cita.
* Servicio corresponde a Cita.

---

### Cardinalidades

Indican cuántas instancias pueden participar en una relación.

Ejemplos:

* Cliente (1) → (N) Cita
* Servicio (1) → (N) Cita

---

## Explicación Feynman

Si una base de datos fuera una ciudad:

* Las entidades serían los edificios.
* Los atributos serían las características de cada edificio.
* Las relaciones serían las calles que los conectan.
* Las cardinalidades indicarían cuántos edificios pueden conectarse entre sí.

El Modelo ER es el mapa completo de esa ciudad.

---

## Ejemplo: Gestor de Turnos

### Entidades

Cliente

* id
* nombre
* telefono
* email

Servicio

* id
* nombre
* duracion
* precio

Cita

* id
* fecha
* hora
* estado

Usuario

* id
* nombre
* email
* rol

---

### Relaciones

Cliente reserva Cita.

Servicio corresponde a Cita.

Usuario administra Cita.

---

### Cardinalidades

Cliente (1) -------- (N) Cita

Servicio (1) ------- (N) Cita

Usuario (1) -------- (N) Cita

---

## Diagrama ER

[Insertar imagen: modelo-er-gestor-turnos.png]

---

## Relación con Bases de Datos

El Modelo ER suele transformarse posteriormente en tablas.

Ejemplo:

Entidad → Tabla

Cliente → clients

Servicio → services

Cita → appointments

Usuario → users

Las relaciones se implementarán mediante claves foráneas en el diseño de bases de datos.
