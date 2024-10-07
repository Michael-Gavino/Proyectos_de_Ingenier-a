# Entregable: Diseño de PCB y sus Componentes

## Descripción del Proyecto:
El proyecto consiste en el diseño de un PCB utilizando EasyEDA para controlar un sensor de pH y mostrar los valores en una pantalla OLED. El sistema está basado en un microcontrolador **Arduino Nano** y está alimentado por una batería de 9V. Se ha diseñado para monitorear niveles de pH y mostrar la información en tiempo real.

## Componentes Principales:

### Arduino Nano
- **Función**: Es el microcontrolador principal que gestiona todas las señales y el procesamiento de datos del sensor de pH.
- **Conexiones principales**:
  - Alimentación por el pin **Vin** (batería de 9V).
  - Conexiones de datos y reloj (SPI) con la pantalla OLED.

### Sensor de pH
- **Función**: Mide los niveles de pH en el líquido y envía los datos al Arduino para procesarlos.
- **Conexiones**:
  - **VCC** al pin de 5V del Arduino Nano.
  - **GND** al pin GND del Arduino Nano.
  - Señal de salida a un pin analógico del Arduino (ej. **A0**).

### Pantalla OLED (SPI, 4 pines)
- **Función**: Muestra los valores medidos del pH en tiempo real.
- **Conexiones**:
  - **VCC** al pin 5V del Arduino Nano.
  - **GND** al GND del Arduino Nano.
  - **SDA (MOSI)** al pin **D11** del Arduino Nano.
  - **SCK** al pin **D13** del Arduino Nano.

### Batería de 9V
- **Función**: Proporciona energía al sistema a través del pin **Vin** del Arduino Nano, que regula la tensión a 5V para alimentar tanto el Arduino como los periféricos.

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
- Se dejó espacio para posibles expansiones futuras (conectores adicionales).

## Resultado Esperado:
El PCB permite la lectura continua de los niveles de pH y la visualización en tiempo real de los valores en la pantalla OLED. El sistema es portátil gracias a la batería de 9V y está diseñado para funcionar de manera eficiente con componentes de bajo consumo.
