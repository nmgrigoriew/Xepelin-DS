# Xepelin-DS

Este repositorio contiene la solución propuesta para: Prueba DS Xepelin.

Fue desarrollado mediante un Jupyter Notebook el cual se ejecuto y desarrollo utilizando Google Colab.

Dentro del desarrollo de este Notebook se encuentra el analisis exploratorio, limpieza y procesamiento de los datos. Junto a esto esta el desarrollo del modelo seleccionado para llevar a cabo la predicción solicitada.

Para este caso en específico, luego de analizar los datos y su distribución es que se seleccionó predecir el dinero que moverá Xepelin en Octubre mediante la aplicacion de series de tiempo. En especifico, se aplico la librería Prophet, la cual es ampliamente utilizada para la predicción de series de tiempo en diferentes ambitos como por ejemplo las ventas.

## Supuestos

Status 'FAILED' se consideraron como no procesados dentro del financiamiento por parte de Xepelin por lo que no se consideraron dentro de el calculo del movimiento para el mes de Octubre. Esto quiere decir, que se extrajeron los datos con status = 'FAILED' de la base.

Se llevaron a cabo dos casos, uno de ellos agrupando los montos financiados por Xepelin de manera mensual y el otro caso asocia el monto asociado por día.

Para la predicción mensual se sumaron las facturas de cada mes asociado a estas. Se considero utilizar aquellas facturas con status = 'PROCESSING'. Estas fueron incorporadas al último mes del cual se tiene información, en este caso Septiembre. Para incorporarlo se tomo en cuenta la proporcionalidad de facturas pagadas con aquellas rechazadas, con esto en mente se calcula el promedio de todas las facturas 'PROCESSING' y se le aplica la proporcionalidad para ser posteriormente incorporado el valor a los datos.

Para la predicción diaria, se tomaron los datos disponibles y se agruparon en base a los días que se tienen en la base de datos para cada día. En este caso, se decidió no incorporar aquellas facturas con status 'PROCESSING' para la predicción.


## Conclusiones

En particular para mejorar el modelo presentado, se requeriria para ambos casos (mensual o diario) recopilar una mayor cantidad de información para de estar manera mejorar el desempeño de la predicción. Una vez implementado el producto la generación y aplicación de los nuevos datos irá continuamente entregando una mayor cantidad de herramientas para su perfeccionamiento. Además de esto, el conocimiento obtenido por el modelo en terminos de noción sobre la cantidad de dinero que moverá Xepelin para el mes de Octubre 2021 se considera como logrado. De igual forma los periodos analizados son acotados para llevar a cabo un analisis con series de tiempo a cabilidad.

Para lo que respecta otra arista que puede ser explorada en el futro, que sería la aplicacion de un modelo de Machine Learning como por ejemplo XGBoost, Random Forest o Regresión Logistica. Para ello idealmente se considera incorporar a la base de datos una mayor cantidad de variables. Estas nuevas variables pueden ser como por ejemplo el comportamiento de un cliente, historial de pago, historial crediticio. Además de variables que esten directamente relacionadas con el cliente y/o la empresa se recomienda también la incorporación de variables externas como lo son la tasa de interes, estado de la industria en especifico del cliente en cuestión, entre otras.

El implementar el modelo para este nuevo producto entregará nociones respecto al flujo que se espera para el mes siguiente, con ello se preveen distintas situaciones y decisiones con las cuales se logra anteponer al escenario futuro. Pero, actualmente dada la cantidad de datos tanto como para llevar acabo el entrenamiento del modelo es que a medida que pase el tiempo de la implementacion se van a tener más datos para comparar el desempeño del modelo como para ingestar estos a la base para mejorar la prediccion.
