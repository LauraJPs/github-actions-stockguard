# StockGuard – Práctica de GitHub Actions

Taller individual · Línea de Profundización I – Big Data
**Autora:** Laura Posada (@LauraJPs)

Clasifica el riesgo de inventario de un producto según su stock actual y su stock mínimo:

| Condición | Resultado |
|---|---|
| stock actual = 0 | AGOTADO |
| stock actual ≤ 50 % del mínimo | CRITICO |
| stock actual ≤ mínimo | BAJO |
| otro caso | NORMAL |
| stock negativo o mínimo ≤ 0 | `ValueError` |

## Ejecutar localmente
```bash
python -m pip install -r requirements.txt
pytest -v
```

## CI
El workflow `.github/workflows/ci.yml` se ejecuta en `push` y `pull_request` a `main` y manualmente (`workflow_dispatch`): instala dependencias, valida sintaxis con `compileall` y ejecuta `pytest`.
