![Clasificacion](https://github.com/user-attachments/assets/316d013a-7709-4531-907a-70d3bded555a)


# Predicción de Retención de Empleados 🏢

Dado una serie de datos, nos enfrentaremos a intentar predecir si un empleado se va a ir de la empresa o no.

En este proyecto, vamos a enfrentarnos a la tarea de desentrañar patrones, analizar tendencias y construir un modelo que pueda predecir si un empleado permanecerá o decidirá decir adiós según una serie de variables dadas.

Vamos a ir comparando varios modelos predictivos para ver cuál es el modelo que mejor funciona para acabar montando nuestro predictor.


## 🗂️ Estructura del Proyecto

    ├── notebooks/           # Notebooks de Jupyter donde se encontraran la exploracion de los datos y el                                             preprocesamiento para el train del modelo, el train del mismo y una predicción.
    ├── src/                 # Soportes de funciones.
    ├─  Datos                # Datos originales para el estudio del modelo, donde tambien se encuentra un diccionario                                   para enterder las variables que hemos utilizado.
    ├─  Datos_pkl            # Datos pkl despues del preprocesamiento de los datos.
    ├── README.md            # Descripción del proyecto.


## 🛠️ Instalación y Requisitos  
Este proyecto utiliza Python 3.12.6.


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

---

## Conclusiones del Proyecto

### 🛠️ Preprocesamiento

Durante el preprocesamiento y el estudio de los datos, llegamos a la conclusión de que había 4 variables las cuales no nos iban a afectar a nuestra predicción puesto que solo era un dato único. Por lo tanto, decidimos borrar estas variables:  
- Número de empleados = 1  
- Mayor de 18 años = Yes  
- EmployeeID = Valor único de identidad del empleado  
- Horas estándar = 8 horas  

Seguimos con la gestión de nulos y observamos que no tenemos nulos en las variables que de primeras se consideran categóricas y que tenemos un ínfimo porcentaje de nulos en las variables numéricas, por lo que imputamos los nulos de las numéricas con el método KNN con los 5 vecinos más cercanos.

El próximo paso es identificar los outliers, donde tras observación y cálculo mediante IQR y Épsilon DBSCAN, decidimos dejarlos sin tratar puesto que es una información demasiado relevante para el modelo.

Una vez tratados los puntos anteriores, comenzamos a escalar las variables numéricas. Como observamos que hay variables categóricas que se pueden escalar porque son números, por ejemplo, nivel de educación y más, convertimos a número decimal (float). Realizamos el método Standard Scaler, en este caso porque tenemos variables numéricas con mucha diferencia de rangos y con el estándar evitamos que las de mayor rango puedan dominar el modelo afectando así a su rendimiento.

Pasamos a codificar variables categóricas, realizando una prueba de chi-cuadrado para ver si hay diferencias entre los grupos y así codificar con un método u otro. Usamos Target Encoding para las que no tienen diferencias y One-Hot Encoding para las que sí las tienen en su comparativa con la variable respuesta 'Attrition'.

Por último, observamos el balanceo de la variable respuesta. Vemos un gran desequilibrio hacia el "no se van", por lo que decidimos usar un método de balanceo SMOTENC. Usamos SMOTENC porque es ideal para datasets mixtos como este, donde hay una combinación de variables categóricas y numéricas, y se necesita abordar el problema del desbalanceo de clases.

---

### 🛠️ Entrenamiento del modelo

Entrenamos el modelo mediante Regresión Logística, Decision Tree, Random Forest, Gradient Boosting y XGBoost.  
Nos quedamos con XGBoost para el predictor, puesto que vemos que no hay sobreajuste tanto en el Accuracy (siendo el train 0.92 con un excelente rendimiento y siendo el test de 0.89) como en el AUC (siendo el train de este 0.97, discriminando de manera excelente, y en el test 0.95), lo cual no nos deja señales de overfitting.  

La precisión, el recall y el Kappa también tienen métricas muy buenas para la posible predicción.

---

### 🛠️ Predicción

En el último archivo notebook hemos creado un caso de uso de un empleado con una serie de características y hemos realizado una predicción con nuestro modelo XGBoost entrenado.

---

Si quieres ver más proyectos de Python u otras tecnologías, no dudes en visitar mi repositorio [adrims10](https://github.com/adrims10).


**Adrián Moreno**












