# Python Forecasting

Estas son notas para trabajar modelos de predicción con python 
basadas en el libro "Introduction to time series forecasting with python"

python3.9 -m venv "py39"

source ~/py39/bin/activate

dentro de el entorno virtual "py39" corremos:

pip install jupyterlab scipy scikit-learn pandas statsmodel matplotlib selenium bs4

Pandas es una librería que nos proporciona métodos para cargar y manejar datos en python, contiene estructuras como "DataFrame" y "series" para representar datos en python

http://pandas.pydata.org/

Pandas Support for Time Series:

http://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html

statsmodels es una librería que proporciona métodos para análisis estadístico, autoregresion, arima, promedio movil, etc.

http://statsmodels.sourceforge.net/

http://statsmodels.sourceforge.net/stable/tsa.html

scikit-learn es una librería para aprendizaje de máquina

http://scikit-learn.org/

Ahora podemos activar el entorno de JupyterLab y accederlo desde un navegador para continuar con la prueba de librerias

Corremos el jupytelab, desde el entorno
~~~
jupyter-lab
~~~
Y accedemos a la dirección que nos indica desde el navegador.

# C.2 What is time series forecasting?

La predicción en series de tiempo es una parte importante del aprendizaje de machina (machine learning) que es a veces olvidada, muchos problemas de predicción tienen una componente temporal, estas componentes temporales hace que los problemas sean mas complejos lo cual ocasiona que no sean tratados con la importancia que requieren

Un conjuto de datos (dataset) para aprendizaje de maquina es solo una colección de observaciones, para predecir el futuro, todas las observaciones tienen que ser tratadas de igual manera.

Una serie de tiempo es una colección de observaciones tomadas de manera secuencial en el tiempo

## Analisis de series de tiempo vs Predicción de series de tiempo.

En el análisis de series de tiempo se requiere una comprensión del dataset para realizar la predicción, la serie de tiempo es modelada y analizada para obtener mejores predicciones en terminos de patrones estacionales, tendencias y relaciones a factores externos, como por ejemplo los aumentos de consumo electrico durante el invierno o el verano debidos al uso de la calefacción.

En contraste la prediccion en series de tiempo usa la información de manera secuencial para predecir los valore futuros de esa serie.

Cuando usamos estadística clásica, nuestra primera preocupación es el análisis de la serie de tiempo, para el desarrollo de modelos matemáticos que nos permitan la predicción. La calidad del modelo determina la calidad de la predicción.

## Prediccion en series de tiempo

Hacer predicciones en el tiempo es llamado extrapolación en el manejo estadístico de la series de tiempo. La predicción en series de tiempo implica desarrollar modelos que cubran los datos históricos y usarlos para predecir los futuros. El futuro es completamente desconocido y solo puede ser estimando a partir de la informació histórica.

La habilidad de un modelo de predicción es determinada por su desempeño para predecir el futuro. Esto tiene el costo de explicar como se realizo  una proyección, cuales son los intervalos de confianza y las causas que originan la serie de tiempo. 

## Componentes de una serie de tiempo

* Nivel: Los valores base de la serie si es una linea recta
* Tendencia: El opcional y generalmente lineal comportamiento del  crecimiento o decrecimiento de la serie en el tiempo.
* Estacionalidad: Los patrones repetitivos o ciclos en el tiempo.
* Ruido: Las variaciones en la observaciones que no pueden ser explicadas por el modelo. 

Todas las series de tiempo tienen estos elementos. 

Los elementos principales de muchas series de tiempo son la tendencia y la estacionalidad, otra característica importante es que las observaciones cercanas en el tiempo tienden a estar correlacionadas. 

These constituent components can be thought to combine in some way to provide the observed time series. Assumptions can be made about these components both in behavior and in how they are combined, which allows them to be modeled using traditional statistical methods. These components may also be the most effective way to make predictions about
future values, but not always. In cases where these classical methods do not result in effective performance, these components may still be useful concepts, and even input to alternate methods.
The decomposition of time series into level, trend, seasonality and noise is covered more in Chapter 12.

# Ch.3 Series de tiempo como aprendizaje supervisado. 


# Ch.4 Data preparation

## Cargar y explorar series de tiempo

* Vamos a utilizar la librería de pandas para leer datos en formato csv
* vamos a obtener datos usando fechas
* como utilizar estadisticas en los datos.

Primero descargamos un dataset con los nacimientos de mujeres en california en 1959

~~~
https://raw.githubusercontent.com/jbrownlee/Datasets/master/daily-total-female-births.csv
~~~



# Ch. 5 Basic feature engineering (p26)


A time series dataset must be transformed to be modeled as a supervised learning problem.
That is something that looks like:

~~~
time 1, value 1
time 2, value 2
time 3, value 3
~~~

to:
~~~
input 1, output 1
input 2, output 2
input 3, output 3
~~~

So that we can train a supervised learning algorithm. Input variables are also called features in the field of machine learning, and the task before us is to create or invent new input features from our time series dataset. Ideally, we only want input features that best help the learning methods model the relationship between the inputs (X) and the outputs (y) that we would like to predict. In this tutorial, we will look at three classes of features that we can create from our time series dataset:

* Date Time Features: these are components of the time step itself for each observation.
* Lag Features: these are values at prior time steps.
* Window Features: these are a summary of values over a fixed window of prior time steps.


~~~
 https://github.com/Kanbc/ar-model-python/blob/master/data/daily-minimum-temperatures.csv
~~~


