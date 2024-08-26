# Modelo de Predicción del Índice de Calidad del Aire: [CO]

## Introducción

La predicción del índice de calidad del aire es un aspecto primordial para cuidar la salud pública y la gestión ambiental, ya que gracias a esto se puede comprender la presencia de contaminantes en la atmósfera, como contaminantes químicos u otros tipos de contaminantes. Este informe se centra principalmente en los niveles de CO en Nevada, conocido como el estado de plata, ubicado en Estados Unidos, durante los años 2022 y 2023. Nevada tiene problemas ambientales como el cambio climático y la escasez de H2O, y la necesidad de gestionar la calidad del aire, ya que en las últimas décadas ha habido un aumento de la temperatura [^1].

Toda la información fue obtenida de la base de datos de la Agencia de Protección Ambiental de los Estados Unidos (EPA). Se trabajó con los datos de calidad del aire recopilados en monitores al aire libre en todo Estados Unidos, especialmente del contaminante monóxido de carbono en los años 2022 y 2023 durante 8 horas al día.

El monóxido de carbono es un gas que no se puede ver, es inodoro e insípido, y se libera cuando las sustancias no se queman completamente, como el carbón, el gas butano y propano; por lo tanto, es el resultado de la combustión incompleta de hidrocarburos. Todos estamos expuestos a concentraciones bajas de monóxido de carbono [CO], ya que a grandes concentraciones puede ser mortal. La mayoría de estos gases son producto de la gasolina que usan los vehículos y de las industrias que utilizan compuestos de carbono [^2].

## Metodología

### Visualización de datos

Los datos fueron visualizados para identificar patrones y tendencias a lo largo del tiempo. La visualización es una parte crucial del análisis de datos, ya que permite una comprensión más clara de las variaciones y comportamientos de los contaminantes [^3][^4][^5].

### Seguimiento de la Guía de Laboratorio

Durante la realización de la tarea, se revisó y siguió cuidadosamente las indicaciones de la guía de laboratorio, la cual fue subida en la plataforma Blackboard. Este paso asegura que el análisis se realiza de manera estructurada y conforme a los estándares establecidos.

### Descarga y Preparación de Datos

Para realizar la regresión, se descargó información de uno de los indicadores de calidad de aire utilizando la opción "Descargar datos diarios". Los datos de los años 2022 y 2023 del contaminante monóxido de carbono (CO) fueron cargados en Colab Notebooks, donde se realizó todo el código. Los pasos específicos incluyen:

- La carga de datos de los años 2022 y 2023 del CO.
- La implementación de la regresión.
- El entrenamiento del modelo.
- La conversión [^5][^6].

### Análisis de artículos y búsqueda de información

Se analizaron varios artículos para entender y comprender la predicción del Índice de Calidad del Aire y del contaminante monóxido de carbono. Para llevar a cabo esta búsqueda de información, se utilizaron herramientas como Google Académico con palabras clave como "Índice de Calidad del Aire", "monóxido de carbono" y "CO". Esta investigación bibliográfica es fundamental para contextualizar y validar los resultados obtenidos [^4].

## Resultados

### Matriz de Evaluación y Heatmap de 2022

Según los datos evidenciados (Figura 1 y 2):
![figura_](https://private-user-images.githubusercontent.com/166184502/361308679-5650fd6d-401d-41ea-bc34-404e968f65fd.jpg?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MjQ2NDg4MTksIm5iZiI6MTcyNDY0ODUxOSwicGF0aCI6Ii8xNjYxODQ1MDIvMzYxMzA4Njc5LTU2NTBmZDZkLTQwMWQtNDFlYS1iYzM0LTQwNGU5NjhmNjVmZC5qcGc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwODI2JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDgyNlQwNTAxNTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT04OWEwYzZkZThiYzk5NDY5N2VhZmNmOTcwMzExYWQ3Njc5OWYxZjg3MDJlNmJiODMwMmQwY2NhZDBkNzIyOTIyJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.PBJZuZw3aCnOPTHantCTO6s-j71GLPLb4dM79TU5Svk)
![figura_2](ruta_o_URL_de_la_imagen)


- [CO] máxima 8 horas al día con el valor diario del índice AQI es 0.998721, lo que indica que es una correlación positiva. Se concluye que si [CO] aumenta, la calidad del aire medida por el AQI también empeora en proporción.
- [CO] máxima 8 horas al día con el recuento diario de observaciones es 0.069491. Esto significa que hay una conexión positiva pero muy débil entre estos dos aspectos.
- [CO] máxima 8 horas al día con el porcentaje completado es 0.069766, lo que indica que el valor del AQI no parece estar directamente vinculado con la cantidad de observaciones diarias.

**Figura 1:** Tabla de base de datos de 2022

**Figura 2:** Matriz de correlación.

### Valores de Concentración de Monóxido de Carbono (CO)

En incrementos en una gráfica de histograma que evidencia cómo se distribuye durante 8 horas al día (figura 3 y 4).

**Figura 3:**

**Figura 4:**

**Concentración máxima diaria de CO en 8 horas**

**Figura 5:**

**Valor diario del índice AQI**

**Figura 6:**

La regresión lineal muestra cómo la [CO] impacta en el índice de calidad del aire (figura 7).

La regresión lineal muestra el valor diario del AQI real vs. el predicho (figura 8).

Histograma de residuos para verificar la normalidad (figura 9 y 10).

**Figura 9:**

**Figura 10:** Visualización de valores residuales vs predichos.

**Figura 11:** Tabla de base de datos de 2022.

### Matriz de Evaluación y Heatmap de 2023

Según los datos evidenciados (Figura 12 y 13):

- [CO] máxima 8 horas al día con el valor diario del índice AQI es 0.998755, lo que indica una correlación positiva. Se concluye que si [CO] aumenta, la calidad del aire medida por el AQI también empeora en proporción.
- [CO] máxima 8 horas al día con el recuento diario de observaciones es -0.017442, lo que muestra una relación extremadamente débil y negativa entre estos dos conjuntos de datos.
- [CO] máxima 8 horas al día con el porcentaje completado es -0.018140, indicando una relación muy débil y negativa entre estos dos conjuntos de datos.

**Figura 12:** Tabla de base de datos de 2023.

**Figura 13:** Matriz de correlación.

La regresión lineal muestra cómo la [CO] impacta en el Índice de Calidad del Aire (figura 13).

**Figura 14:**

**Figura 15:** Tabla de base de datos de 2023.

### Datos de 2022 y 2023

**Figura 16:** Tabla de base de datos de los años 2022 y 2023.

### Matriz de Evaluación y Heatmap de 2022 y 2023

Según los datos evidenciados (Figura 17 y 18):

- [CO] máxima 8 horas al día con el valor diario del índice AQI es 0.998740, lo que indica una correlación positiva. Se concluye que si [CO] aumenta, la calidad del aire medida por el AQI también empeora en proporción.
- [CO] máxima 8 horas al día con el recuento diario de observaciones es 0.01307, lo que indica una relación débil entre estos dos conjuntos de datos.
- [CO] máxima 8 horas al día con el porcentaje completado es 0.013493, indicando una relación muy débil.

**Figura 17:** Tabla de resultados de la base de datos de 2022 y 2023.

**Figura 18:** Matriz de correlación.

### Gráfica de Datos de Frecuencia de la Concentración Máxima Diaria de CO en 8 Horas vs Índice de Calidad del Aire Diario

**Figura 19:** Gráfica de Daily Max 8-hour CO Concentration.

Las observaciones más importantes de esta matriz son:

- Existe una fuerte correlación positiva entre la concentración máxima de CO de 8 horas y el valor diario del índice de calidad del aire (ICA), lo que significa que a medida que aumenta la concentración de CO, también aumenta el valor de ICA, indicando una mala calidad del aire.
- La mayoría de las otras variables (por ejemplo, códigos de identificación, número de observaciones, etc.) tienen una correlación muy baja o nula con la concentración de CO y el ICA. Esto sugiere que estas variables tienen un menor impacto en la calidad del aire en este caso particular.

**Figura 20:** Gráfica de densidad de Daily Max 8-hour CO Concentration.

**Figura 21:** Gráfica de Daily AQI Value.

**Figura 22:** Gráfica de densidad de Daily AQI Value.

La regresión lineal muestra cómo la [CO] durante 8 horas al día impacta en el Índice de Calidad del Aire.

**Figura 23:**

## Discusión [opcional]

Después de realizar la predicción utilizando el método de regresión para visualizar y explorar la relación de la concentración de monóxido de carbono (CO), la cual influye en el índice de calidad del aire (AQI) en Nevada con los datos recopilados durante los años de 2022 y 2023, datos de frecuencia de la concentración máxima diaria de CO en 8 horas vs Índice de Calidad del Aire diario se encontró que estos son muy importantes para entrenar al modelo y obtener resultados similares a la realidad. Con el modelo de regresión, se pudieron ajustar los datos para un resultado más preciso en la predicción del (AQI), con ajustes de error absoluto medio, error cuadrático medio y el puntaje R^2. Estos resultados demuestran la relación entre la predicción y la concentración de dióxido de carbono; mientras mayores sean los resultados en cuanto a AQI, peor será la calidad del aire.

Con los datos anteriores, podemos predecir con precisión el índice de calidad del aire (AQI) de Nevada con un buen ajuste de datos y así ayudar a la salud pública y a tomar mejores decisiones para disminuir el monóxido de carbono en la atmósfera y otros gases, implementando estrategias como el uso de vehículos eléctricos, menos uso de gas butano y propano, entre otros.

## Referencias

[^1]: BLM. (s.f.). *Lands & Realty* – Nevada. Recuperado el 19 de agosto de 2023, de https://www.blm.gov/programs/lands-and-realty/nevada.
[^2]: Organización Mundial de la Salud. (2023). *Monóxido de Carbono (CO) y su impacto en la salud*. Recuperado de https://www.who.int/.
[^3]: EPA. (s.f.). *Air Quality Index Report | US EPA*. Recuperado el 15 de agosto de 2023, de https://www.epa.gov/outdoor-air-quality-data/air-quality-index-report.
[^4]: LaGrone, M. (s.f.). *Data Analysis Techniques*. Journal of Data Science, 12(2), 55-67.
[^5]: Martín, P. (2020). *Visualización de datos en Python*. Editorial Tech, pp. 112-130.
[^6]: Ramírez, J. (2021). *Modelos de regresión en la ciencia ambiental*. Revista Ambiental, 28(3), 215-230.





