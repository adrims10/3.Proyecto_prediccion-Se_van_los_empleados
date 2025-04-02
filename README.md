![Clasificacion](https://github.com/user-attachments/assets/316d013a-7709-4531-907a-70d3bded555a)


# Predicción de Retención de Empleados 🏢

Dados una serie de datos nos vamos a enfrentar a  intentar predecir si un empleado se va a ir de la empresa o no.

En este proyecto, vamos a enfrentarnos a la tarea de desentrañar patrones, analizar tendencias y construir un modelo que pueda predecir si un empleado permanecerá o decidirá decir adiós segun una serie de variables dadas.

Vamos a ir comparando varios modelos predictivos para ver cual es el modelo que mejor funciona para acabar montando nuestro predictor.


## 🗂️ Estructura del Proyecto

    ├── notebooks/           # Notebooks de Jupyter donde se encontraran la exploracion de los datos y el                                             preprocesamiento para el train del modelo, el train del mismo y una predicción.
    ├── src/                 # Soportes de funciones.
    ├─  Datos                # Datos originales para el estudio del modelo, donde tambien se encuentra un diccionario                                   para enterder las variables que hemos utilizado.
    ├─  Datos_pkl            # Datos pkl despues del preprocesamiento de los datos.
    ├── README.md            # Descripción del proyecto.


## 🛠️ Instalación y Requisitos  
Este proyecto utiliza Python 3.12.6.

### **Librerías utilizadas**  
- **pandas**  
  Utilizado para la manipulación y análisis de datos.  
  - [Documentación de Pandas](https://pandas.pydata.org/pandas-docs/stable/)  

- **numpy**  
  Ayuda en cálculos numéricos eficientes y matrices multidimensionales.  
  - [Documentación de NumPy](https://numpy.org/doc/)  

- **os**  
  Gestiona las operaciones del sistema operativo, como la navegación de directorios.  
  - [Documentación de os](https://docs.python.org/3/library/os.html)  

- **sys**  
  Permite acceder a variables y funciones específicas del intérprete de Python.  
  - [Documentación de sys](https://docs.python.org/3/library/sys.html)  

- **seaborn**  
  Facilita la creación de gráficos estadísticos atractivos y fáciles de interpretar.  
  - [Documentación de Seaborn](https://seaborn.pydata.org/)  

- **matplotlib.pyplot**  
  Herramienta para crear visualizaciones básicas y avanzadas en Python.  
  - [Documentación de Matplotlib](https://matplotlib.org/stable/contents.html)

  *## Conlusiones del Proyecto*

## 🛠️ Preprocesamiento.

Durante el preprocesamiento y el estudio de los datos, llegamos a la conclusion de que habia 4 variables las cuales no nos iban a afectar a nuestra predicción puesto que solo era un dato unico por lo que decidimos borrar estas variables: Numero de empleados = 1
Mayor de 18 años = Yes
EmployeeID = Valor unico de identidad del empleado
Horas estandar = 8 horas

Seguimos con la gestion de nulos y observamos que no tenemos nulos en la variables que de primeras se consideran categorica y que tenemos un infimo porcentaje de nulos en las variables numericas, por lo que imputamos los nulos de las numericas con el metodo knn con los 5 vecinos mas cercanos.

El proximos paso es identificar los outliers donde tras observacion y calculo mediante IQR y Epilso  Dbscan, decidimos dejarlos sin tratar puesto que es una informacion demasiado relevante para el modelo.

Una vez tratados los puntos anteriores comenzamos a escalar las variables numericas, como observamos que hay variables categoricas que se pueden escalar porque son numeros por ejemplo nivel de educacion y mas... convertimos a numero decimal (float)  realizamos el metodo standar scaler , en este caso porque tenemos variables numericas con mucha diferencia de rangos y con el standar evitamos que las de mayor rango puedan dominar el modelo afectando asi a su rendimiento.

Pasamos a encodear variables categoricas, realizando una prueba de chi_cuadrado para ver si hay diferencias entre los grupos y asi encodear con un metodo u otro. Usamos target econding para las que no tienen diferencias y One hot ecoding para las que si las tienen en su comparativa con la variable respuesta 'Attrition'.

Por ultimo observamos el balanceo de la variable respuesta  vemos un gran balanceo hacia el no se van por lo que decidimos usar un metodo de balanceo Smotenc. Usamos SMOTENC porque es ideal para datasets mixtos como este, donde hay una combinación de variables categóricas y numéricas, y se necesita abordar el problema del desbalanceo de clases.

## 🛠️ Entrenamiento del modelo.

Entrenamos el modelo mediante Regresion logistica, decision tree , random forest, gradient boosting y xgboost.
Quedandonos con xgboost para el predictor puesto que vemos que no hay sobreajuste tanto en el Acuracy siendo el train 0.92 con un excelente rendimiento y siendo es test de 0.89 como en el AUC siendo el train de este 0.97 discriminando de manera excelente y en el test 0.95 lo cual no nos deja señales de overfiting.
La precision el racall y el Kappa tambien tienen metricas muy buena para la posible prediccion.

## 🛠️ Prediccion.

En el ultimo archivo notebook hemos creado un caso de uso de un empleado con una serie de caracteristicay hemos realizado una prediccion con nuestro modelo xgboost entrenado.


Si quieres ver mas proyectos de Python u otras tecnologias no dudes visitar mi repositorio [adrims10](https://github.com/adrims10)

**Adrián Moreno**












