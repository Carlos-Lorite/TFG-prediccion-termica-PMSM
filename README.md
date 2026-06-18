# Predicción térmica del rotor en un motor PMSM mediante aprendizaje automático

Este repositorio contiene el código completo desarrollado para el Trabajo Fin de Grado titulado **“Análisis avanzado de datos de un motor eléctrico mediante aprendizaje automático”**.

El objetivo del trabajo es estimar la temperatura del rotor de un motor síncrono de imanes permanentes (PMSM) a partir de variables eléctricas, mecánicas y térmicas registradas durante distintos perfiles de funcionamiento.

## Contenido del repositorio

* `Modelo_V7_TFG.ipynb`: notebook completo con el análisis, preparación de datos, generación de variables, entrenamiento del modelo residual V7, postprocesado y cálculo de métricas finales.

## Dataset utilizado

El conjunto de datos empleado corresponde al dataset público Electric Motor Temperature, disponible en [Kaggle](https://www.kaggle.com/datasets/wkirgsn/electric-motor-temperature/data)
Por motivos de tamaño y organización, el dataset no se incluye directamente en este repositorio. Para ejecutar el notebook, debe descargarse previamente el archivo de datos original y colocarse en la ruta indicada dentro del propio código.

## Modelo desarrollado

El modelo final corresponde a una arquitectura residual CNN-GRU-Attention. La red predice el residuo térmico entre la temperatura del rotor y la temperatura del diente del estator. La temperatura final se reconstruye sumando el residuo predicho a la referencia térmica.

El modelo utiliza ventanas temporales de 75 muestras y 65 variables de entrada, incorporando variables físicas derivadas y variables EWMA para representar parte de la memoria térmica del sistema.

## Resultados principales

En el conjunto de prueba, el modelo final obtiene:

* MAE: 1,951 ºC
* RMSE: 2,574 ºC
* Predicciones dentro de ±2 ºC: 61,02 %
* Predicciones dentro de ±5 ºC: 93,86 %

## Autor

Carlos Lorite Fuentes
Grado en Ingeniería Mecánica
Universidad de Málaga
