# Unit of Work

## Problema que resuelve
Agrupa múltiples operaciones sobre repositorios en **una sola transacción atómica**. Si algo falla a mitad del proceso, todos los cambios se revierten. Coordina el trabajo de varios repositorios para que actúen como una unidad.

## Implementación

```csharp
public class Pedido
{
    public int Id { get; set; }
    public string Descripcion { get; set; }
}

public class Inventario
{
    public int ProductoId { get; set; }
    public int Stock { get; set; }
}

// Repositorios simples
public class PedidoRepository
{
    private readonly List<Pedido> _pedidos = new();
    public void Agregar(Pedido p) => _pedidos.Add(p);
    public IEnumerable<Pedido> ObtenerTodos() => _pedidos;
}

public class InventarioRepository
{
    private readonly List<Inventario> _items = new()
    {
        new Inventario { ProductoId = 1, Stock = 10 }
    };

    public void ReducirStock(int productoId, int cantidad)
    {
        var item = _items.FirstOrDefault(i => i.ProductoId == productoId);
        if (item == null) throw new Exception("Producto no encontrado");
        if (item.Stock < cantidad) throw new Exception("Stock insuficiente");
        item.Stock -= cantidad;
    }
}

// Unit of Work: orquesta ambos repositorios y maneja la transacción
public class UnitOfWork : IDisposable
{
    public PedidoRepository Pedidos { get; } = new PedidoRepository();
    public InventarioRepository Inventario { get; } = new InventarioRepository();

    private bool _committed = false;

    public void Commit()
    {
        // Aquí se confirmarían los cambios en la BD real (ej: dbContext.SaveChanges())
        _committed = true;
        Console.WriteLine("Transacción confirmada correctamente.");
    }

    public void Dispose()
    {
        if (!_committed)
            Console.WriteLine("Transacción revertida (rollback).");
    }
}

// Uso
using (var uow = new UnitOfWork())
{
    try
    {
        uow.Pedidos.Agregar(new Pedido { Id = 1, Descripcion = "Pedido #1" });
        uow.Inventario.ReducirStock(productoId: 1, cantidad: 3);
        uow.Commit(); // solo confirma si todo salió bien
    }
    catch (Exception ex)
    {
        Console.WriteLine($"Error: {ex.Message}");
        // El Dispose() ejecuta rollback automáticamente al salir del using
    }
}
```

**Clave:** El bloque `using` garantiza que si no se llama a `Commit()`, los cambios se deshacen.
