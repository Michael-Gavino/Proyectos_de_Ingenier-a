# Entregable: Diseño de PCB y sus Componentes
![Schematic_Circuito2 0_2024-10-21](https://github.com/user-attachments/assets/5888af52-da0f-409d-9c46-a5a7b0e2a90a)


![Captura de pantalla 2024-10-21 224711](https://github.com/user-attachments/assets/94db9ee0-00cb-4c71-adf4-cd9cde203830)


![Captura de pantalla 2024-10-21 181548](https://github.com/user-attachments/assets/318c66cd-ecf2-4931-bf34-3f56fe039028)


![Captura de pantalla 2024-10-21 182148](https://github.com/user-attachments/assets/4a407b6a-250e-4dd6-8dc8-cd3b26d83344)


## Descripción del Proyecto:
El proyecto consiste en el diseño de un PCB utilizando EasyEDA para controlar los sensores de pH, conductividad electrica y turbidez del agua, mostrar los parametros del agua en una pantalla OLED. El sistema está basado en un microcontrolador **Arduino Nano** y está alimentado por una batería de 9V. Se ha diseñado para que la información pueda mostrarse en tiempo real.

## Componentes Principales:

### Arduino Nano
- **Función**: Es el microcontrolador principal que gestiona todas las señales y el procesamiento de datos del sensor de pH.
- **Conexiones principales**:
  - Alimentación por el pin **Vin** (batería de 9V).
  - Conexiones de datos y reloj (SPI) con la pantalla OLED.

### Sensor de pH
- **Función**: Mide los niveles de pH del agua y envía los datos al Arduino para procesarlos.
- **Conexiones**:
  - **VCC** al pin de 5V del Arduino Nano.
  - **GND** al pin GND del Arduino Nano.
  - Señal de salida a un pin analógico del Arduino(**A3**).

### Sensor de Conductividad
- **Función**: Mide la conductividad del líquido, proporcionando información sobre la concentración de iones.
- **Conexiones**:
  - **VCC** al pin de 5V del Arduino Nano.
  - **GND** al pin GND del Arduino Nano.
  - Señal de salida a un pin analógico del Arduino (**A2**).

### Sensor de Turbidez
- **Función**: Detecta la turbidez (claridad) del líquido, que indica la cantidad de partículas suspendidas.
- **Conexiones**:
  - **VCC** al pin de 5V del Arduino Nano.
  - **GND** al pin GND del Arduino Nano.
  - Señal de salida a un pin analógico del Arduino (ej. **A1**).

### Pantalla OLED (SPI, 4 pines)
- **Función**: Muestra los valores medidos del pH, conductividad y turbidez en tiempo real.
- **Conexiones**:
  - **VCC** al pin 5V del Arduino Nano.
  - **GND** al GND del Arduino Nano.
  - **SDA (MOSI)** al pin **D11** del Arduino Nano.
  - **SCK** al pin **D13** del Arduino Nano.

### Servomotores (x2)
- **Función**: Los servomotores se encargan de realizar movimientos mecánicos en respuesta a las mediciones de los sensores.
- **Conexiones**:
  - **VCC** al pin de 5V del Arduino Nano.
  - **GND** al pin GND del Arduino Nano.
  - Señal de control a un pin digital del Arduino (**A4** y **A5**).

### Batería de 9V
- **Función**: Proporciona energía al sistema a través del pin **Vin** del Arduino Nano, que regula la tensión a 5V para alimentar tanto el Arduino como los periféricos. Ademas para el ruteo se retiro la bateria, ya que podemos hacer una conexion directa aun cuando la bateria no este dentro del PCB.

## Proceso de Diseño del PCB:

### Esquema:
- El primer paso fue crear el esquema eléctrico en EasyEDA, conectando todos los componentes según el diagrama del circuito.

### Conversión a PCB:
- Luego, el esquema se convirtió en un diseño de PCB, donde se colocaron estratégicamente los componentes para minimizar la longitud de las pistas y optimizar el espacio.

### Ruteo Automático:
- Se utilizó el ruteo automático para conectar todas las pistas en la PCB, utilizando dos capas:
  - **Capa superior** (pistas en rojo).
  - **Capa inferior** (pistas en azul) para evitar cruces entre las pistas.

### Consideraciones de Diseño:
- Se utilizó una resistencia **pull-up** en las líneas de comunicación SPI para evitar errores en la transmisión de datos entre el Arduino Nano y la pantalla OLED.
- Se dejó espacio para posibles expansiones.
- El **autoruteo** distribuyó las pistas en ambos lados del PCB:
  - **Capa superior** (en rojo) para algunas conexiones.
  - **Capa inferior** (en azul) para evitar cruces y mantener el diseño compacto.


## Resultado Esperado:
El PCB permite  tiene ls conexiones adecuadas para la lectura continua de los niveles de pH, conductividad y turbidez, además de la visualización en tiempo real de los valores en la pantalla OLED. El sistema es portátil gracias a la batería de 9V y está diseñado para funcionar de manera eficiente con componentes de bajo consumo.

Durante el proceso de diseño, se presentaron algunas complicaciones con los componentes, ya que algunos no tenían los **footprints** adecuados. Esto requirió  buscar componentes en la biblioteca de EasyEDA para encontrar aquellos que fueran compatibles con el diseño del PCB.

