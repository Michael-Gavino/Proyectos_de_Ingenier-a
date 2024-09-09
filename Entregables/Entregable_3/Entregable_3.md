# Tema:
### Implementación de TinyML en Arduino para el Reconocimiento de Formas y Números

# **Curso:**
### Proyectos de Ingeniería 1

# **Nombre de los Integrantes:**

- **Castillo Ore Lourdes**
- **Huanca Ampuero Lila Zarai**
- **Gavino Isidro Michael Richard**
- **Manosalva Peralta Yojan Alexander**
- **Bertil Vasthian Rodriguez Valderrama**

#


## **1. Introducción**

El modelo de TinyxML  es una  tecnología que se enfoca en el desarrollo de algoritmos  y modelos, ya sea  para desarrollar dispositivos autónomos (Tsoukas et al., 2024). También este modelo combina hardware y software para integrar modelos de Machine Learning y redes neuronales en dispositivos con recursos limitados  con   una  capacidad de  realizar análisis en tiempo real de los datos recopilados. la capacidad de realizar análisis en el dispositivo para múltiples modalidades de detección, como visión, audio y voz. Además, los dispositivos IoT que implementan TinyML en sus microcontroladores requieren menos dependencia de servicios en la nube, lo que a su vez reduce costos, consumo de energía, asi mismo fortalece la seguridad y privacidad de los datos de forma progresiva. Es beneficioso en muchas areas ya sea como  en la atención médica, industria , la agricultura, seguridad, etc. El crecimiento de TinyML  ha motivado a  nuevas  posibilidades  en la creación de diferentes recursos y herramientas compatibles con esta tecnología , como placas de desarrollo, frameworks, bibliotecas y otros conjuntos de herramientas (Kallimani et al., 2023).

Nano 33 BLE sense es una placa que incluye sensores y capacidades de conectividad Bluetooth de baja energa . Esto es para los que requieren una interaccion con el entorno y cmunicacion inalambrica(Barrett, 2023).

Este trabajo tiene como objetivo utilizar un modelo de TinyML en un Arduino Nano 33 BLE Sense para reconocer patrones de movimiento específicos  o mostrar cómo se puede aplicar la inteligencia artificial, incluso en dispositivos con recursos limitados como el Arduino, para tareas de reconocimiento de gestos y se explicarán los pasos necesarios para entrenar el modelo, implementarlo en el dispositivo y comprobar su funcionamiento y activar LEDs según el gesto detectado. Al aprovechar los sensores integrados del Arduino, el dispositivo podrá identificar movimientos que representan un círculo o los números "3" y "1", encendiendo diferentes LEDs como respuesta.

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
| Edge Impulse |
| ----------- |
| ![Dta_1](https://github.com/user-attachments/assets/7047107a-20dc-4a96-8c49-ed97abc11bba) /> |

## **2.1. Diseño de impulso**

Para recrear el proceso de creación del impulso en la plataforma Edge Impulse con los datos de series de tiempo obtenidos del Arduino Nano 33 BLE Sense, puedes seguir estos pasos detallados:

Recolección de Datos:

Sensores Utilizados: Arduino Nano 33 BLE Sense.
Sensores Específicos: Acelerómetro, giroscopio y magnetómetro.
Ejes de Datos: accX, accY, accZ (acelerómetro); gyrX, gyrY, gyrZ (giroscopio); magX, magY, magZ (magnetómetro).
Tamaño de Ventana: 3 segundos para la segmentación de datos.
Preparación de Datos:

Segmentación: Los datos se segmentan en ventanas de 3 segundos.
Características Espectrales: Se extraen características espectrales de las ventanas de datos utilizando un análisis espectral. Este análisis puede incluir transformadas de Fourier u otras técnicas que permitan identificar patrones y características relevantes en el dominio de la frecuencia.
Procesamiento:

Bloque de Procesamiento: En el análisis espectral, asegúrate de verificar que el bloque de procesamiento esté configurado para manejar los ejes de entrada. Esto implica aplicar el análisis espectral a los datos de los sensores para extraer características relevantes.
Entrenamiento del Modelo:

Bloque de Aprendizaje: Utiliza un bloque de clasificación para el aprendizaje automático.
Entrada: Características espectrales extraídas de los datos segmentados.
Salida: Las tres clases que estás tratando de clasificar. En este caso, las clases son: "círculo", "tres" y "uno".
Características de Salida:

Clases a Identificar: El modelo entrenado debe ser capaz de distinguir entre las tres clases especificadas: "círculo", "tres" y "uno". Estas clases corresponden a las etiquetas que se han asignado a las ventanas de datos durante el proceso de etiquetado.
Resumen del Proceso:

Recopilación de Datos: Datos de los ejes de acelerómetro, giroscopio y magnetómetro del Arduino Nano 33 BLE Sense.
Segmentación: Ventanas de 3 segundos.
Análisis Espectral: Extracción de características espectrales.
Clasificación: Entrenamiento de un modelo de clasificación con tres clases de salida ("círculo", "tres", "uno").

![Impulce_LH](https://github.com/user-attachments/assets/538cd041-d8df-47e9-a47a-dce7944b8484)


## **3. Características espectrales** 

En cuanto a la configuración de parámetros, se optó por mantener las opciones predeterminadas. Al generar las características, el tiempo total de procesamiento fue de 40 ms y el uso máximo de RAM alcanzó los 5 KB. La configuración quedó establecida de la siguiente manera:

![C Espectrales_LH](https://github.com/user-attachments/assets/62cbe781-a89d-4f4d-8f61-da717fc491a2)


## **3.1. Clasificación y entrenamiento**

<table>
  <tr>
    <th width="33%">
      En la configuración de la red neuronal, dejamos el número de ciclos de entrenamiento en 30 y la tasa de aprendizaje en 0.0005. La arquitectura de la red neuronal quedó de la siguiente manera:
    </th>
    <th width="33%">
      Pasamos al entrenamiento de nuestro modelo y obtuvimos un 97.8% de exactitud y una pérdida de 0.04 en general, lo que evidencia que se trata de un modelo eficiente:
    </th>
    <th width="33%">
      En la exploración de los datos, vistos gráficamente, queda así:
    </th>
  </tr>
  <tr>
    <td>
      <img src="https://github.com/user-attachments/assets/86138184-94e6-4b2c-b1fb-1e962ceaff09" alt="Red Neuronal" width="400"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/ebfad7f6-0804-4556-9cfa-122b7f17b028" alt="Tabla de Resultados" width="450"/>
    </td>
    <td>
      <img src="https://github.com/user-attachments/assets/35e8e74b-32b0-4794-ad68-2d7780911676" alt="Datos Gráficos" width="650"/>
    </td>
  </tr>
</table>



De este modo, podemos ver que, aunque la predicción de nuestro modelo puede presentar algunas imprecisiones, estas son mínimas en comparación con la tasa de predicciones correctas.

## **3.2.  Despliegue** 

Una vez entrenado y ajustado el modelo para nuestro problema, se configuró el formato del modelo como una biblioteca de Arduino, permitiendo así su programación en el Arduino Nano 33 BLE Sense.

![Arduino_LH](https://github.com/user-attachments/assets/77e384fc-b56f-4660-aaca-3565dd585cef)


## **3.3.  Implementación del modelo_ En Arduino** 

En esta sección, describiremos la implementación del modelo de inferencia de gestos en una placa Arduino Nano 33 BLE Sense utilizando la plataforma Edge Impulse. Este código se encarga de capturar datos del acelerómetro, procesar estos datos a través de un modelo de TinyML y mostrar los resultados.

```cpp
#include <Decteccion_de_gestos_inferencing.h>
#include <Arduino_LSM9DS1.h>
```

En el inicio del código, incluimos las bibliotecas necesarias para la inferencia y la interacción con el acelerómetro. Decteccion_de_gestos_inferencing.h es el archivo generado por Edge Impulse que contiene las funciones necesarias para la inferencia. Arduino_LSM9DS1.h es la biblioteca para manejar el acelerómetro de tres ejes.

```cpp
#define NUM_FEATURES 124 // Número total de características esperadas (62 pares de X, Y)
float features[NUM_FEATURES];
```
Definimos el número total de características (lecturas del acelerómetro) que se esperan para la inferencia y creamos un array features para almacenar estas lecturas.

```cpp
int raw_feature_get_data(size_t offset, size_t length, float *out_ptr) {
    memcpy(out_ptr, features + offset, length * sizeof(float));
    return 0;
}
```

La función raw_feature_get_data se encarga de copiar los datos desde el array features a la memoria que utilizará la función de inferencia. Este es un paso necesario para que el modelo pueda procesar los datos correctamente.

```cpp
void setup() {
    Serial.begin(115200);
    while (!Serial);
    Serial.println("Edge Impulse Inferencing Demo");

    pinMode(LEDR, OUTPUT);
    pinMode(LEDG, OUTPUT);
    pinMode(LEDB, OUTPUT);

    turn_off_leds(); // Apaga todos los LEDs al inicio

    if (!IMU.begin()) {
        Serial.println("Failed to initialize IMU!");
        while (1);
    }
}
```

En la función setup, inicializamos la comunicación serial para depuración y configuramos los pines. También inicializamos el IMU (unidad de medición inercial) y comprobamos si se inicializa correctamente. Si no se inicializa, se detiene el programa.

```cpp
void loop() {
    ei_printf("Edge Impulse standalone inferencing (Arduino)\n");

    for (int i = 0; i < NUM_FEATURES / 2; i++) {
        if (IMU.accelerationAvailable()) {
            float x, y, z;
            IMU.readAcceleration(x, y, z);
            features[2 * i] = x;
            features[2 * i + 1] = y;
        }
        delay(100); // Ajusta el retraso si es necesario para sincronizar con la velocidad de muestreo
    }
```

En el bucle principal loop, capturamos las lecturas del acelerómetro en tiempo real y las almacenamos en el array features. Cada lectura de aceleración (X e Y) se almacena en dos posiciones consecutivas del array. El retraso de 100 ms se ajusta para sincronizar con la velocidad de muestreo.

```cpp
    if (sizeof(features) / sizeof(float) != EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE) {
        ei_printf("The size of your 'features' array is not correct. Expected %lu items, but had %lu\n",
                  EI_CLASSIFIER_DSP_INPUT_FRAME_SIZE, sizeof(features) / sizeof(float));
        delay(1000);
        return;
    }

    ei_impulse_result_t result = { 0 };

    signal_t features_signal;
    features_signal.total_length = sizeof(features) / sizeof(features[0]);
    features_signal.get_data = &raw_feature_get_data;

    EI_IMPULSE_ERROR res = run_classifier(&features_signal, &result, false /* debug */);
    if (res != EI_IMPULSE_OK) {
        ei_printf("ERR: Failed to run classifier (%d)\n", res);
        return;
    }

    ei_printf("run_classifier returned: %d\r\n", res);
    print_inference_result(result);

    delay(1000); // Pausa de 1 segundo antes de repetir el ciclo
}
```

Luego verificamos que el tamaño del array features sea el esperado por el modelo. Si el tamaño es incorrecto, mostramos un mensaje de error y pausamos. Si el tamaño es correcto, preparamos la señal de entrada para el clasificador y llamamos a run_classifier para realizar la inferencia. Los resultados de la inferencia se procesan y se muestran mediante la función print_inference_result.

```cpp
void print_inference_result(ei_impulse_result_t result) {
    ei_printf("Timing: DSP %d ms, inference %d ms, anomaly %d ms\r\n",
              result.timing.dsp,
              result.timing.classification,
              result.timing.anomaly);

    int max_index = -1;
    float max_value = 0.0;

    for (uint16_t i = 0; i < EI_CLASSIFIER_LABEL_COUNT; i++) {
        ei_printf("  %s: ", ei_classifier_inferencing_categories[i]);
        ei_printf("%.5f\r\n", result.classification[i].value);

        if (result.classification[i].value > max_value) {
            max_value = result.classification[i].value;
            max_index = i;
        }
    }

    turn_on_leds(max_index);

#if EI_CLASSIFIER_HAS_ANOMALY
    ei_printf("Anomaly prediction: %.3f\r\n", result.anomaly);
#endif
}
```
La función print_inference_result muestra los tiempos de procesamiento del modelo y los resultados de clasificación. Determina la categoría con el valor de confianza más alto y enciende el LED correspondiente usando la función turn_on_leds.

```cpp
void turn_off_leds() {
    digitalWrite(LEDR, HIGH);
    digitalWrite(LEDG, HIGH);
    digitalWrite(LEDB, HIGH);
}

void turn_on_leds(int pred_index) {
    turn_off_leds(); // Apaga todos los LEDs antes de encender uno

    switch (pred_index) {
        case 0:
            digitalWrite(LEDR, LOW);
            break;
        case 1:
            digitalWrite(LEDG, LOW);
            break;
        case 2:
            digitalWrite(LEDB, LOW);
            break;
        default:
            turn_off_leds();
            break;
    }
}
```
Las funciones turn_off_leds y turn_on_leds manejan el estado de los LEDs. turn_off_leds apaga todos los LEDs, mientras que turn_on_leds enciende el LED correspondiente según el índice de predicción del modelo.


## **4.  Resultados** 

En este proyecto, hemos demostrado la capacidad del Arduino Nano 33 BLE Sense para ejecutar modelos de TinyML, lo que representa un avance significativo en la inteligencia artificial aplicada a dispositivos portátiles. La habilidad del dispositivo para predecir con precisión los gestos del usuario, como un círculo, el número 3 o el número 1, sin necesidad de una conexión continua a la nube, marca un importante paso hacia la creación de dispositivos más autónomos y eficientes(Kallimani et al., 2023).

Un aspecto destacado de esta implementación es la optimización en el uso de recursos y energía. Al realizar el procesamiento directamente en el dispositivo, se reduce la latencia y se mejora la experiencia del usuario, lo cual es crucial para aplicaciones en tiempo real. Esta capacidad también permite que el dispositivo funcione eficazmente en entornos con conectividad a Internet intermitente o nula, ampliando su utilidad en diversas situaciones.

Sin embargo, es importante considerar las limitaciones actuales del modelo. La precisión de las predicciones puede verse afectada por factores como la variabilidad en los movimientos del usuario y el ruido ambiental. Por lo tanto, se recomienda que futuras investigaciones se centren en mejorar la robustez del modelo y en entrenarlo con un conjunto de datos más diverso para asegurar un rendimiento óptimo en diferentes condiciones(Barrett, 2023).

## **5.  Discusion** 

En este proyecto, hemos demostrado la capacidad del Arduino Nano 33 BLE Sense para ejecutar un modelo de TinyML entrenado con Edge Impulse. Esto permite al dispositivo predecir con precisión si los movimientos corresponden a un círculo, el número 3 o el número 1. Esta implementación subraya cómo los sistemas embebidos pueden llevar a cabo tareas complejas de reconocimiento de patrones sin necesidad de una conexión continua a la nube, al mismo tiempo que optimizan el uso de recursos y energía. Al combinar el aprendizaje automático con hardware eficiente, como el Arduino Nano 33 BLE Sense, y herramientas como Edge Impulse, hemos abierto nuevas posibilidades para el desarrollo de aplicaciones inteligentes en dispositivos compactos y de bajo consumo.

## **6.  Referencias** 

[1] A Machine Learning-Oriented Survey on Tiny Machine Learning. (2024). IEEE Journals & Magazine | IEEE Xplore. https://ieeexplore.ieee.org/abstract/document/10433185

[2] Freitag, F., Roger, P. C., & De Catalunya Departament D’Arquitectura de Computadors, U. P. (2021, 30 junio). Aplicación de modelos de aprendizaje automático en microcontroladores. https://upcommons.upc.edu/handle/2117/356304

[3] Tsoukas, V., Gkogkidis, A., Boumpa, E., & Kakarountas, A. (2024). A Review on the emerging technology of TinyML. ACM Computing Surveys. https://doi.org/10.1145/3661820

[4]  Kallimani, R., Pai, K., Raghuwanshi, P., Iyer, S., & López, O. L. A. (2023). TinyML: Tools, applications, challenges, and future research directions. Multimedia Tools And Applications, 83(10), 29015-29045. https://doi.org/10.1007/s11042-023-16740-9

[5] Barrett, S. F. (2023). Arduino V: Machine Learning. En Synthesis lectures on digital circuits and systems. https://doi.org/10.1007/978-3-031-21877-4
