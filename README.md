# PROYECTO 3 - Big Data   <h1>
# Tópicos especiales en telemática <h2>

## Miembros del equipo:
* Juan David Loaiza Botero
* Juan Camilo Gomez Ruiz
* Jorge Iván Ortiz Serna

## Problema elegido

### Problema1: Descubrimiento de temas basados en texto.
Se usarán técnicas de procesamiento natural de lenguaje para hacer análisis de texto en el dataset __airlines.csv__ con __Spark__, esto con la finalidad de reconocer en los registros del dataset las emociones que hay en los clientes de la aerolinea al dar sus opiniones del servicio y sus experiencias con el.

## Carga de datos en HDFS

```javascript
cargar_datos1 = sc.textFile("hdfs:///user/jgomez88/datasets/airlines.csv")


cargar_datos1.saveAsTextFile("hdfs:///user/jgomez88/BigDataProyecto_3")

```

## Leer datos en spark
```python
 >>> data = spark.read.load('/user/jgomez88/datasets/airlines.csv',format='csv', header=True)
 >>> data.show(10);
```
![data](http://img.fenixzone.net/i/IcTCMd7.png)

## Procesamiento de texto y limpieza para tranformación
* Código de limpieza

![limpieza](http://img.fenixzone.net/i/n9gukBw.png)

* Mostrar tabla

![Table](http://img.fenixzone.net/i/vBQGf1U.png)

* Generación de la nueva tabla con nuevos campos

![Generacion](http://img.fenixzone.net/i/s4IoRc1.png)

* Generar TFIDF

* LDA

![Generacion2](http://img.fenixzone.net/i/5I2iaLK.png)


![Generacion3](http://img.fenixzone.net/i/yWhHFeB.png)


* Tabla de registro para SparkSQL


## Modelo de analítica basado en Spark ML

### Clasificación de comentarios

Para el modelo de analítica clasificamos manualmente __450__ registros, esta clasificación se repartió entre los tres miembros del equipo, cada miembro verificó 150 registros y de acuerdo al comentario de cada cliente se clasifico como negativo, neutro y positivo. 

### Entrenamiento

Para el entrenamiento del modelo, vamos a usar la transformación del __80%__ (360 registros) de los comentarios realizados en el numeral anterior, así el modelo aprenderá que ciertas palabras están relacionadas con un tipo de comentario.

### Testeo

Para probar el modelo usaremos el __20%__ (90 registros) restante de los comentarios transformados, así verificaremos las precisión del modelo. 

## Visualización de resultados