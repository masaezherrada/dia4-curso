 Práctica Día 4: Spring Boot Básico

**Duración:** 120 minutos | **Nivel:** Intermedio

## Objetivos

- Crear una aplicación Spring Boot
- Implementar controladores REST
- Usar Spring Data JPA
- Ejecutar en Docker

## Ejercicios Principales

### Ejercicio 1: Explorar el Proyecto (20 min)

Navega por `dia4_base/repo-ejemplos/04-spring-boot`:
- `Application.java`: Clase principal
- `HelloController.java`: Controlador REST
- `pom.xml`: Dependencias Spring Boot
- `Dockerfile`: Configuración Docker

### Ejercicio 2: Ejecutar la Aplicación (15 min)

```bash
mvn spring-boot:run
```

Abre http://localhost:8080/hello en el navegador.

### Ejercicio 3: Crear un Nuevo Endpoint (30 min)

Crea `BookController.java`:

```java
@RestController
@RequestMapping("/api/books")
public class BookController {
    
    @GetMapping
    public List<String> getBooks() {
        return Arrays.asList("Effective Java", "Clean Code");
    }
    
    @GetMapping("/{id}")
    public String getBook(@PathVariable Long id) {
        return "Book " + id;
    }
}
```

### Ejercicio 4: Dockerizar (30 min)

Construye la imagen Docker:

```bash
mvn clean package
docker build -t curso-spring-boot .
docker run -p 8080:8080 curso-spring-boot
```

### Ejercicio 5: Tests de Integración (25 min)

Completa `SmokeTest.java` para verificar que el contexto de Spring carga correctamente.