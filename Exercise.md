---
title: "Práctica 1: Programación en R"
author: "Probabilidad y Estadística"
output:
  pdf_document: default
  html_document:
    df_print: paged
  word_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```

## Introducción

El objetivo de esta práctica es realizar un estudio muy superficial de modelos de regresión simple. Para ello, necesitaremos un conjunto de datos (*dataset*) sobre el que hacer el estudio. En la primera parte de la práctica, cargaremos dicho *dataset* y realizaremos una exploración estadística de ellos. En la segunda parte, realizaremos un estudio de regresión más específico. 

## Información del *dataset*

El dataset elegido es "*Boston Housing*". Consiste en un *dataset* público con información de viviendas en Boston. En concreto, el *dataset* contine las siguientes columnas:

* **CRIM**: Per capita crime rate by town
* **ZN**: Proportion of residential land zoned for lots over 25,000 sq. ft
* **INDUS**: Proportion of non-retail business acres per town
* **CHAS**: Charles River dummy variable (= 1 if tract bounds river; 0 otherwise)
* **NOX**: Nitric oxide concentration (parts per 10 million)
* **RM**: Average number of rooms per dwelling
* **AGE**: Proportion of owner-occupied units built prior to 1940
* **DIS**: Weighted distances to five Boston employment centers
* **RAD**: Index of accessibility to radial highways
* **TAX**: Full-value property tax rate per $10,000
* **PTRATIO**: Pupil-teacher ratio by town
* **B**: 1000(Bk - 0.63)?, where Bk is the proportion of [people of African American descent] by town
* **LSTAT**: Percentage of lower status of the population
* **MEDV**: Median value of owner-occupied homes in $1000s```

El *dataset* lo cargaremos en R mediante la instalación de un paquete y su posterior importación:
```{r pressure, eval=TRUE}
#install.packages("mlbench")
library(mlbench)
```

Ya cargado en R, procedemos a guardar el *dataset* en la variable $\tt housing$ para que realicéis el resto de la práctica sobre ella:
```{r, eval=TRUE}
data("BostonHousing")
housing <- BostonHousing
```

## Información de la práctica.
* La práctica se calificará sobre 10 puntos.
* La práctica se resuelve sobre este mismo código.
* Antes de entregarlo, habrá que cambiar el nombre del fichero, sustituyendo *nombre1* y *apellido1* por los propios del alumno.
* Si el alumno considera relevante la instalación de alguna librería extra que pueda mostrar mejores resultados o gráficos, es libre para hacerlo. Puntuará más si se realiza un trabajo óptimo en esta parte.
* Sobre todo en la parte final (regresión), puntuará más aquellos comentarios del alumno que muestren haber investigado el significado de todos los análisis realizados.
* Si el alumno se encuentra con errores durante la ejecución del código, tiene que aprender a lidiar con ellos como futuro ingeniero informático.
* Es recomendable consultar los diferentes comandos, así como nuevos comendos y librerías, através de buscadores, que os llevará a paginas web adecuadas de programación en R.

## 1) Análisis exploratorio inicial: 
Se pide utilizar los comandos $\tt str, head, dim, summary$ sobre $\tt housing$ para explorar distribución inicial de los datos en el *dataset*.

## 2) Análisis exploratorio de la variable objetivo:
En esta práctica, trataremos de predecir el valor del precio medio de la vivienda MEDV. Para ello, primero exploraremos la distribución de sus datos. Se pide dibujar un histograma, calcular asimetría y apuntamiento de MEDV. Se pide dibujar un boxplot, calcular los cuartiles y los percentiles 10-90 sobre MEDV. Se pide describir los elementos más importantes de ambas gráficas.

## 3) Correlación entre variables: 
Lo primero es que hay que tener en cuenta solo las variables cuantitativas. Se recomienda calcular la matriz de correlaciones de las variables cuantitativas con el comando $\tt cor$.Además se pide utilizar el comando $\tt corrplot$ de la libreria $\tt corrplot$, y la librería $\tt RColorBrewer$ (que posiblemente tengais que instalar) para mostrar graficamente las correlaciones entre todas las variables cuantitativas. Se pide describir los elementos de la gráfica que aportan mayor información.NOTA: para poder trabajar tendreis que crear una variable auxiliar para eliminar las variables cualitativas

## 4) Regresiones lineales simples:
Se pide escoger las variables independientes TAX y RM y realizar dos regresiones simples con cada una de ellas sobre la variable dependiente MEDV. Se pide calcular la recta de regresión, dibujar los *scatterplots* de cada variable independiente con MEDV y la recta de regresión resultante sobre cada *scatterplot*, para ello habrá que instalar la libreria $\tt ggplot2$. Finalmente describir brevemente el resultado de este análisis, calcular el coeficiente de correlación y la variabilidad explicada, y comentar los resultados obtenidos.

## 5) Análisis de los residuos:
Se pide mostrar en un *scatterplot* los residuos $e_i$ (eje-x) y la predicción que hace la recta de regresión de la variable independiente RM respecto a la variable MEDV con cada punto $\hat{y}_i$ (eje-y), también llamada variable ajustada. Se pide realizar un histograma de los residuos exclusivamente. Se pide investigar el significado y la importancia de este gráfico y comentarlo brevemente.Para los residuos, se han de seguir los siguientes supuestos:Los ei(residuos) deben seguir una distribución normal con mu=0 y desviación típica constante, y tienen que ser lineales


Comentarios del alumno (máximo 100 palabras): 


## 6) Regresión lineal múltiple:
Se pide realizar una regresión lineal múltiple con las dos variables independientes TAX y RM a la vez sobre la variable MEDV. Se pide, además, realizar un análisis de los residuos, similar al realizado en el apartado anterior, y comentarlo.




