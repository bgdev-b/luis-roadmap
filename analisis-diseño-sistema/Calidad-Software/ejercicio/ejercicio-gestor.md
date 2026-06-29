# Ejercicio Integrador: Calidad de Software del Gestor de Turnos

## Objetivo

Aplicar los conceptos de Validación, Verificación, Casos de Prueba, Manejo de Errores y Seguridad Básica al sistema Gestor de Turnos.

---

# Contexto

La barbería ha finalizado el desarrollo de la primera versión del Gestor de Turnos.

Antes de poner el sistema en producción, es necesario comprobar que funciona correctamente, cumple los requisitos del negocio y protege la información de los usuarios.

---

# Validación

## Objetivo del negocio

El sistema debe permitir que los clientes puedan reservar citas de forma sencilla, evitando conflictos de horarios.

### Validación realizada

Se verificó que el usuario puede:

- Registrarse.
- Consultar los servicios disponibles.
- Reservar una cita.
- Cancelar una cita.
- Reprogramar una cita.
- Consultar sus próximas citas.

### Resultado

El sistema cumple los requisitos definidos durante el análisis y satisface las necesidades de la barbería.

---

# Verificación

Durante el desarrollo se comprobó que cada componente fue implementado correctamente.

## Requisitos verificados

✔ Crear citas.

✔ Cancelar citas.

✔ Reprogramar citas.

✔ Consultar disponibilidad.

✔ Registrar clientes.

✔ Registrar servicios.

Además se realizaron:

- Revisión de requisitos.
- Revisión de la arquitectura.
- Revisión del código.
- Pruebas unitarias.
- Pruebas de integración.

---

# Casos de Prueba

## Caso de Prueba 001

### Objetivo

Crear una cita correctamente.

### Precondiciones

- Cliente registrado.
- Servicio existente.
- Horario disponible.

### Pasos

1. Seleccionar servicio.
2. Elegir fecha.
3. Elegir hora.
4. Confirmar reserva.

### Resultado esperado

- La cita se crea correctamente.
- HTTP 201 Created.

Estado:

✅ Pass

---

## Caso de Prueba 002

### Objetivo

Intentar reservar un horario ocupado.

### Resultado esperado

- La cita no debe crearse.
- Mostrar mensaje indicando que el horario está ocupado.
- HTTP 409 Conflict.

Estado:

✅ Pass

---

## Caso de Prueba 003

### Objetivo

Cancelar una cita.

### Resultado esperado

- El estado cambia a Cancelada.
- La información se actualiza en la base de datos.
- HTTP 200 OK.

Estado:

✅ Pass

---

# Manejo de Errores

Se definieron distintos escenarios de error.

## Error de Validación

Solicitud:

```http
POST /appointments
```

Sin fecha.

Respuesta:

```http
400 Bad Request
```

---

## Error de Negocio

Intentar reservar un horario ya ocupado.

Respuesta:

```http
409 Conflict
```

---

## Error del Sistema

Fallo de conexión con PostgreSQL.

Respuesta:

```http
500 Internal Server Error
```

Todos los errores generan un registro (log) para facilitar su diagnóstico.

---

# Seguridad Básica

El sistema implementa las siguientes medidas de seguridad:

## Validación de Entradas

Todos los formularios son validados antes de procesarse.

---

## Hash de Contraseñas

Las contraseñas se almacenan utilizando bcrypt.

Nunca se almacenan en texto plano.

---

## Autenticación

Los usuarios deben iniciar sesión mediante correo electrónico y contraseña.

---

## Autorización

Clientes:

- Reservar citas.
- Cancelar sus propias citas.

Administradores:

- Gestionar clientes.
- Gestionar empleados.
- Gestionar servicios.

---

## HTTPS

Toda la comunicación entre el cliente y el servidor utiliza HTTPS.

---

## SQL Injection

Todas las consultas utilizan parámetros preparados o un ORM para evitar la inyección de código SQL.

---

# Flujo de Calidad

```text
Requisitos

↓

Desarrollo

↓

Verificación

↓

Casos de Prueba

↓

Validación

↓

Producción
```

---

# Conclusión

El Gestor de Turnos ha sido evaluado aplicando los principios fundamentales de la calidad del software.

Se comprobó que:

- El sistema satisface las necesidades del negocio (Validación).
- La implementación cumple las especificaciones técnicas (Verificación).
- Las funcionalidades fueron comprobadas mediante casos de prueba.
- Los errores se gestionan de forma controlada.
- Se aplicaron medidas básicas de seguridad para proteger la información de los usuarios.

Gracias a este proceso, el sistema está preparado para ser desplegado con un mayor nivel de confianza y confiabilidad.