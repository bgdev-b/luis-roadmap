# Repository

## Problema que resuelve
Abstrae el acceso a los datos detrás de una interfaz, **desacoplando la lógica de negocio de la tecnología de persistencia** (SQL, MongoDB, archivo, etc.). El código de negocio habla con el repositorio, no directamente con la base de datos.

## Implementación

```csharp
public class Usuario
{
    public int Id { get; set; }
    public string Nombre { get; set; }
    public string Email { get; set; }
}

// Contrato: define qué operaciones existen, sin importar cómo se implementan
public interface IUsuarioRepository
{
    Usuario ObtenerPorId(int id);
    IEnumerable<Usuario> ObtenerTodos();
    void Agregar(Usuario usuario);
    void Eliminar(int id);
}

// Implementación concreta (simula una base de datos en memoria)
public class UsuarioRepository : IUsuarioRepository
{
    private readonly List<Usuario> _db = new List<Usuario>
    {
        new Usuario { Id = 1, Nombre = "Ana", Email = "ana@mail.com" },
        new Usuario { Id = 2, Nombre = "Luis", Email = "luis@mail.com" }
    };

    public Usuario ObtenerPorId(int id) =>
        _db.FirstOrDefault(u => u.Id == id);

    public IEnumerable<Usuario> ObtenerTodos() => _db;

    public void Agregar(Usuario usuario) => _db.Add(usuario);

    public void Eliminar(int id) => _db.RemoveAll(u => u.Id == id);
}

// Servicio de negocio: solo conoce la interfaz, no la implementación
public class UsuarioService
{
    private readonly IUsuarioRepository _repo;

    public UsuarioService(IUsuarioRepository repo)
    {
        _repo = repo;
    }

    public void MostrarTodos()
    {
        foreach (var u in _repo.ObtenerTodos())
            Console.WriteLine($"{u.Id} - {u.Nombre} ({u.Email})");
    }
}

// Uso
var repo = new UsuarioRepository();
var service = new UsuarioService(repo);
service.MostrarTodos();
```

**Clave:** El servicio puede testearse fácilmente inyectando un repositorio falso (mock) sin necesidad de una base de datos real.
