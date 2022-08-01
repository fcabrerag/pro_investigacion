# pro_investigacion



## 1.- Análisis exploratorio de datos:
### 1.1.- Gráficos distancia acumulada /tiempo de buses de un servicio de bus:
Permiten observar la distancia recorrida por un bus(de un servicio de bus específico) a lo largo del tiempo(hr). Además, es posible realizar zoom en intervalos de distancia y tiempo específicos, buscando patrones para viajes de buses. Mi trabajo de investigación de tesis de magíster trata el problema de bunching bus, por lo que se desea encontrar características comunes para los viajes de buses que se encuentren viajando cercanamente o viajes de buses(representados por una línea) que se intersecten entre ellos , lo que inmediatamente indicaría presencia del fenómeno. En la imagen se visualizan los viajes de buses(resprestenados cada uno por una serie) en el intervalo comprendido entre las 09:30 horas y las 13:30 horas para los cuatro lunes del mes de Agosto de 2018.
![](https://github.com/fcabrerag/pro_investigacion/blob/main/imagenes/fig_4.1_2.png)

El lenguaje de programación utilizado es Python. Para el tratamiento de datos es usada la librería pandas y en la visualización de resultados la librería Matplotlib.

### 1.2.- Gráficos de contabilización de casos de bunching para un período de tiempo:
Contabilización de casos para dos períodos de tiempo determinados (meses de Julio y Agosto). Para ambos meses se determinan los paraderos que poseen mayor cantidad de casos positivos de bunching, durante cada uno de los meses presentando casos positivos vs negativos (al situarlos en la misma barra, con efecto de comparación). El valor 1 (color anaranjado) indica existencia de bunching y el valor 0 (color azul) que no existe bunching para ese muestreo de GPS.

![](https://github.com/fcabrerag/pro_investigacion/blob/main/imagenes/fig_3.3.png)

El lenguaje de programación utilizado es Python. Para el tratamiento de datos es usada la librería pandas y en la visualización de resultados la librería Seaborn.

## 2.- Limpieza y tratamiento de datos faltantes:
### 2.1.- Limpieza de datos:
Se busca visualizar todos los viajes de los buses usando las variables de longitud y latitud. La finalidad es encontrar los límites a nivel de coordenadas, localizando posibles viajes de buses que circularon por lugares distintos a su ruta. El gráfico escogido para este propósito es un
scatterplot. El eje X de coordenadas representa la longitud y el eje Y de coordenadas representa la latitud. Son detectados viajes de buses que describen rutas que se escapan del rango de valores aceptados como válidos y que deben ser eliminados con la finalidad de homogeneizar los viajes del servicio de bus.En la figura se muestra la aplicación de un filtro de eliminación de registros de viajes para un grupo de buses que su ruta que sobrepasa su límite de longitud (valores superiores a -70.64)
![](https://github.com/fcabrerag/pro_investigacion/blob/main/imagenes/filtro_datos.png)


### 2.2.- Interpolación lineal de datos faltantes:
El muestreo de datos GPS no ha sido capturado con la misma regularidad para todos los viajes de bus, encontrando tiempos con valores superiores a 30 segundos (que es el tiempo de muestreo definido entre cada registro de GPS).Es aplicado un algoritmo encargado de generar nuevos registros de fechas de muestreo GPS con la regularidad correcta. Las variables de latitud y longitud nuevas son completadas a través de la interpolación lineal, que calcula los valores intermedios entre dos puntos con un pequeño error. La figura realiza una comparativa antes y posterior a la regularización del viaje. Los datos corresponden a un día deJulio de 2018 para un viaje de bus (entre las 12:10 y 12:14 horas).

![](https://github.com/fcabrerag/pro_investigacion/blob/main/imagenes/fig_3.2.png)

El lenguaje de programación utilizado es Python. Para el tratamiento de datos es usada la librería pandas y en la visualización de resultados la librería Matplotlib.

## 3.- Visualización de resultados de una red neuronal LSTM:
Posterior a la construcción de una red neuronal LSTM (de arquitectura Many-to-One),a través de loops se generan predicciones de los viajes de un bus, en un intervalo de una hora, para los días que corresponden para el conjunto de test del dataset. Estas predicciones se guardan en archivos de textos , los cuales son leídos a través de un script en Python que se encarga de cargar estos datos y generar las imagenes las cuales son guardadas en un directorio especifico(es un proceso masivo). En la figura se muestran las predicciones para un día puntual en un intervalo de una hora, comparando las predicciones de la red (imagen izquierda) contra los datos reales(imagen derecha).

![](https://github.com/fcabrerag/pro_investigacion/blob/main/imagenes/resultados_red_mo.png)

El lenguaje de programación utilizado es Python. Para el tratamiento de datos es usada la librería pandas y en la visualización de resultados la librería Matplotlib.




