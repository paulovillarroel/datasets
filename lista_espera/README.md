# Lista de espera sintética

Casos simulados de una lista de espera de consultas de especialidad en cinco hospitales ficticios. El archivo incluye a propósito problemas de calidad de datos para practicar análisis exploratorio, por ejemplo con la mnemotecnia ALICIA FREDUSA. El diccionario describe los valores esperados, y el ejercicio consiste en contrastarlo con lo que efectivamente trae el archivo.

Los datos son sintéticos. Las personas, los identificadores, los establecimientos y las fechas son ficticios.

## Ficha

| Campo | Valor |
|---|---|
| Archivo | `lista_espera.csv` |
| Filas | 2.018 |
| Columnas | 9 |
| Unidad de observación | Un caso, es decir, una derivación de una persona a una especialidad |
| Período de referencia | 2023-01-01 a 2026-09-30 |
| Fecha de corte | 2026-09-30 |
| Codificación | UTF-8 |
| Separador | Coma |
| Formato de fechas | AAAA-MM-DD (ISO 8601) |
| Valores faltantes | Celda vacía |
| Origen | Sintético, generado con semilla fija |
| Licencia | CC BY 4.0 |
| Versión | 2026-10-27 |

## Diccionario de datos

| Variable | Tipo | Descripción | Valores esperados |
|---|---|---|---|
| `id_caso` | Entero | Identificador del caso | Único por fila |
| `id_paciente` | Entero | Identificador seudónimo de la persona | Una persona puede tener varios casos |
| `edad` | Entero | Edad en años al ingreso a la lista | 0 a 110 |
| `sexo` | Texto | Sexo registrado | Mujer, Hombre |
| `especialidad` | Texto | Especialidad de destino | Cardiología, Cirugía general, Dermatología, Ginecología, Oftalmología, Otorrinolaringología, Traumatología |
| `establecimiento` | Texto | Hospital de destino | Hospital Costero, Hospital de la Cordillera, Hospital del Norte, Hospital del Sur, Hospital del Valle |
| `fecha_entrada` | Fecha | Fecha de ingreso a la lista | Dentro del período de referencia |
| `fecha_salida` | Fecha | Fecha de egreso de la lista | Igual o posterior a `fecha_entrada`, vacía mientras el caso sigue abierto |
| `causal_salida` | Texto | Motivo del egreso | Atención realizada, Inasistencia, Renuncia voluntaria, Contacto no posible o Fallecimiento, vacía mientras el caso sigue abierto |

## Lectura

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

## Cita sugerida

Villarroel Tapia, P. (2026). *Lista de espera sintética* [conjunto de datos]. https://github.com/paulovillarroel/datasets
