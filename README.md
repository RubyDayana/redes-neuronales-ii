# Redes Neuronales II

Funciones de activación, backpropagation y clasificación binaria y multiclase (MNIST) con **NumPy**, **TensorFlow + Keras** y **PyTorch**. Continuación del taller [Redes Neuronales Básicas](https://github.com/RubyDayana/redes-neuronales-basicas).

**Universidad de Cundinamarca**
**CADI:** Deep Learning — Conceptos
**Estudiante:** Ruby Dayana Cárdenas Gómez
**Docente:** Nidia Stella García Roa

---

## ¿De qué trata?

En el taller anterior programé un perceptrón, una red de una capa y una red multicapa desde cero, y las probé con compuertas lógicas. Aquí tomo esos mismos modelos y los mejoro para resolver problemas reales, y luego construyo la misma red con dos herramientas profesionales. No se usan redes convolucionales.

| Notebook | Herramienta | Problema | Qué se hace |
|---|---|---|---|
| [`01 NumPyActivacionesBackpropBinaria.ipynb`](01%20NumPyActivacionesBackpropBinaria.ipynb) | Python + NumPy | Binario: diagnóstico de tumores (benigno / maligno) | Perceptrón, red de una capa y red multicapa rediseñados. Funciones Sigmoide y ReLU, retropropagación, entropía cruzada, mini-lotes, separación entrenamiento / prueba |
| [`02 MNISTTensorFlowKeras.ipynb`](02%20MNISTTensorFlowKeras.ipynb) | TensorFlow + Keras | Multiclase: dígitos escritos a mano (0–9) | Red densa 784 → 128 → 64 → 10 con softmax. Matriz de confusión, análisis de errores, experimento ReLU vs. Sigmoide |
| [`03 MNISTPyTorch.ipynb`](03%20MNISTPyTorch.ipynb) | PyTorch | Multiclase: dígitos escritos a mano (0–9) | La misma red replicada en PyTorch con el ciclo de entrenamiento escrito a mano. Comparación Keras vs. PyTorch |

## Abrir en Google Colab

| Notebook | |
|---|---|
| 1. NumPy: activaciones, backpropagation y clasificación binaria | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RubyDayana/redes-neuronales-ii/blob/main/01%20NumPyActivacionesBackpropBinaria.ipynb) |
| 2. MNIST con TensorFlow + Keras | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RubyDayana/redes-neuronales-ii/blob/main/02%20MNISTTensorFlowKeras.ipynb) |
| 3. MNIST con PyTorch | [![Abrir en Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/RubyDayana/redes-neuronales-ii/blob/main/03%20MNISTPyTorch.ipynb) |

Haz clic en el botón y luego en `Entorno de ejecución → Ejecutar todo`. No hay que instalar nada: Colab ya trae NumPy, TensorFlow y PyTorch. Los notebooks de MNIST tardan unos 2 minutos cada uno (menos si se activa la GPU en `Entorno de ejecución → Cambiar tipo de entorno`).

## Resultados

**Parte 1 — Clasificación binaria (569 tumores, 30 medidas, 20 % para prueba)**

| Modelo | Exactitud en prueba |
|---|---|
| Perceptrón (escalón) | 97.35 % |
| Red de una capa (sigmoide + backpropagation) | 99.12 % |
| Red multicapa con sigmoide | 98.23 % |
| Red multicapa con ReLU | 98.23 % |

Con la misma red, la versión con **ReLU** bajó de 0.10 de error en la época 13; la de sigmoide necesitó 42.

**Partes 2 y 3 — MNIST (60 000 imágenes de entrenamiento, 10 000 de prueba)**

| Framework | Red | Parámetros | Exactitud en prueba |
|---|---|---|---|
| TensorFlow + Keras | 784 → 128 ReLU → 64 ReLU → 10 softmax | 109 386 | 97.24 % |
| PyTorch | la misma | 109 386 | 97.46 % |

Los errores más comunes en ambas son entre dígitos que se parecen al escribirlos (5 y 3, 8 y 5, 4 y 9, 7 y 9).

## Archivos

| Archivo | Descripción |
|---|---|
| `01 NumPyActivacionesBackpropBinaria.ipynb` | Parte 1: modelos en NumPy, con sus resultados |
| `02 MNISTTensorFlowKeras.ipynb` | Parte 2: MNIST con Keras, con sus resultados |
| `03 MNISTPyTorch.ipynb` | Parte 3: MNIST con PyTorch, con sus resultados |
| `Informe_Redes_Neuronales_II.pdf` | Documento técnico con la explicación de los modelos, resultados y evidencias |
| `README.md` | Este archivo |
