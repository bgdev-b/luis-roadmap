# Strategy

## Problema que resuelve
Define una **familia de algoritmos intercambiables**, encapsula cada uno en su propia clase y los hace intercambiables en tiempo de ejecución. Elimina condicionales largos (`if/else` o `switch`) cuando el comportamiento varía según el contexto.

## Implementación

```csharp
// Interfaz de la estrategia
public interface ICalculadorDescuento
{
    decimal Calcular(decimal precioOriginal);
}

// Estrategias concretas
public class SinDescuento : ICalculadorDescuento
{
    public decimal Calcular(decimal precio) => precio;
}

public class DescuentoPorcentaje : ICalculadorDescuento
{
    private readonly decimal _porcentaje;
    public DescuentoPorcentaje(decimal porcentaje) => _porcentaje = porcentaje;

    public decimal Calcular(decimal precio) =>
        precio - (precio * _porcentaje / 100);
}

public class DescuentoFijo : ICalculadorDescuento
{
    private readonly decimal _monto;
    public DescuentoFijo(decimal monto) => _monto = monto;

    public decimal Calcular(decimal precio) =>
        Math.Max(0, precio - _monto);
}

// Contexto: usa la estrategia sin saber cuál es
public class CarritoDeCompras
{
    private ICalculadorDescuento _estrategia;

    public CarritoDeCompras(ICalculadorDescuento estrategia)
    {
        _estrategia = estrategia;
    }

    // Permite cambiar la estrategia en tiempo de ejecución
    public void CambiarEstrategia(ICalculadorDescuento nueva) =>
        _estrategia = nueva;

    public decimal CalcularTotal(decimal precio)
    {
        var total = _estrategia.Calcular(precio);
        Console.WriteLine($"Precio: ${precio} → Total con descuento: ${total}");
        return total;
    }
}

// Uso
var carrito = new CarritoDeCompras(new SinDescuento());
carrito.CalcularTotal(100);                              // $100

carrito.CambiarEstrategia(new DescuentoPorcentaje(20));
carrito.CalcularTotal(100);                              // $80

carrito.CambiarEstrategia(new DescuentoFijo(15));
carrito.CalcularTotal(100);                              // $85
```

**Clave:** Agregar un nuevo tipo de descuento solo requiere crear una nueva clase, sin tocar el código existente (Principio Open/Closed).
