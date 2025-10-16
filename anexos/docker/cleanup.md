# Limpieza y buenas prácticas Docker (local-only)
- Detén servicios antes de borrar (`docker compose down`).
- Usa etiquetas claras (`:local`) para no tocar imágenes del sistema.
- Verifica puertos con `ss -tulpen` y limita a `127.0.0.1`.
- `docker system prune -f` solo cuando estés seguro de no borrar recursos útiles.
