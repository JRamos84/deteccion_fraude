# Detección de Fraude
[![Python](https://img.shields.io/badge/Python-3.11%2B-blue)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-2.0.3-blue)](https://xgboost.readthedocs.io/en/latest/)
[![RandomForest](https://img.shields.io/badge/Algorithm-RandomForest-brightgreen)](https://en.wikipedia.org/wiki/Random_forest)
[![Pandas](https://img.shields.io/badge/Pandas-1.5%2B-blue)](https://pandas.pydata.org/)



<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

## Descripción
El objetivo principal de este proyecto es detectar transacciones comerciales fraudulentas con la mayor precisión posible, discriminando eficazmente entre transacciones legítimas y fraudulentas. La detección precisa es crucial para evitar tanto los falsos positivos (transacciones legítimas etiquetadas como fraudulentas) como los falsos negativos (transacciones fraudulentas no detectadas), ya que ambos pueden afectar negativamente la experiencia del cliente. El proyecto se enfoca en desarrollar y optimizar métricas robustas para evaluar el desempeño del modelo, garantizando una alta eficacia en la identificación de transacciones fraudulentas sin impactar negativamente a los usuarios honestos.

## Tabla de Contenido
1. [Introducción](#introducción)
2. [Análisis Exploratorio de los Datos (EDA)](#análisis-exploratorio-de-los-datos-eda)
3. [Limpieza de los Datos y Preprocesamiento](#limpieza-de-los-datos-y-preprocesamiento)
4. [Selección de Características](#selección-de-características)
5. [Modelado](#modelado)
6. [Hyperparameter Tuning](#hyperparameter-tuning)
7. [Evaluación y Validación del Modelo](#evaluación-y-validación-del-modelo)
8. [Documentación y Reporte](#documentación-y-reporte)
9. [Futuras Líneas de Trabajo](#futuras-líneas-de-trabajo)
10. [Conclusión](#conclusión)
11. [Contribuciones](#contribuciones)
12. [Contacto](#contacto)

## Introducción
Este proyecto tiene como objetivo la detección de transacciones fraudulentas en un dataset de transacciones comerciales. La precisión en la detección es crucial para minimizar el impacto tanto de los falsos positivos (transacciones legítimas mal clasificadas como fraudulentas) como de los falsos negativos (transacciones fraudulentas no detectadas). A través de este proyecto, se busca desarrollar y optimizar un modelo robusto para identificar transacciones fraudulentas con alta efectividad.

## Análisis Exploratorio de los Datos (EDA)
Durante el análisis exploratorio de datos, se llevaron a cabo las siguientes tareas:
- Se aplicó un muestreo estratificado al dataset original de más de medio millón de registros para obtener una muestra representativa.
- Se identificaron las características más relevantes para la detección de fraude.
- Se evaluaron y eliminaron columnas con un alto porcentaje de valores nulos.
- Se eliminaron valores duplicados que eran mínimos en comparación con el tamaño total del dataset.
- Se realizaron análisis univariados y bivariados para entender las distribuciones y relaciones entre variables.

## Limpieza de los Datos y Preprocesamiento
- Manejo de valores nulos identificados en el análisis EDA.
- Aplicación de un corte en la columna `TransactionAmt` con un umbral determinado.
- Conversión de la columna `TransactionDT` a unidades temporales diferenciales (días, horas, semanas, meses).
- Mapeo y transformación de la columna `email` para estandarización.
- División de los datos en conjuntos de entrenamiento, evaluación y prueba.
- Normalización y estandarización de las variables.
- Uso de validación cruzada para determinar el número óptimo de componentes en PCA.
- Exportación de los conjuntos de datos de entrenamiento, evaluación y prueba.

## Selección de Características
- Análisis Chi-cuadrado para evaluar la relevancia de las características.
- Análisis ANOVA para comparar las medias de diferentes grupos y determinar la importancia de las características.

## Modelado
- Balanceo de los datos de entrenamiento para manejar el desbalance en las clases.
- Comparación entre diferentes modelos de entrenamiento.
- Entrenamiento de modelos con Random Forest utilizando diversos métodos de procesamiento de datos:
  - Con datos balanceados.
  - Con datos desbalanceados y PCA.
  - Con datos procesados en la selección de características.
- Entrenamiento adicional usando XGBoost.

## Hyperparameter Tuning
- Entrenamiento y ajuste de hiperparámetros para optimizar el rendimiento del modelo.
- Evaluación del modelo optimizado utilizando técnicas avanzadas.
- Uso de XGBoost como segunda propuesta de modelo.

## Evaluación y Validación del Modelo
- Evaluación del modelo utilizando un conjunto de datos de prueba que no se usó en ninguna otra parte del trabajo, siguiendo principios éticos.
- Evaluación con métricas avanzadas para medir la efectividad del modelo.

## Documentación y Reporte
- Resumen del proyecto.
- Principales hallazgos del análisis exploratorio de datos (EDA).
- Detalles del modelo final y su rendimiento.
- Conclusiones y recomendaciones para futuras mejoras.

## Futuras Líneas de Trabajo
- **Ajuste del Umbral de Decisión**: Modificar el umbral de decisión del modelo para mejorar la precisión en la detección de fraudes.
- **Técnicas de Ensamblado**: Implementar técnicas de ensamblado como bagging o boosting para mejorar el rendimiento del modelo.
- **Evaluación Continua**: Realizar una evaluación continua del modelo utilizando diferentes métricas y conjuntos de datos para asegurar su eficacia en la detección de fraudes.
- **Experimentación con Algoritmos Avanzados**: Probar algoritmos más avanzados, como redes neuronales profundas.
- **Implementación de MLPo (Machine Learning Pipeline Optimization)**: Emplear técnicas de optimización de pipelines de aprendizaje automático para automatizar la selección de modelos, preprocesamiento y ajuste de hiperparámetros, mejorando así la eficiencia y efectividad del proceso de modelado.

## Conclusión
Aunque el modelo muestra una precisión global mejorada y un buen rendimiento en la clasificación de transacciones no fraudulentas, continúa presentando deficiencias significativas en la detección precisa de transacciones fraudulentas. La baja precisión y puntuación F1 para la clase de transacciones fraudulentas se debe al desbalance en los datos de evaluación. Se recomienda ajustar el umbral de decisión del modelo, explorar técnicas de muestreo o considerar la incorporación de características adicionales para mejorar la detección de fraudes en transacciones.

## Project Organization



```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for detección_de_fraude
│                         and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── detección_de_fraude                <- Source code for use in this project.
    │
    ├── __init__.py    <- Makes detección_de_fraude a Python module
    │
    ├── data           <- Scripts to download or generate data
    │   └── make_dataset.py
    │
    ├── features       <- Scripts to turn raw data into features for modeling
    │   └── build_features.py
    │
    ├── models         <- Scripts to train models and then use trained models to make
    │   │                 predictions
    │   ├── predict_model.py
    │   └── train_model.py
    │
    └── visualization  <- Scripts to create exploratory and results oriented visualizations
        └── visualize.py
```

--------

## Contribuciones
Las contribuciones son lo que hacen que la comunidad de código abierto sea un lugar increíble para aprender, inspirar y crear. Cualquier contribución que realices es muy apreciada.

Si tienes una sugerencia para mejorar este proyecto, por favor haz un fork del repositorio y crea un pull request. También puedes abrir un issue con la etiqueta "mejora". ¡No olvides darle una estrella al proyecto! ¡Gracias de nuevo!

1. Haz un Fork del Proyecto
2. Crea tu Rama de Característica (git checkout -b feature/1. caracteristica)
3. Haz tus Cambios (git commit -m 'Añadir una nueva Característica')
4. Haz Push a la Rama (git push origin feature/Característica)
5. Abre un Pull Request

## Contacto
Si tienes preguntas, comentarios o sugerencias, no dudes en contactarme:

- José F. Ramos: joseph0001@gmail.com
- Enlace del Proyecto: [https://github.com/JRamos84/deteccion_fraude](https://github.com/JRamos84/deteccion_fraude)

