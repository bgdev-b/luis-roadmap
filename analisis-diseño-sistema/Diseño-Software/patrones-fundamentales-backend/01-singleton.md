# Singleton

## Problema que resuelve
Garantiza que una clase tenga **una única instancia** en toda la aplicación y provee un punto de acceso global a ella. Útil para recursos compartidos como configuraciones, conexiones a base de datos o loggers, donde crear múltiples instancias sería costoso o incorrecto.

## Implementación

```csharp
public sealed class DatabaseConnection
{
    // La única instancia, creada de forma lazy y thread-safe
    private static readonly Lazy<DatabaseConnection> _instance =
        new Lazy<DatabaseConnection>(() => new DatabaseConnection());

    private string _connectionString;

    // Constructor privado: nadie puede instanciar esta clase desde afuera
    private DatabaseConnection()
    {
        _connectionString = "Server=localhost;Database=MiApp;";
        Console.WriteLine("Conexión creada (solo ocurre una vez)");
    }

    public static DatabaseConnection Instance => _instance.Value;

    public void ExecuteQuery(string query)
    {
        Console.WriteLine($"Ejecutando en [{_connectionString}]: {query}");
    }
}

// Uso
var conn1 = DatabaseConnection.Instance;
var conn2 = DatabaseConnection.Instance;

conn1.ExecuteQuery("SELECT * FROM usuarios");
Console.WriteLine(object.ReferenceEquals(conn1, conn2)); // true → misma instancia
```

**Clave:** `Lazy<T>` garantiza que la instancia se crea una sola vez incluso en entornos multi-hilo.
