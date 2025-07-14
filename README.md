# TelecomX_LATAM_parte2
Challenge del curso de DataScience con Python de Alura Latam, parte 2 Maching Learning.

## **Introducción.**

Se presenta el análisis de la empresa de telecomunicaciones TelecomX_LATAM, la cual esta perdiendo muchos clientes, nos solicitó que revisaramos sus datos, 
para  de ser posible que detectemos cual es la causa de que los clientes se este retirando de la compañia.


## **Instrucciones de uso**

* import pandas as pd
* import matplotlib.pyplot as plt
* import seaborn as sns
* import numpy as np
* Se debe dar click en cada una de las celdas del documento Googlecolab


## **Limpieza y tratamiento de datos**

* Se procedió a importar a un dataframe el archivo: 'TelecomX_Data' el cual viene de una API y esta en formato JSON.
* Se revisaron las primeras 5 lineas del dataframe.
* Por medio de df.info(), se obtuvo la información de que el df tiene 7267 lineas y 6 columnas, sólo las dos primeras columnas tiene información individual, en las restantes la información esta en forma de dicccionarios.
* Se procedió a extraer (normalizar) cada diccionario en un nuevo df, que al final se concatenaron con las dos primeras columnas, resultando en un df de 7267 lineas y 21 columnas.
* Se cambió el tipo de data de 'Charges.Total' a float64

  ## **Análisis y exploración de datos**
* Se generaron un dataframe para evasores y otro para usuarios que se mantinen, para compararlos respecto al tiempo que permanecen con el servicio(tenure).
 ![image](https://github.com/user-attachments/assets/75d7bee9-7a81-48a9-b5f7-cfba0660670d)
 Se observa que la mayoria de los usuarios evadidos se van al primer mes.

## **Maching Learning**

### Librerias usadas

* from sklearn.compose import ColumnTransformer
* from sklearn.preprocessing import OneHotEncoder
* from sklearn.compose import make_column_transformer
* from sklearn.model_selection import train_test_split
* from sklearn.dummy import DummyClassifier
* from sklearn.tree import DecisionTreeClassifier
* from sklearn.tree import plot_tree
* from sklearn.preprocessing import MinMaxScaler
* from sklearn.neighbors import KNeighborsClassifier
* from sklearn.ensemble import RandomForestClassifier
* from sklearn.metrics import confusion_matrix
* from sklearn.metrics import accuracy_score, precision_score, recall_score,f1_score
* from sklearn.model_selection import KFold,cross_validate
* from sklearn.model_selection import StratifiedKFold
* from imblearn.over_sampling import SMOTE
* from imblearn.pipeline import Pipeline as imbpipeline
* from imblearn.under_sampling import NearMiss
* import pickle

### Conclusiones

El modelo arbol fue el que mostró la mayor exactitud, como se aprecia en la siguiente tabla:

**Modelo árbol.**

La exactitud(accuracy) del modelo árbol es: 0.8017037387600567.

La precisión del modelo árbol  es: 0.6748768472906403.

La sensibilidad(recall) del modelo árbol  es: 0.48841354723707664.

La F1 del modelo árbol es: 0.5667011375387797.

**Modelo KNN**

La exactitud(accuracy) del modelo knn es: 0.73450070989115.

La precisión del modelo knn  es: 0.0.

La sensibilidad(recall) del modelo knn  es: 0.0.

La F1 del modelo knn es: 0.0.

Este modelo no generalizó bien el conjunto de datos de entrenamiento, por eso sólo mostró valores en la exactitud.

**Modelo random forest**

La exactitud(accuracy) del modelo rf es: 0.7747278750591576.

La precisión del modelo rf  es: 0.8057553956834532.

La sensibilidad(recall) del modelo rf  es: 0.19964349376114082.

La F1 del modelo rf es: 0.32

**Undersampling**
En vista de que los datos estan desbalanceados, se  procedio a usar el
método 'NearMiss' para balancear los datos.
Obteneniendose un nivel de confianza de : 

El intervalo de confianza es:[0.4860765166140574,0.9297569481391362],
y la siguiente matrix de confusíon :

          precision    recall  f1-score   support

               0       0.90      0.78      0.84      1552
               1       0.56      0.76      0.64       561

        accuracy                           0.77      2113
       macro avg       0.73      0.77      0.74      2113
    weighted avg       0.81      0.77      0.78      2113




<img width="515" height="433" alt="image" src="https://github.com/user-attachments/assets/a89b152d-e681-41bf-87bd-3499781e7fa2" />




