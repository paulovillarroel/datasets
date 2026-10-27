# Conjuntos de datos

Conjuntos de datos que uso en cursos, talleres y ejemplos de [Hazla con Datos](https://hazlacondatos.com). Cada carpeta contiene un conjunto con su diccionario de datos. Cada conjunto es sintético o proviene de una fuente abierta, y su README indica cuál.

## Catálogo

| Conjunto | Descripción | Filas | Columnas | Origen | Agregado |
|---|---|---:|---:|---|---|
| [lista_espera](lista_espera/) | Casos de una lista de espera de consultas de especialidad, con problemas de calidad incluidos a propósito para practicar análisis exploratorio | 2.018 | 9 | Sintético | 2026-10-27 |

## Lectura directa desde R o Python

Los archivos se pueden leer sin descargarlos, con la dirección *raw* de GitHub.

```r
library(tidyverse)

datos <- read_csv(
  "https://raw.githubusercontent.com/paulovillarroel/datasets/main/lista_espera/lista_espera.csv"
)
```

```python
import pandas as pd

datos = pd.read_csv(
    "https://raw.githubusercontent.com/paulovillarroel/datasets/main/lista_espera/lista_espera.csv"
)
```

La dirección con `/blob/` corresponde a la página del archivo en GitHub y entrega una página web, así que para leer los datos se usa la dirección *raw*.

## Estructura del repositorio

Cada conjunto vive en su propia carpeta, con un nombre en minúsculas y guiones bajos.

```
datasets/
├── README.md
├── LICENSE
├── _plantilla/
│   └── README.md
└── lista_espera/
    ├── README.md
    └── lista_espera.csv
```

## Incorporación de un conjunto nuevo

1. Crear una carpeta con el nombre del conjunto.
2. Copiar dentro `_plantilla/README.md` y completar el origen, la ficha y el diccionario de datos.
3. Agregar una fila al catálogo de este archivo.

## Licencia

Los datos se publican bajo [Creative Commons Atribución 4.0 Internacional (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/deed.es), salvo que el README de un conjunto indique otra licencia. Los conjuntos tomados de fuentes abiertas mantienen la licencia de su fuente original.
