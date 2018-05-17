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
```javascript
data = spark.read.load('/user/jgomez88/datasets/airlines.csv',format='csv', header=True)

data.show(10);

![data](http://img.fenixzone.net/i/IcTCMd7.png)


```

## Procesamiento de texto y limpieza para tranformación

## Modelo de análitica basado en Spark ML

## Visualización de resultados