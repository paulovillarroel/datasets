# Conjuntos de datos

Conjuntos de datos que uso en cursos, talleres y ejemplos de [Hazla con Datos](https://hazlacondatos.com). Cada carpeta contiene un conjunto con su diccionario de datos. Cada conjunto es sintético o proviene de una fuente abierta, y su README indica cuál.

## Catálogo

| Conjunto | Descripción | Filas | Columnas | Origen | Agregado |
|---|---|---:|---:|---|---|
| [lista_espera](lista_espera/) | Casos de una lista de espera de consultas de especialidad, con problemas de calidad incluidos a propósito para practicar análisis exploratorio | 2.018 | 9 | Sintético | 2026-10-27 |

## Lectura directa desde R o Python

Los archivos se pueden leer sin descargarlos, con la dirección *raw* de GitHub. La dirección se arma en tres trozos (el servidor, el repositorio con su rama y la carpeta con el archivo) para que se lea con facilidad. Para otro conjunto basta con cambiar el último trozo.

```r
library(tidyverse)

url_datos <- paste0(
  "https://raw.githubusercontent.com/",
  "paulovillarroel/datasets/main/",
  "lista_espera/lista_espera.csv"
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
    "lista_espera/lista_espera.csv"
)

datos = pd.read_csv(url_datos, encoding="utf-8")
```

La dirección de la página del archivo en GitHub, la que contiene `/blob/`, muestra el archivo en el navegador y entrega una página web, así que para leer los datos se usa siempre la dirección *raw*.

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
