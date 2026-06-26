# Mediator

## Problema que resuelve
Reduce el **acoplamiento entre objetos** que necesitan comunicarse entre sí, haciendo que en lugar de referenciarse directamente, todos se comuniquen a través de un mediador central. Evita la red de dependencias cruzadas ("spaghetti de objetos").

## Implementación

```csharp
// Interfaz del mediador
public interface IMediator
{
    void Enviar(string mensaje, Componente remitente);
}

// Componente base
public abstract class Componente
{
    protected IMediator _mediator;
    public string Nombre { get; }

    protected Componente(string nombre, IMediator mediator)
    {
        Nombre = nombre;
        _mediator = mediator;
    }

    public abstract void Recibir(string mensaje, string de);
}

// Mediador concreto: conoce a todos los componentes y dirige la comunicación
public class ChatMediator : IMediator
{
    private readonly List<Componente> _componentes = new();

    public void Registrar(Componente c) => _componentes.Add(c);

    public void Enviar(string mensaje, Componente remitente)
    {
        Console.WriteLine($"\n[Mediador] '{remitente.Nombre}' envía: \"{mensaje}\"");
        foreach (var comp in _componentes)
        {
            if (comp != remitente) // no se envía a sí mismo
                comp.Recibir(mensaje, remitente.Nombre);
        }
    }
}

// Componentes concretos: solo conocen al mediador, no entre sí
public class Modulo : Componente
{
    public Modulo(string nombre, IMediator mediator) : base(nombre, mediator) { }

    public void EnviarMensaje(string mensaje) =>
        _mediator.Enviar(mensaje, this);

    public override void Recibir(string mensaje, string de) =>
        Console.WriteLine($"  [{Nombre}] recibió de [{de}]: \"{mensaje}\"");
}

// Uso
var mediator = new ChatMediator();

var pagos    = new Modulo("Pagos", mediator);
var envios   = new Modulo("Envíos", mediator);
var notif    = new Modulo("Notificaciones", mediator);

mediator.Registrar(pagos);
mediator.Registrar(envios);
mediator.Registrar(notif);

// Pagos notifica al resto sin conocerlos directamente
pagos.EnviarMensaje("Pago aprobado para orden #42");

// Envíos notifica al resto
envios.EnviarMensaje("Paquete despachado para orden #42");
```

**Clave:** `Pagos` no tiene ninguna referencia a `Envíos` ni a `Notificaciones`. Toda comunicación pasa por el mediador, lo que facilita agregar o quitar módulos sin romper nada.
