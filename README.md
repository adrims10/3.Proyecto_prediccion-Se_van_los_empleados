# Proyecto: Predicción de Retención de Empleados 🏢
![OIP (3)](https://github.com/user-attachments/assets/14183db5-eff2-4f77-9d41-962bbec3bcf0)

Bienvenidos! 

# *Es un placer recibirlos*

## Introducción

Esta vez nos toca trabajar en Recursos Humanos y nos enfrentamos a uno de los mayores dolores de cabeza de cualquier empresa: la rotación de empleados. ¿Por qué algunas personas deciden quedarse mientras otras se van? ¿Será el salario? ¿Las horas extra? ¿La relación con su jefe?

En este proyecto, vamos a enfrentarnos a la tarea de desentrañar patrones, analizar tendencias y construir un modelo que pueda predecir si un empleado permanecerá o decidirá decir adiós.

Pero esto no es solo sobre números y gráficos; se trata de entender cómo las decisiones empresariales impactan la vida de las personas y cómo, con un poco de análisis, podríamos ayudar a las empresas a ser mejores lugares para trabajar. Así que prepárate para explorar datos, ensuciarte las manos con algoritmos y, quién sabe, tal vez descubrir el secreto para mantener a los empleados felices y comprometidos.

## 🗂️ Estructura del Proyecto

    ├── notebooks/           # Notebooks de Jupyter donde se encontraran la exploracion el train del modelo y una predicción.
    ├── src/                 # Soportes de funciones.
    ├─  Datos                # Datos para el estudio del modelo.
    ├─  Datos_pkl            # Datos pkl despues del preprocesamiento de los datos.
    ├── README.md            # Descripción del proyecto.
    ├── PDF                  # PDF con la presentación y las conclusiones de todo el estudio.


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



**Resultados , Conclusiones**

-Hemos elegido el modelo xgboost como mejor modelo entranado.
-Podemos obtener toda la informacion del resumen y las conclusiones en el archivo PDF subido donde se encuetra la manera de preprocesar los datos, los modelos que se     han entrenado y un modelo predictivo bastante buento.
-Para mas informacion en cada notebook se añaden descripciones concisas de cada paso que se da en el preprocesamiento en el modelado y prediccion del modelo.


**Proximos pasos**

-Seguir entrenando el modelo mediante los hiperparametos.
-Añadir mas datos al modelo.
-Tratamiento de datos de manera diferente para optimizar si se puede el train del modelo.


![OIP](https://github.com/user-attachments/assets/a3261f22-9193-45df-bf33-14a396dfd988)


