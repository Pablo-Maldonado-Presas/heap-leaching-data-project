# Análisis de datos de lixiviación para predicción de cobre

## Descripción del proyecto
Este repositorio contiene una serie de notebooks de Jupyter utilizados para analizar datos de sensores en pilas de lixiviación de una minera. El objetivo fue desarrollar un modelo predictivo de Machine Learning para estimar la concentración de cobre en la solución lixiviante, optimizando el proceso de extracción.

Los notebooks abarcan desde el preprocesamiento de datos hasta la evaluación de modelos predictivos, sin incluir los conjuntos de datos originales debido a restricciones de acceso y confidencialidad.

## Objetivos del proyecto
- Proponer un sistema informático que permita el uso más eficiente de la solución lixiviante y maximizar la obtención de cobre a través de un monitoreo predictivo del estado de las pilas.
- Analizar la distribución de las variables (humedad, temperatura, pH y concentración de cobre).
- Identificar patrones que optimicen la eficiencia del proceso de lixiviación.
- Diseñar un flujo de preprocesamiento de datos adecuado.
- Entrenar y evaluar modelos de Machine Learning para la predicción de la concentración de cobre.

## Alcance del análisis
### Datos disponibles
- Datos provenientes de dos fuentes:
  - Sensores instalados en las pilas de lixiviación.
  - Muestras tomadas por el cliente.
- Variables registradas:
  - Humedad, temperatura, pH y concentración de cobre.

### Restricciones
- Falta de disponibilidad de datos adicionales como granulometría del material, velocidad del flujo de la solución, porosidad del material y condiciones ambientales externas.
- Solo algunos nodos contaron con sensor de pH.
- Se dispone de 427 registros del cliente, lo que limita el tamaño del conjunto de datos.

## Estructura del Repositorio
```
/
├── 1.0-pmp-separated-nodes.ipynb  # Procesamiento inicial de datos por nodos individuales
├── 2.0-pmp-all-nodes.ipynb        # Integración de datos de todos los nodos
├── 2.5-pmp-all-nodes-2.ipynb      # Refinamiento en la integración de datos
├── 3.0-pmp-solution-data.ipynb    # Análisis de datos extraídos por el cliente
├── 4.0-pmp-assembled-data.ipynb   # Análisis de los datos consolidados y preparación final para modelado
├── 5.0-pmp-assembled-without-ph.ipynb  # Variación del dataset sin la variable pH de entrada
```

## Modelos de Predicción
- Se entrenaron distintos modelos de regresión para predecir la concentración de cobre en la solución lixiviante.
- Variables utilizadas:
  - Predictoras (X): Humedad y temperatura en diferentes niveles de profundidad.
  - Variable objetivo (y): Concentración de cobre y nivel de pH de solución final.

### Desempeño de modelos
Los modelos utilizados incluyen:
- Regresión lineal
- Ridge regularizado
- Regresión polinómica
- Árboles de decisión
- Gradient Boosting Regressor
- XGBoost Regressor
- Extra Trees Regressor

El mejor desempeño se obtuvo con modelos no lineales, capaces de capturar mejor las interacciones entre las variables.

## Consideraciones
- Los datasets originales no están incluidos en este repositorio.
- Los modelos de Machine Learning se evaluaron utilizando diferentes técnicas de regresión y árboles de decisión, destacando el uso de Gradient Boosting y XGBoost.
