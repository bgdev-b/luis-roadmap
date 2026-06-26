# Atributos

## Definición

Los atributos son las propiedades o características que describen una entidad.

En una base de datos, los atributos suelen convertirse en las columnas de una tabla y permiten almacenar información específica sobre cada entidad.

Por ejemplo, si la entidad es Cliente, algunos atributos podrían ser:

* nombre
* teléfono
* correo electrónico

Los atributos proporcionan los detalles necesarios para describir completamente una entidad.

---

## Importancia

Los atributos permiten:

* Describir entidades.
* Almacenar información relevante.
* Diferenciar registros.
* Diseñar correctamente bases de datos.

Sin atributos, las entidades existirían pero no contendrían información útil.

---

## Tipos de Atributos

### Simples

No pueden dividirse en partes más pequeñas.

Ejemplos:

* edad
* género
* precio

---

### Compuestos

Pueden dividirse en varios atributos más simples.

Ejemplo:

Dirección

* calle
* ciudad
* código postal

---

### Monovalorados

Contienen un único valor para cada entidad.

Ejemplo:

* fecha de nacimiento

---

### Multivalorados

Pueden contener varios valores para una misma entidad.

Ejemplo:

* números de teléfono

Un cliente podría tener varios teléfonos asociados.

---

### Derivados

Se calculan a partir de otros atributos.

Ejemplo:

* edad

La edad puede obtenerse a partir de la fecha de nacimiento.

---

### Clave o Identificador

Permiten identificar de manera única cada instancia de una entidad.

Ejemplos:

* id_cliente
* id_servicio
* id_cita

Normalmente se convierten en claves primarias dentro de la base de datos.

---

## Explicación Feynman

Si una entidad es una persona, los atributos son la información que aparece en su documento de identidad.

Por ejemplo:

Entidad:

Cliente

Atributos:

* nombre
* teléfono
* correo
* fecha de nacimiento

La entidad representa "qué es".

Los atributos representan "qué sabemos sobre ella".

---

## Ejemplo: Gestor de Turnos

### Entidad: Cliente

Atributos:

* id
* nombre
* telefono
* email

---

### Entidad: Servicio

Atributos:

* id
* nombre
* duracion
* precio

---

### Entidad: Cita

Atributos:

* id
* fecha
* hora
* estado

---

### Entidad: Usuario

Atributos:

* id
* nombre
* email
* rol

---

## Relación con la Programación

Los atributos suelen convertirse en propiedades de una clase.

Ejemplo:

class Cliente {
id
nombre
telefono
email
}

---

## Relación con Bases de Datos

Los atributos suelen convertirse en columnas.

Ejemplo:

Tabla: clients

* id
* nombre
* telefono
* email

Cada fila representa un cliente y cada columna representa un atributo.
