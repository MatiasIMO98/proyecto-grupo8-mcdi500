# Proyecto Grupo 8 — MCDI500

Análisis de la relación entre los patrones de uso de tecnología (pantallas, redes
sociales, videojuegos) y los indicadores de salud mental, estrés y calidad del
sueño, mediante un flujo de trabajo reproducible, documentado y colaborativo.

## Integrantes
- Abigail Roblez Chávez (@abda-abigail-github)
- Daniel Pérez Ramirez (@DanielRamirezPerez-github)
- Matias Manriquez Ortiz (@MatiasManriquezO-github)
- Roberto Sánchez Saldivia (@RobertSanchezS-github)

## Datos
- **Fuente:** Kaggle — *Mental Health and Technology Usage Dataset* (autor: waqi786).
  `https://www.kaggle.com/datasets/waqi786/mental-health-and-technology-usage-dataset`
- **Licencia:** verificar términos del autor en Kaggle antes de una redistribución pública.
- **Dimensiones:** 10.000 registros × 14 variables originales.
- **Variables:** `User_ID`, `Age`, `Gender`, `Technology_Usage_Hours`,
  `Social_Media_Usage_Hours`, `Gaming_Hours`, `Screen_Time_Hours`,
  `Mental_Health_Status`, `Stress_Level`, `Sleep_Hours`,
  `Physical_Activity_Hours`, `Support_Systems_Access`,
  `Work_Environment_Impact`, `Online_Support_Usage`.

## Estructura del repositorio
```
proyecto-grupo8-mcdi500/
├─ F1/
│  ├─ Data/raw/
│  │  └─ mental_health_and_technology_usage_2024.csv
│  └─ notebooks/
│     └─ S1_F1_Definicion.ipynb        Fase 1 — definición del problema y entorno
├─ F2/
│  └─ S1_F2_Preprocesamiento.ipynb     Fase 2 — obtención, limpieza y transformación
├─ F3/
│  └─ notebooks/
│     └─ Fase 3.md                     (pendiente: notebook de Fase 3)
├─ F4/
│  └─ notebooks/
│     └─ Fase 4.md                     (pendiente: notebook de Fase 4)
├─ docs/
│  ├─ Informe/
│  └─ Mapa Conceptual Proyecto/
├─ requirements.txt                    dependencias del proyecto (único, en la raíz)
└─ README.md                           este archivo
```

## Requisitos y ejecución
Python 3.11 o superior.

```bash
python -m venv .venv
source .venv/Scripts/activate      # Windows, Git Bash
# .venv\Scripts\Activate.ps1       # Windows, PowerShell
python -m pip install -r requirements.txt
python -m ipykernel install --user --name grupo8_mcdi500 --display-name "Python (grupo8-mcdi500)"
```

Ejecutar los notebooks en orden, desde la raíz del proyecto, seleccionando el
kernel `Python (grupo8-mcdi500)`:
1. `F1/notebooks/S1_F1_Definicion.ipynb`
2. `F2/S1_F2_Preprocesamiento.ipynb`

## Documentación (docs/)
Cada tipo de documento va en su propia subcarpeta, para no mezclar archivos:
- `docs/Mapa Conceptual Proyecto/`
- `docs/Informe/`
- `docs/Referencias/` (crear si se necesita)

## Convención de commits

Cada commit debe empezar con un prefijo que indique el **tipo de cambio**, seguido
de dos puntos y una descripción breve en presente. Lo que decide el prefijo es
**qué archivo cambia y por qué**, no si el cambio "corrige algo" o no.

### Definición de cada prefijo

| Prefijo | Úsalo cuando... | No lo uses para... |
|---|---|---|
| `docs` | subes o editas documentación: README, mapa conceptual, informe, comentarios explicativos, bitácora de decisiones | cambios en el dataset o en código ejecutable (aunque el archivo sea texto) |
| `data` | agregas, actualizas o reemplazas el dataset (archivos de datos, diccionario de variables, fuente/licencia) | limpiar o transformar el dataset dentro del código (eso es `feat` o `fix`) |
| `feat` | implementas algo nuevo: una función, un notebook, un análisis, una carpeta de fase | corregir algo que ya existía y no funcionaba (eso es `fix`) |
| `fix` | corriges un error real en el código, en la estructura de archivos o en los datos (duplicados, rutas rotas, archivos que no debían subirse) | mejorar redacción o completar información en documentación (eso es `docs`) |
| `test` | agregas o ejecutas validaciones (nulos, duplicados, rangos, tipos de dato, casos límite) | escribir la función que se está validando (eso es `feat`) |

### Ejemplos de commits

| Prefijo | Mensaje de commit | Qué cambia realmente |
|---|---|---|
| `docs` | `docs: agrega mapa conceptual v1 y v2` | se sube un archivo de documentación (imagen del mapa) |
| `docs` | `docs: actualiza README con estructura completa` | se edita texto explicativo, no código ni datos |
| `data` | `data: incorpora dataset mental_health_and_technology_usage_2024.csv` | se agrega el archivo de datos original |
| `feat` | `feat: implementa funciones de preprocesamiento` | se escribe código nuevo (funciones en `src/procesamiento.py`) |
| `feat` | `feat: crea estructura de carpetas F3 y F4` | se crea algo que no existía antes en el proyecto |
| `fix` | `fix: elimina requirements.txt duplicados en F1 y F2` | se corrige un problema real en la estructura de archivos |
| `fix` | `fix: agrega .gitignore y elimina archivos .DS_Store` | se corrige algo que no debía estar versionado |
| `test` | `test: valida nulos, duplicados y rangos del dataset procesado` | se ejecutan validaciones sobre datos ya existentes |

## Decisiones técnicas
- **Limpieza:** [completar: qué encontraron al revisar nulos/duplicados/rangos]
- **Transformación:** [completar: qué transformaciones aplicaron y por qué]
- **Reproducibilidad:** entorno virtual `.venv` + `requirements.txt` (un solo archivo en la raíz).
