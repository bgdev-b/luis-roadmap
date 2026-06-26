# Observer

## Problema que resuelve
Define una relación **uno a muchos** donde cuando un objeto cambia su estado, todos sus dependientes son notificados automáticamente. Desacopla al emisor (subject) de los receptores (observers), que pueden suscribirse o desuscribirse libremente.

## Implementación

```csharp
// Interfaz del observer
public interface IObserver
{
    void Actualizar(string evento, object datos);
}

// Subject: el objeto que emite eventos
public class SistemaDeOrdenes
{
    private readonly List<IObserver> _observadores = new();

    public void Suscribir(IObserver obs) => _observadores.Add(obs);
    public void Desuscribir(IObserver obs) => _observadores.Remove(obs);

    private void Notificar(string evento, object datos)
    {
        foreach (var obs in _observadores)
            obs.Actualizar(evento, datos);
    }

    public void CrearOrden(string producto, int cantidad)
    {
        Console.WriteLine($"\n[Sistema] Nueva orden: {cantidad}x {producto}");
        Notificar("OrdenCreada", new { Producto = producto, Cantidad = cantidad });
    }

    public void CancelarOrden(string orderId)
    {
        Console.WriteLine($"\n[Sistema] Orden {orderId} cancelada");
        Notificar("OrdenCancelada", orderId);
    }
}

// Observers concretos
public class ServicioEmail : IObserver
{
    public void Actualizar(string evento, object datos)
    {
        if (evento == "OrdenCreada")
            Console.WriteLine($"[Email] Enviando confirmación de orden al cliente.");
    }
}

public class ServicioInventario : IObserver
{
    public void Actualizar(string evento, object datos)
    {
        if (evento == "OrdenCreada")
            Console.WriteLine($"[Inventario] Reservando stock para la orden.");
        else if (evento == "OrdenCancelada")
            Console.WriteLine($"[Inventario] Liberando stock de orden {datos}.");
    }
}

public class ServicioAuditoria : IObserver
{
    public void Actualizar(string evento, object datos)
    {
        Console.WriteLine($"[Auditoría] Registrando evento: {evento}");
    }
}

// Uso
var sistema = new SistemaDeOrdenes();

sistema.Suscribir(new ServicioEmail());
sistema.Suscribir(new ServicioInventario());
sistema.Suscribir(new ServicioAuditoria());

sistema.CrearOrden("Laptop", 2);
sistema.CancelarOrden("ORD-001");
```

**Clave:** El `SistemaDeOrdenes` no sabe nada sobre email, inventario ni auditoría. Se pueden agregar nuevos observers sin modificarlo.
