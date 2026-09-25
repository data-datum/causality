# Causal Inference

Introducción práctica a la **inferencia causal** utilizando Python y el dataset **Titanic**.

Este repositorio acompaña un recorrido progresivo por los principales conceptos de causalidad, desde la formulación de una pregunta causal y la construcción de **DAGs (Directed Acyclic Graphs)** hasta la identificación y estimación de efectos causales.

El objetivo es aprender a distinguir entre **asociación y causalidad** y entender qué supuestos son necesarios para poder estimar un efecto causal a partir de datos observacionales.

---

## 📚 Contenidos

El repositorio está organizado como una serie de notebooks que construyen los conceptos de manera progresiva.

### 01 — Hipótesis causales y DAG

**Notebook:** `01_hipotesis_causales_DAG.ipynb`

Introducción al razonamiento causal a partir de una pregunta concreta sobre el dataset Titanic:

> **¿Cuál es el efecto causal de `Pclass` sobre `Survived`?**

En este notebook se trabaja sobre:

* Preguntas causales
* Tratamiento (*treatment*)
* Outcome
* Hipótesis causales
* Diferencia entre correlación y causalidad
* Variables causales
* DAGs (*Directed Acyclic Graphs*)
* Interpretación de las relaciones causales
* Construcción de un modelo causal inicial

---

### 02 — Confusores, mediadores y colisionadores

**Notebook:** `02_colisionadores_confusores_mediadores.ipynb`

Una vez construido el DAG, el siguiente paso es aprender cómo diferentes estructuras causales afectan el análisis.

Se estudian:

* **Confusores**
* **Caminos backdoor**
* **Mediadores**
* **Efecto total vs. efecto directo**
* **Colisionadores**
* Por qué no debemos ajustar automáticamente por todas las variables disponibles
* Criterio de ajuste (*adjustment*)
* Identificación de conjuntos de ajuste a partir del DAG

También se introduce **DoWhy** para comenzar a formalizar el proceso de identificación causal.

---

## 🧠 Conceptos principales

El recorrido se basa en una idea fundamental:

```text
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
Estimación del efecto
      ↓
Refutación y análisis de robustez
```

La separación entre **identificación** y **estimación** es especialmente importante.

### Identificación

La identificación responde:

> ¿Podemos identificar el efecto causal que nos interesa a partir de nuestras hipótesis causales y del DAG?

### Estimación

La estimación responde:

> Una vez identificado el efecto, ¿cuál es su valor utilizando los datos?

---

## 🛳️ Dataset

Los notebooks utilizan el dataset **Titanic**, que permite trabajar con variables como:

* `pclass`
* `survived`
* `sex`
* `age`
* `fare`
* `sibsp`
* `parch`
* entre otras.

El dataset se utiliza principalmente como recurso didáctico para construir ejemplos de razonamiento causal.

Es importante destacar que un DAG representa **supuestos causales**, no relaciones que puedan demostrarse únicamente observando las correlaciones presentes en el dataset.

---

## 🛠️ Tecnologías

El proyecto utiliza principalmente:

* Python
* Jupyter Notebook
* pandas
* NumPy
* seaborn
* matplotlib
* DoWhy

---

## 🚀 Instalación

Cloná el repositorio:

```bash
git clone https://github.com/data-datum/causality.git
cd causality
```

Instalá las dependencias necesarias:

```bash
pip install pandas numpy seaborn matplotlib dowhy jupyter
```

Luego iniciá Jupyter:

```bash
jupyter notebook
```

y ejecutá los notebooks en orden.

---

## 📂 Estructura del repositorio

```text
causality/
│
├── 01_hipotesis_causales_DAG.ipynb
├── 02_colisionadores_confusores_mediadores.ipynb
├── README.md
├── LICENSE
└── .gitignore
```

La estructura irá creciendo a medida que se incorporen nuevos conceptos y métodos de inferencia causal.

---

## 🔬 Próximos contenidos

El recorrido continuará con temas como:

* Identificación causal
* Criterio de backdoor
* Adjustment sets
* Average Treatment Effect (ATE)
* Estimación causal con DoWhy
* Diferentes métodos de estimación
* Refutación de estimaciones
* Análisis de robustez
* Propensity Scores
* Matching
* Inverse Probability Weighting
* Métodos de inferencia causal más avanzados

---

## 🎯 Objetivo del proyecto

El objetivo no es solamente aprender a utilizar una librería, sino desarrollar una forma de **pensar causalmente sobre los datos**.

En particular, el proyecto busca responder preguntas como:

* ¿Qué significa que una variable sea una causa?
* ¿Qué diferencia existe entre asociación y causalidad?
* ¿Qué variables debemos controlar?
* ¿Cuándo controlar una variable puede introducir sesgo?
* ¿Cómo podemos representar nuestros supuestos mediante un DAG?
* ¿Qué efectos causales pueden identificarse a partir de esos supuestos?
* ¿Cómo podemos estimar y evaluar esos efectos utilizando datos?

---

## 📖 Referencias

Algunas de las ideas desarrolladas en este proyecto están basadas en conceptos fundamentales de inferencia causal y modelos gráficos causales, particularmente en el trabajo de **Judea Pearl**.

También se utiliza **DoWhy** como herramienta práctica para la identificación, estimación y refutación de efectos causales.

---

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for details.

