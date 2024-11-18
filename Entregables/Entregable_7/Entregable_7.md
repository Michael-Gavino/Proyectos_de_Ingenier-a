# Entregable: Diseño de PCB y sus Componentes


![Captura de pantalla 2024-11-17 192453](https://github.com/user-attachments/assets/cd7b5362-588f-4169-a7d7-6191acae804e)


![Captura de pantalla 2024-11-17 192646](https://github.com/user-attachments/assets/e6bec9cc-d15e-4119-9901-e6055a832cd3)



## Descripción del Proyecto:
El proyecto consiste en el diseño de un PCB utilizando EasyEDA para controlar los sensores de pH, conductividad electrica y turbidez del agua, mostrar los parametros del agua en una pantalla OLED. El sistema está basado en un microcontrolador **Arduino ESP32_Devkit_V4** y está alimentado por una batería de 5V. Se ha diseñado para que la información pueda mostrarse en tiempo real.

## Componentes Principales:

### ESP32_Devkit_V4
- **Función**: Es el microcontrolador principal que gestiona todas las señales y el procesamiento de datos del sensor de pH, conductividad y turbidez.
- **Conexiones principales**:
  - Alimentación por el pin **Vin** (batería de 5V).
  - Conexiones de datos y reloj (SPI) con la pantalla OLED.
  - Control de los servomotores para el paso del agua.

### Sensor de pH
- **Función**: Mide los niveles de pH del agua y envía los datos al microcontrolador para procesarlos.
- **Conexiones**:
  - **VCC** a 5V de la fuente externa.
  - **GND** al GND de la fuente externa.
  - Señal de salida a un pin analógico del microcontrolador(**GPIO_36**).

### Sensor de Conductividad
- **Función**: Mide la conductividad del líquido, proporcionando información sobre la concentración de iones.
- **Conexiones**:
  - **VCC** a 5V de la fuente externa.
  - **GND** al GND de la fuente externa.
  - Señal de salida a un pin analógico del microcontrolador (**GPIO_39**).

### Sensor de Turbidez
- **Función**: Detecta la turbidez (claridad) del líquido, que indica la cantidad de partículas suspendidas.
- **Conexiones**:
  - **VCC** a 5V de la fuente externa.
  - **GND** al GND de la fuente externa.
  - Señal de salida a un pin analógico del Arduino (**GPIO_34**).

### Pantalla OLED (SPI, 4 pines)
- **Función**: Muestra los valores medidos del pH, conductividad y turbidez en tiempo real.
- **Conexiones**:
  - **VCC** a 5V de la fuente externa.
  - **GND** al GND de la fuente externa.
  - **SDA** al pin **GPIO_21** del microcontrolador.
  - **SCK** al pin **GPIO_22** del microcontrolador.

### Servomotores (x2)
- **Función**: Los servomotores se encargan de realizar movimientos mecánicos en respuesta a las mediciones de los sensores.
- **Conexiones**:
  - **VCC** al pin de 5V del Arduino Nano.
  - **GND** al pin GND del Arduino Nano.
  - Señal de control a un pin digital del Arduino (**GPIO_18** y **GPIO_19**).

### Batería de 7.4V
- **Función**: Proporciona energía al sistema a través del pin **Vin** al ESP32_Devkit_V4, esta regulada la tensión a 5V para alimentar tanto el microcontrolador como los periféricos de los sensores. Ademas para el ruteo se retiro la bateria, ya que podemos hacer una conexion directa aun cuando la bateria no este dentro del PCB.

## Proceso de Diseño del PCB:

### Esquema:
- El primer paso fue crear el esquema eléctrico en EasyEDA, conectando todos los componentes según el diagrama del circuito.

### Conversión a PCB:
- Luego, el esquema se convirtió en un diseño de PCB, donde se colocaron estratégicamente los componentes para minimizar la longitud de las pistas y optimizar el espacio.

### Ruteo Automático:
- Se utilizó el ruteo automático para conectar todas las pistas en la PCB, utilizando la capa inferior:
  - **Capa inferior** (pistas en azul) para evitar cruces entre las pistas.

### Consideraciones de Diseño:
- Se dejó espacio para posibles expansiones.
- El **autoruteo** distribuyó las pistas en el PCB:
  - **Capa inferior** (en azul) el diseño se puedo realizar en una capa de la placa.


## Resultado Esperado:
El PCB permite  tiene las conexiones adecuadas para la lectura continua de los niveles de pH, conductividad y turbidez, además de la visualización en tiempo real de los valores en la pantalla OLED. El sistema es portátil gracias a la batería de de 7.4V, está diseñado para funcionar de manera eficiente con componentes de bajo consumo.

Durante el proceso de diseño, se presentaron algunas complicaciones con los componentes, ya que algunos no tenían los **footprints** adecuados. Esto requirió  buscar componentes en la biblioteca de EasyEDA para encontrar aquellos que fueran compatibles con el diseño del PCB.

