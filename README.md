# StockGuard – Práctica de GitHub Actions

Taller individual · Línea de Profundización I – Big Data
**Autora:** Laura Juliana Posada Soriano (@LauraJPs)

Clasifica el riesgo de inventario de un producto según su stock actual y su stock mínimo:

| Condición | Resultado |
|---|---|
| stock actual = 0 | AGOTADO |
| stock actual ≤ 50 % del mínimo | CRITICO |
| stock actual ≤ mínimo | BAJO |
| otro caso | NORMAL |
| stock negativo o mínimo ≤ 0 | `ValueError` |

También incluye `detectar_sobrestock(stock_actual, stock_maximo)`: devuelve `True` si el stock supera la capacidad máxima de bodega (agregada en el [PR #1](https://github.com/LauraJPs/github-actions-stockguard/pull/1)).

## Se ejecutó localmente
```bash
python -m pip install -r requirements.txt
pytest -v
```

## CI
El workflow `.github/workflows/ci.yml` se ejecuta en `push` y `pull_request` a `main` y manualmente (`workflow_dispatch`): se instalan dependencias, valida sintaxis con `compileall` y ejecuta `pytest`.


## Evidencias y respuestas del taller
Todas las capturas, el historial de ejecuciones y las respuestas a las preguntas de la guía están en
**[docs/RESPUESTAS_TALLER.md](docs/RESPUESTAS_TALLER.md)**.

| Evidencia | Dónde |
|---|---|
| Ejecución exitosa | Run #2 / #4 · [captura](docs/evidencias/04-run2-exitoso.png) |
| Ejecución fallida intencional | Run #3 · [captura](docs/evidencias/05-run3-fallo-intencional.png) |
| Ejecución corregida | Run #4 · [historial](docs/evidencias/06-historial-ejecuciones.png) |
| Pull Request con checks | [PR #1](https://github.com/LauraJPs/github-actions-stockguard/pull/1) · [captura](docs/evidencias/07-pr1-checks.png) |
| Ejecución manual (`workflow_dispatch`) | Run #7 · [captura](docs/evidencias/08-run7-workflow-dispatch.png) |
