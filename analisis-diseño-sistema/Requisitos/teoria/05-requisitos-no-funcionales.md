# Requisitos no Funcionales.

## Definición

Los requisitos no funcionales, se centran en el rendimiento del sistema. Abordan aspectos como el rendimiento, la seguridad, la escalabilidad y la fiabilidad, garantizando que el sistema no solo funcione según lo previsto, sino que también ofrezca una experiencia de usuario de alta calidad.

## Características clave de los requisitos no funcionales.

Los requisitos no funcionales generalmente se definen por:

- Rendimiento:Describe la rapidez con la que debe funcionar el sistema en condiciones normales y máximas, como los tiempos de carga de la página o la velocidad de procesamiento.

- Escalabilidad organizacional:Garantiza que el sistema pueda manejar el crecimiento en la demanda de los usuarios o el volumen de datos sin una pérdida significativa de rendimiento.
usabilidad:Se centra en hacer que el sistema sea intuitivo y fácil de usar, mejorando la experiencia del usuario a través del diseño y la accesibilidad.

- Confiabilidad :Garantiza que el sistema funcione de manera constante y esté disponible cuando sea necesario, incluido el tiempo de actividad del sistema y la tolerancia a errores.
Seguridad:Especifica estándares de seguridad, como cifrado de datos, controles de acceso y medidas para evitar acceso no autorizado o violaciones de datos.

## Ejemplos de requisitos no funcionales.

- Velocidad de rendimiento: El sistema debe procesar las solicitudes de los usuarios en un plazo promedio de 2 segundos, incluso con mucho tráfico de usuarios.

- Disponibilidad del sistema: El sistema debe mantener un tiempo de actividad del 99.9 % para garantizar que los usuarios tengan acceso constante.

- Estándares de seguridad: El sistema debe utilizar encriptación de 256 bits para el almacenamiento de datos y cumplir con las regulaciones de protección de datos pertinentes.

## Explicación Feynman

Los requisitos no funcionales no describen qué hace el sistema.

Describen cómo debe hacerlo.

Por ejemplo:

Un requisito funcional puede ser:

* El sistema debe permitir reservar turnos.

Pero eso no indica si la reserva tardará 1 segundo o 1 minuto, si será segura o si soportará miles de usuarios.

Los requisitos no funcionales definen la calidad del sistema.

---

## Ejemplos Generales

### Rendimiento

* El sistema debe responder a las solicitudes en menos de 2 segundos.

### Disponibilidad

* El sistema debe estar disponible el 99.9% del tiempo.

### Seguridad

* El sistema debe cifrar las contraseñas de los usuarios.

### Usabilidad

* Un usuario nuevo debe poder reservar una cita sin capacitación previa.

### Escalabilidad

* El sistema debe soportar hasta 10,000 usuarios concurrentes.

### Confiabilidad

* El sistema debe recuperarse automáticamente ante fallos menores.

---

## Ejemplo: Gestor de Turnos

### Rendimiento

* El sistema debe mostrar los horarios disponibles en menos de 2 segundos.

### Seguridad

* El sistema debe almacenar las contraseñas cifradas.
* El sistema debe restringir el acceso según el rol del usuario.

### Usabilidad

* El proceso de reserva no debe requerir más de 5 pasos.

### Disponibilidad

* El sistema debe estar disponible durante el horario de operación del negocio.

### Escalabilidad

* El sistema debe soportar el crecimiento futuro de clientes y servicios.

### Confiabilidad

* El sistema no debe perder información de las citas registradas.

---

## Diferencia entre Requisitos Funcionales y No Funcionales

### Requisito Funcional

Describe una función del sistema.

Ejemplo:

* El sistema debe permitir cancelar un turno.

### Requisito No Funcional

Describe una característica de calidad.

Ejemplo:

* El sistema debe procesar la cancelación en menos de 2 segundos.

Los requisitos funcionales describen qué hace el sistema.

Los requisitos no funcionales describen cómo debe comportarse mientras lo hace.
