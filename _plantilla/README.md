# Nombre del conjunto

Uno o dos párrafos que describan qué contiene el conjunto, para qué sirve y en qué curso o taller se usa.

## Origen

Indicar si el conjunto es sintético o proviene de una fuente abierta. Para una fuente abierta, incluir la institución, el enlace, la fecha de descarga y la licencia original.

## Ficha

| Campo | Valor |
|---|---|
| Archivo | |
| Filas | |
| Columnas | |
| Unidad de observación | |
| Período de referencia | |
| Codificación | UTF-8 |
| Separador | |
| Formato de fechas | AAAA-MM-DD (ISO 8601) |
| Valores faltantes | |
| Origen | |
| Licencia | CC BY 4.0 |
| Versión | |

## Diccionario de datos

| Variable | Tipo | Descripción | Valores esperados |
|---|---|---|---|
| | | | |

## Lectura

```r
library(tidyverse)

url_datos <- paste0(
  "https://raw.githubusercontent.com/",
  "paulovillarroel/datasets/main/",
  "carpeta/archivo.csv"
)

datos <- read_csv(
  url_datos,
  locale = locale(encoding = "UTF-8")
)
```

```python
import pandas as pd

url_datos = (
    "https://raw.githubusercontent.com/"
    "paulovillarroel/datasets/main/"
    "carpeta/archivo.csv"
)

datos = pd.read_csv(url_datos, encoding="utf-8")
```

## Cita sugerida

Autoría (año). *Nombre del conjunto* [conjunto de datos]. https://github.com/paulovillarroel/datasets
