# Causal Inference

Introducción práctica a la **inferencia causal** con Python, usando el dataset **Titanic**.

Este repositorio acompaña un recorrido progresivo por los principales conceptos de causalidad: desde formular una pregunta causal y construir un **DAG** (*Directed Acyclic Graph*), hasta identificar y estimar efectos causales con distintos métodos sobre datos observacionales.

El objetivo es aprender a distinguir entre **asociación y causalidad** y entender qué supuestos hacen falta para estimar un efecto causal.

---

## 📚 Contenidos

Los notebooks están pensados para leerse **en orden**: cada uno retoma lo anterior.

| # | Notebook | Tema |
|---|----------|------|
| 01 | [`01_hipotesis_causales_DAG.ipynb`](01_hipotesis_causales_DAG.ipynb) | Preguntas causales, hipótesis y DAGs |
| 02 | [`02_colisionadores_confusores_mediadores.ipynb`](02_colisionadores_confusores_mediadores.ipynb) | Confusores, mediadores, colisionadores y criterio de ajuste |
| 03 | [`03_PS_IPW.ipynb`](03_PS_IPW.ipynb) | Propensity Score e Inverse Probability Weighting |
| 04 | [`04_ATE_ATT_ATC_CATE.ipynb`](04_ATE_ATT_ATC_CATE.ipynb) | ATE, ATT, ATC y CATE |
| 05 | [`05_propensity_score_matching.ipynb`](05_propensity_score_matching.ipynb) | Propensity Score Matching |
| 06 | [`06_metalearners.ipynb`](06_metalearners.ipynb) | Metalearners para efectos heterogéneos |
| 07 | [`07_DiD.ipynb`](07_DiD.ipynb) | Diferencias en diferencias (DiD) |

### 01 — Hipótesis causales y DAG

Punto de partida: una pregunta concreta sobre el Titanic.

> **¿Cuál es el efecto causal de `Pclass` sobre `Survived`?**

- Preguntas causales, tratamiento (*treatment*) y outcome
- Diferencia entre correlación y causalidad
- Hipótesis causales y construcción de un DAG inicial
- Interpretación de las relaciones causales

### 02 — Confusores, mediadores y colisionadores

- Confusores y caminos *backdoor*
- Mediadores: efecto total vs. efecto directo
- Colisionadores
- Por qué **no** conviene ajustar por todas las variables disponibles
- Criterio de ajuste e identificación de *adjustment sets* a partir del DAG
- Primer contacto con **DoWhy** para formalizar la identificación

### 03 — Propensity Score e IPW

- Qué es el propensity score y cómo estimarlo
- Ponderación por probabilidad inversa (*Inverse Probability Weighting*)
- Balance de covariables y estimación del efecto

### 04 — ATE, ATT, ATC y CATE

- Distintos estimandos causales: efecto promedio en toda la población (**ATE**), en tratados (**ATT**) y en controles (**ATC**)
- Efectos condicionales por subgrupos (**CATE**)
- Cuándo importa cada uno según la pregunta

### 05 — Propensity Score Matching

- Emparejamiento de unidades tratadas y controles según su propensity score
- Evaluación de la calidad del matching
- Estimación del efecto a partir de la muestra emparejada

### 06 — Metalearners

- Estimación de efectos heterogéneos con modelos de machine learning
- Enfoques tipo *S-learner*, *T-learner* y *X-learner*

### 07 — Diferencias en diferencias (DiD)

- Diseños con datos antes/después y grupo tratado/control
- Supuesto de tendencias paralelas
- Estimación del efecto del tratamiento

---

## 🧠 Hilo conductor

```
Pregunta causal
      ↓
Hipótesis causales
      ↓
DAG
      ↓
Confusores / Mediadores / Colisionadores
      ↓
Identificación del efecto
      ↓
Estimación (IPW, matching, metalearners, DiD...)
      ↓
Refutación y análisis de robustez
```

La separación entre **identificación** y **estimación** es central:

- **Identificación:** ¿podemos identificar el efecto causal que nos interesa a partir de nuestras hipótesis y del DAG?
- **Estimación:** una vez identificado, ¿cuál es su valor usando los datos?

---

## 🛳️ Dataset

Los notebooks usan el dataset **Titanic**, con variables como `pclass`, `survived`, `sex`, `age`, `fare`, `sibsp` y `parch`, entre otras.

Se usa como recurso didáctico. Un DAG representa **supuestos causales**, no algo que pueda demostrarse solo mirando las correlaciones del dataset.

---

## 🛠️ Tecnologías

- Python
- Jupyter Notebook
- pandas, NumPy
- seaborn, matplotlib
- scikit-learn
- DoWhy

---

## 🚀 Instalación

Cloná el repositorio:

```bash
git clone https://github.com/data-datum/causality.git
cd causality
```

Creá un entorno virtual (opcional, pero recomendado) e instalá las dependencias:

```bash
python -m venv .venv
source .venv/bin/activate   # En Windows: .venv\Scripts\activate

pip install pandas numpy seaborn matplotlib scikit-learn dowhy jupyter
```

Iniciá Jupyter y ejecutá los notebooks en orden:

```bash
jupyter notebook
```

---

## 📂 Estructura del repositorio

```
causality/
├── 01_hipotesis_causales_DAG.ipynb
├── 02_colisionadores_confusores_mediadores.ipynb
├── 03_PS_IPW.ipynb
├── 04_ATE_ATT_ATC_CATE.ipynb
├── 05_propensity_score_matching.ipynb
├── 06_metalearners.ipynb
├── 07_DiD.ipynb
├── LICENSE
└── README.md
```

---

## 🎯 Objetivo del proyecto

No se trata solo de aprender a usar una librería, sino de desarrollar una forma de **pensar causalmente sobre los datos**. En particular, buscamos responder:

- ¿Qué significa que una variable sea causa de otra?
- ¿Qué diferencia hay entre asociación y causalidad?
- ¿Qué variables debemos controlar y cuándo controlar puede introducir sesgo?
- ¿Cómo representamos nuestros supuestos con un DAG?
- ¿Qué efectos pueden identificarse a partir de esos supuestos?
- ¿Cómo estimamos y evaluamos esos efectos con datos?

---

## 📖 Referencias

- Judea Pearl, trabajo fundacional en modelos gráficos causales.
- [DoWhy](https://github.com/py-why/dowhy): librería para identificación, estimación y refutación de efectos causales.

---

## 📄 Licencia

Este proyecto está bajo la licencia MIT. Ver el archivo [`LICENSE`](LICENSE) para más detalles.
