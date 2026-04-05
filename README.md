# Predicción de valor de vivienda — California Housing

**Curso:** Aprendizaje de Máquina Aplicado — EAFIT 2026  
**Estudiantes:** Sofia Rodriguez · Mariana Gutierrez · Esteban Giraldo
**Dataset:** California Housing (scikit-learn)  
**Tarea:** Regresión supervisada  
**Semilla global:** `RANDOM_STATE = 42`

---

## Descripción

Proyecto que estima el valor mediano de vivienda por distrito censal
en California a partir de 8 variables socioeconómicas y geográficas
del censo de 1990, siguiendo el flujo de trabajo CRISP-DM.

**Pregunta:** ¿Es posible estimar el valor mediano de vivienda de un
distrito censal con un MAE menor al 20% del valor mediano observado?

---

## Estructura del repositorio

```text
ml-project/
├── README.md              # Punto de entrada del repositorio. Explica el proyecto,
│                          # cómo reproducirlo y el estado de cada entrega
├── environment.yml        # Define el entorno de conda con todas las dependencias
│                          # necesarias para reproducir el proyecto
│
├── data/
│   └── README.md          # dataset que se está utilizando
│
├── notebooks/
│   └── 01_eda_baseline.ipynb  # Notebook principal de la Entrega 1: carga de datos,
│                              # revisión de calidad, EDA, separación train/test
│                              # y baseline reproducible
│
├── figures/               # Gráficas generadas automáticamente por el notebook
│   ├── fig1_target_dist.png   # Histograma y boxplot de la variable objetivo
│   ├── fig2_features_dist.png # Distribución de los 8 features
│   ├── fig3_correlations.png  # Matriz de correlaciones de Pearson
│   └── fig4_map.png           # Distribución geográfica del valor de vivienda
│
├── report/
│   ├── datacard.md        # Descripción estructurada del dataset: fuente, variables,
│   │                      # limitaciones y riesgos potenciales
│   └── reporte_entrega1.pdf   # Reporte técnico completo de la Entrega 1
│
├── poster/                # Vacío por ahora. Contendrá la síntesis visual
│                          # del proyecto para la Entrega 3
│
└── src/                   # Funciones reutilizables
```
---

## Prerequisitos

Antes de comenzar necesitas tener instalado:

- [conda](https://docs.anaconda.com/miniconda/) (Miniconda o Anaconda)
Con esta herramienta gestionamos el entorno y las dependencias.

Para verificar que los tienes disponibles ejecuta:

    conda --version

## Cómo reproducir los resultados

### 1. Clona el repositorio
```bash
git clone https://github.com/AnaSofiR/ml-project.git
```

### 2. Crea y activa el entorno
```bash
    conda env create -f environment.yml
    conda activate ml-project
```

Deberías ver (ml-project) al inicio de tu terminal.
Si el entorno ya existe y quieres recrearlo:
    conda env remove -n ml-project
    conda env create -f environment.yml

### 3. Lanza Jupyter
    jupyter notebook

Esto abre el navegador automáticamente.
Si no abre, copia la URL que aparece en la terminal.

### 4. Ejecuta el notebook
Abre notebooks/01_eda_baseline.ipynb
Ejecuta todas las celdas con Kernel > Restart & Run All

Las figuras se guardan automáticamente en figures/

---

## Resultados por entrega

### Entrega 1 — Baseline
| Modelo    | MAE        | RMSE       | R²     |
|-----------|------------|------------|--------|
| Baseline  | $90,607    | $114,486   | ~0.0   |

### Entrega 2 — Comparación de modelos
| Modelo    | MAE | RMSE | R² |
|-----------|-----|------|----|
| *Pendiente* | — | —  | —  |

### Entrega 3 — Modelo final
| Modelo    | MAE | RMSE | R² |
|-----------|-----|------|----|
| *Pendiente* | — | —  | —  |

---

## Referencias

- Pace, R.K. y Barry, R. (1997). Sparse Spatial Autoregressions.
  *Statistics & Probability Letters*, 33, 291–297.
- Pedregosa et al. (2011). Scikit-learn: Machine Learning in Python.
  *JMLR*, 12, 2825–2830.
- James et al. (2021). *An Introduction to Statistical Learning*. Springer.