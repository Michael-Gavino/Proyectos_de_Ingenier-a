# Tema:
### Implementación de TinyML en Arduino para el Reconocimiento de Formas y Números

# **Curso:**
### Proyectos de Ingeniería 1

# **Integrantes:**
- Lila Huanca
- Michael Gavino
- Alexander Manosalva

#


## **1. Introducción**

El modelo de TinyxML  es una  tecnología que se enfoca en el desarrollo de algoritmos  y modelos, ya sea  para desarrollar dispositivos autónomos (Tsoukas et al., 2024). También este modelo combina hardware y software para integrar modelos de Machine Learning y redes neuronales en dispositivos con recursos limitados  con   una  capacidad de  realizar análisis en tiempo real de los datos recopilados. la capacidad de realizar análisis en el dispositivo para múltiples modalidades de detección, como visión, audio y voz. Además, los dispositivos IoT que implementan TinyML en sus microcontroladores requieren menos dependencia de servicios en la nube, lo que a su vez reduce costos, consumo de energía, asi mismo fortalece la seguridad y privacidad de los datos de forma progresiva. Es beneficioso en muchas areas ya sea como  en la atención médica, industria , la agricultura, seguridad, etc. El crecimiento de TinyML  ha motivado a  nuevas  posibilidades  en la creación de diferentes recursos y herramientas compatibles con esta tecnología , como placas de desarrollo, frameworks, bibliotecas y otros conjuntos de herramientas (Kallimani et al., 2023).

Nano 33 BLE sense es una placa que incluye sensores y capacidades de conectividad Bluetooth de baja energa . Esto es para los que requieren una interaccion con el entorno y cmunicacion inalambrica(Barrett, 2023).

Este trabajo tiene como objetivo utilizar un modelo de TinyML en un Arduino Nano 33 BLE Sense para reconocer patrones de movimiento específicos  o mostrar cómo se puede aplicar la inteligencia artificial, incluso en dispositivos con recursos limitados como el Arduino, para tareas de reconocimiento de gestos y se explicarán los pasos necesarios para entrenar el modelo, implementarlo en el dispositivo y comprobar su funcionamiento.(1) y activar LEDs según el gesto detectado. Al aprovechar los sensores integrados del Arduino, el dispositivo podrá identificar movimientos que representan un círculo o los números "3" y "1", encendiendo diferentes LEDs como respuesta.(1) 

En concreto, el sistema está diseñado para:

Encender un LED rojo cuando se dibuja un círculo en el aire.
Encender un LED azul cuando se dibuja el número 3.
Encender un LED verde cuando se dibuja el número 1.

## **1.1. Metodologia**


Durante el tiempo en que se realizó la tarea, se revisó cuidadosamente en la plataforma blackboard.  Para realizar esta tarea ,se analizó algunos artículos con la finalidad de entender  como utilizar un modelo de TinyML en un Arduino Nano 33 BLE Sense .Para llevar a cabo nuestra búsqueda de información, hemos utilizado herramientas como Google Académico, science direct con  las palabras claves “TinyML” , “Tiny Machine Learning” y como los artículos eran de inglés usamos google traductor. 
El desarrollo de este proyecto se dividió en varias fases, que van desde la recopilación de los datos de movimiento hasta la implementación del modelo en el Arduino Nano 33 BLE Sense. A continuación, se detalla cada uno de los pasos que seguimos para llevar a cabo el reconocimiento de gestos y la activación de los LEDs.

## **2. Captura de datos de movimiento**

El primer paso fue obtener los datos necesarios para entrenar el modelo de reconocimiento de gestos. Usando los sensores de movimiento del Arduino Nano 33 BLE Sense, registramos los gestos deseados: el dibujo de un círculo, el número 3, y el número 1. Para garantizar que el modelo pudiera generalizar bien, repetimos cada gesto varias veces y bajo diferentes condiciones.

A continuación, se puede evidenciar lo mencionado:
| Arduino Nano 33 BLE Sense | Edge Impulse |
| ----------- | ----------- |
| <img src=     /> | ![Dta_1](https://github.com/user-attachments/assets/7047107a-20dc-4a96-8c49-ed97abc11bba) /> |

## **2.1. Preprocesamiento de los Datos**

Una vez recogidos los datos, realizamos un preprocesamiento básico. Esto incluyó normalizar los valores para que los datos fueran comparables entre sí y filtrar el ruido no deseado que pudiera interferir con el modelo. También segmentamos los movimientos en pequeñas ventanas de tiempo, lo que permitió que el modelo de aprendizaje automático identificara patrones claros y diferenciados.

## **3. Creación y Entrenamiento del Modelo TinyML** 

Con los datos listos, el siguiente paso fue desarrollar un modelo de aprendizaje automático lo suficientemente ligero como para correr en el Arduino. Utilizamos TensorFlow Lite para crear una red neuronal sencilla. Entrenamos el modelo con los datos etiquetados de cada gesto, ajustando la estructura y los parámetros para obtener buenos resultados sin comprometer la velocidad ni el tamaño del modelo.(Barrett, S. F. (2023))

## **3.1. Validación del Modelo** 

Antes de cargar el modelo en el Arduino, realizamos pruebas para verificar su precisión y capacidad de generalización. Probamos varias configuraciones y ajustamos los hiperparámetros hasta que el modelo alcanzó un nivel aceptable de precisión para reconocer correctamente los tres gestos, sin confundirlos entre sí.(Barrett, S. F. (2023))

## **3.2.  Implementación en el Arduino Nano 33 BLE Sense** 

Una vez que el modelo estaba entrenado y validado, lo cargamos en el Arduino Nano 33 BLE Sense utilizando TensorFlow Lite . El código se encargó de procesar las predicciones del modelo y activar los LEDs correspondientes: rojo para un círculo, azul para un 3, y verde para un 1. Esta fase requirió integrar el modelo con el hardware para que pudiera reaccionar en tiempo real a los movimientos.

## **3.3.  Pruebas Finales y Optimización** 

Finalmente, realizamos pruebas completas con el sistema en funcionamiento. Repetimos los gestos en distintas condiciones para asegurarnos de que el modelo respondiera de manera precisa y consistente. Hicimos algunos ajustes en el código y optimizamos el comportamiento del modelo para mejorar la experiencia del usuario y la confiabilidad del sistema en general.

## **4.  Resultados** 


## **5.  Discusion** 


## **6.  Referencias** 

1.A Machine Learning-Oriented Survey on Tiny Machine Learning. (2024). IEEE Journals & Magazine | IEEE Xplore. https://ieeexplore.ieee.org/abstract/document/10433185

2.Freitag, F., Roger, P. C., & De Catalunya Departament D’Arquitectura de Computadors, U. P. (2021, 30 junio). Aplicación de modelos de aprendizaje automático en microcontroladores. https://upcommons.upc.edu/handle/2117/356304

Tsoukas, V., Gkogkidis, A., Boumpa, E., & Kakarountas, A. (2024). A Review on the emerging technology of TinyML. ACM Computing Surveys. https://doi.org/10.1145/3661820

Kallimani, R., Pai, K., Raghuwanshi, P., Iyer, S., & López, O. L. A. (2023). TinyML: Tools, applications, challenges, and future research directions. Multimedia Tools And Applications, 83(10), 29015-29045. https://doi.org/10.1007/s11042-023-16740-9

Barrett, S. F. (2023). Arduino V: Machine Learning. En Synthesis lectures on digital circuits and systems. https://doi.org/10.1007/978-3-031-21877-4
