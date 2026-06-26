# Proxy

## Problema que resuelve
Provee un **sustituto o intermediario** de otro objeto para controlar el acceso a él. Permite agregar comportamiento extra (caché, logging, control de acceso, lazy loading) sin modificar el objeto original.

## Implementación

```csharp
// Interfaz común para el objeto real y el proxy
public interface IServicioClima
{
    string ObtenerClima(string ciudad);
}

// Objeto real: hace la llamada costosa (simula API externa)
public class ServicioClimaReal : IServicioClima
{
    public string ObtenerClima(string ciudad)
    {
        Console.WriteLine($"[API] Consultando clima para: {ciudad}...");
        // Simula demora de red
        System.Threading.Thread.Sleep(500);
        return $"Clima en {ciudad}: 22°C, parcialmente nublado";
    }
}

// Proxy con caché: intercepta llamadas y evita consultas repetidas
public class ServicioClimaProxy : IServicioClima
{
    private readonly IServicioClima _servicioReal = new ServicioClimaReal();
    private readonly Dictionary<string, string> _cache = new();

    public string ObtenerClima(string ciudad)
    {
        if (_cache.TryGetValue(ciudad, out var resultado))
        {
            Console.WriteLine($"[CACHE] Retornando resultado guardado para: {ciudad}");
            return resultado;
        }

        var respuesta = _servicioReal.ObtenerClima(ciudad);
        _cache[ciudad] = respuesta;
        return respuesta;
    }
}

// Uso: el cliente solo conoce la interfaz, no sabe si habla con el proxy o el real
IServicioClima servicio = new ServicioClimaProxy();

Console.WriteLine(servicio.ObtenerClima("Buenos Aires")); // llama a la API
Console.WriteLine(servicio.ObtenerClima("Buenos Aires")); // usa caché
Console.WriteLine(servicio.ObtenerClima("Madrid"));       // llama a la API
```

**Clave:** El cliente usa exactamente la misma interfaz sin saber que hay un intermediario.
