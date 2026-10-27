# Fundamentos de Machine Learning

**Escuela de ML Aplicado a Análisis de Estrellas Masivas y eventos de Microlente**

Este repositorio reúne los notebooks de la sesión *Fundamentos de Machine Learning* y del proyecto de la escuela. El hilo conductor es la estimación de parámetros estelares a partir de espectros de estrellas masivas: se parte con métodos clásicos de regresión sobre espectros sintéticos y se termina con una red neuronal convolucional evaluada en espectros observados.

## Notebooks

| | Notebook | Contenido | Abrir |
|---|---|---|---|
| 1 | [Regresión](regresion_MLvalpo.ipynb) | Predicción de la temperatura efectiva de estrellas Be con regresión lineal, árboles de decisión, random forest y gradient boosting. Métricas MSE, MAE y $R^2$. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rpezoa/mlvalpo/blob/main/regresion_MLvalpo.ipynb) |
| 2 | [Regresión de múltiples salidas](regresionMulti_MLvalpo_ipynb.ipynb) | Predicción simultánea de $T_\mathrm{eff}$ y $v \sin i$, optimización de hiperparámetros con validación cruzada y aplicación a cuatro espectros observados. Incluye actividades para completar. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rpezoa/mlvalpo/blob/main/regresionMulti_MLvalpo_ipynb.ipynb) |
| 3 | [Proyecto](proyecto_parametros_estelares.ipynb) | Inferencia de $T_\mathrm{eff}$, $\log g$ y tasa de pérdida de masa desde la línea H-alpha con una red convolucional 1D, y evaluación en 76 espectros observados. | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rpezoa/mlvalpo/blob/main/proyecto_parametros_estelares.ipynb) |

Los notebooks están pensados para seguirse en orden: cada uno supone los conceptos del anterior.

## Datos

| Conjunto | Descripción | Usado en |
|---|---|---|
| Espectros ZPEKTR | 10 691 espectros sintéticos de estrellas Be en la ventana 4460–4477 Å (línea He I 4471 Å), generados por PhD (c) Daniela Turis (IFA-UV) con el código ZPEKTR | 1, 2 |
| Espectros observados de estrellas Be | HD 60606, HD 212076, HD 158427 y HD 68980, en la misma ventana espectral | 2 |
| ISOSCELES | 10 000 espectros sintéticos de la línea H-alpha con velocidad de microturbulencia de 10 km/s, extraídos de la grilla ISOSCELES ([Araya et al. 2025](https://arxiv.org/abs/2511.03184)) | 3 |
| Espectros observados de estrellas masivas | 76 estrellas, 8 líneas por estrella | 3 |

Los archivos se descargan automáticamente desde Google Drive al ejecutar cada notebook; no es necesario descargarlos a mano.

## Ejecución

**Google Colab.** Basta con el botón *Open in Colab* de la tabla. Todas las dependencias vienen instaladas.

**Entorno local.** Se requiere Python 3.10 o superior:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn gdown jupyter
pip install tensorflow   # solo para el notebook 3
jupyter notebook
```

Si los datos ya están descargados, la variable de entorno `MLVALPO_DATA` puede apuntar a la carpeta que los contiene y los notebooks los leerán desde ahí en vez de descargarlos.

Los tres notebooks se verificaron con Python 3.13, scikit-learn 1.7 y TensorFlow 2.20. El notebook 2 incluye una búsqueda de hiperparámetros de gradient boosting que puede tardar más de 10 minutos en Colab.

## Licencia

Código bajo licencia [MIT](LICENSE). Los datos pertenecen a sus respectivos autores.

## Contacto

Repositorio mantenido por **Raquel Pezoa** (Departamento de Informática, Universidad Técnica Federico Santa María). Preguntas, sugerencias y colaboraciones son bienvenidas.
