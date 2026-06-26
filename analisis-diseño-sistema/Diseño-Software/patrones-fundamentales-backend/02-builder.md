# Builder

## Problema que resuelve
Permite construir objetos complejos **paso a paso**, separando la construcción de su representación. Evita constructores con demasiados parámetros ("constructor telescópico") y permite crear distintas variantes del mismo objeto con el mismo proceso.

## Implementación

```csharp
// Producto final
public class Reporte
{
    public string Titulo { get; set; }
    public string Formato { get; set; }       // PDF, Excel, HTML
    public bool IncluyeGraficos { get; set; }
    public bool IncluyeTablas { get; set; }
    public DateTime FechaGeneracion { get; set; }

    public override string ToString() =>
        $"[{Formato}] {Titulo} | Gráficos: {IncluyeGraficos} | Tablas: {IncluyeTablas}";
}

// Builder
public class ReporteBuilder
{
    private readonly Reporte _reporte = new Reporte
    {
        FechaGeneracion = DateTime.Now
    };

    public ReporteBuilder ConTitulo(string titulo)
    {
        _reporte.Titulo = titulo;
        return this; // permite encadenamiento fluido
    }

    public ReporteBuilder EnFormato(string formato)
    {
        _reporte.Formato = formato;
        return this;
    }

    public ReporteBuilder ConGraficos()
    {
        _reporte.IncluyeGraficos = true;
        return this;
    }

    public ReporteBuilder ConTablas()
    {
        _reporte.IncluyeTablas = true;
        return this;
    }

    public Reporte Build() => _reporte;
}

// Uso
var reporte = new ReporteBuilder()
    .ConTitulo("Ventas Mensuales")
    .EnFormato("PDF")
    .ConGraficos()
    .ConTablas()
    .Build();

Console.WriteLine(reporte);
// [PDF] Ventas Mensuales | Gráficos: True | Tablas: True
```

**Clave:** Cada método del builder retorna `this`, permitiendo la sintaxis fluida en cadena.
