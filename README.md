# 📊 Sistema de Análisis Financiero Automatizado con IA

Sistema automatizado y parametrizable que permite generar análisis cuantitativos instantáneos con interpretación asistida por IA para cualquier ticker del mercado comparado contra cualquier benchmark de elección.

---

## 🚀 ¿Qué hace este proyecto?

Con solo cambiar tres parámetros (ticker, benchmark y período), el sistema genera automáticamente:

- **Métricas cuantitativas** en tres grupos: KPIs de precio, análisis de días y comparación vs benchmark
- **Prompt estructurado** enviado a la IA con todos los datos del análisis
- **Resumen ejecutivo profesional** generado por IA en lenguaje natural
- **Carpeta de output** organizada con todos los archivos del análisis

## 🛠️ Tecnologías utilizadas

| Librería | Uso |
|----------|-----|
| `yfinance` | Descarga de datos históricos de Yahoo Finance |
| `pandas` | Manipulación y análisis de datos |
| `numpy` | Cálculos numéricos |
| `cohere` | Generación del resumen ejecutivo con IA |

## ⚙️ Configuración

El sistema funciona con cualquier combinación de parámetros:

```python
params = {
    'ticker':         'AAPL',           # Cualquier ticker de Yahoo Finance
    'ticker_name':    'Apple Inc.',      # Nombre de la empresa
    'start_date':     '2025-10-01',      # Fecha de inicio (YYYY-MM-DD)
    'end_date':       '2026-03-31',      # Fecha de fin   (YYYY-MM-DD)
    'benchmark':      '^GSPC',           # Cualquier benchmark o ETF
    'benchmark_name': 'S&P 500',         # Nombre del benchmark
}
```

**Benchmarks disponibles:**
- `^GSPC` — S&P 500
- `^DJI` — Dow Jones Industrial Average
- `^IXIC` — Nasdaq Composite
- `^RUT` — Russell 2000

## 📁 Estructura de output

Cada ejecución genera automáticamente una carpeta con timestamp:

```
output/
└── YYYYMMDD_analisis_TICKER/
    ├── datos/
    │   ├── datos_historicos.csv     # Precios históricos del ticker
    │   ├── benchmark_datos.csv      # Precios históricos del benchmark
    │   └── prompt_usado.txt         # Prompt enviado a la IA
    └── resumen_ejecutivo.txt        # Análisis generado por IA
```

## 🏃 Cómo ejecutarlo

1. Clona el repositorio:
```bash
git clone https://github.com/tu-usuario/nombre-del-repo.git
```

2. Abre `stock_analyzer.ipynb` en VS Code o Jupyter

3. En la celda de parámetros, añade tu API key de Cohere:
```python
COHERE_API_KEY = 'tu-api-key-aqui'
```
> Obtén una clave gratuita en [dashboard.cohere.com/api-keys](https://dashboard.cohere.com/api-keys)

4. Modifica los `params` con el ticker y período que quieras analizar

5. Ejecuta el notebook de principio a fin (**Run All**)

## 📈 Ejemplo de output

```
==================================================
RESUMEN DEL PERÍODO
==================================================
PRECIOS:
  Inicio:  $242.75
  Final:   $200.66
  Máximo:  $246.26
  Mínimo:  $171.83
CAMBIO:
  La acción BAJÓ 17.34% ($-42.09)
VOLUMEN DE TRANSACCIONES:
  Promedio diario: 57,762,244 acciones
  Total del período: 6,989,231,500 acciones
==================================================
COMPARACIÓN VS S&P 500
==================================================
  Apple Inc.: -17.34%
  S&P 500:    +5.19%
  Apple Inc. quedó 22.53% POR DEBAJO del S&P 500
==================================================
```

---

**Camille Vilain** · [LinkedIn](https://www.linkedin.com/in/camille-vilain/)
