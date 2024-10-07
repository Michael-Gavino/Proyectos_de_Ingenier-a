# **Guía de diseño y ensayo de modelos 3D para piezas immpresas**

## **1. Importar geometría**
- Importamos la geometría desde **OnShape**.
- Aseguramos de que las piezas se importen correctamente y con sus colores originales.

![Importar](https://github.com/user-attachments/assets/2174daff-f873-4249-9df2-b5931d9c71f0)

## **2. Crear simulación**
- Seleccionamos "análisis estructural" y creamos una simulación estática.

![Simulación](https://github.com/user-attachments/assets/ec56048c-c82c-4ec4-ac39-655494104e4e)

## **3. Mallado (meshing)**
- Seleccionamos las piezas a mallar.
- Ajustamos la finura del mallado, priorizando zonas críticas (como el cilindro).
- Refinamos el mallado en áreas específicas.

![Mallado](https://github.com/user-attachments/assets/14be93f9-607e-4487-9126-41a8d9a1fb3d)

## **4. Asignación de materiales**
- Seleccionamos y aplicamos material a las piezas (PLA).

![Materiales](https://github.com/user-attachments/assets/228e7154-0fde-418c-9043-d4f03f3357a2)

## **5. Condiciones de soporte y carga**
- Establecemos las caras que estarán fijas en la simulación.
- Aplicamos una fuerza (-19.6 en el eje Y por ser 2 litros de agua y de diametro el cilindro tiene 10 cm).

![Soporte](https://github.com/user-attachments/assets/a9b6731f-4a1d-4563-96e8-83335cc2fcdf)

## **6. Simulación y refinamiento**
- Generamos el mallado inicial y aplicar refinamientos locales si es necesario.
- Ejecutamos la simulación en pasos incrementales si es un análisis no lineal.

![Refinamiento](https://github.com/user-attachments/assets/11983286-43f7-4bc7-a0b0-7275b36cb318)

## **7. Revisión de resultados**
- Revisamos los resultados de esfuerzo (en pascales o megapascales).
- Analizamos los resultados y ajustamos parámetros.

---

# **Casos de Simulación**

### **Caso 1: Análisis de grietas por cargas pulsantes**
- **Descripción:** La carcasa está expuesta repetidamente a cargas pulsantes y vibraciones. Se debe analizar la formación de grietas o fracturas mediante elementos finitos.

### **Caso 2: Análisis de deformación térmica**
- **Descripción:** La carcasa protege una placa electrónica cerca de un motor DC expuesto a altas temperaturas. Se debe analizar la deformación térmica en estas condiciones.

### **Caso 3: Análisis de torsión**
- **Descripción:** La carcasa experimenta fuerzas de torsión. Se debe analizar cómo la densidad de relleno y la orientación de impresión afectan la resistencia estructural.

---

# **Equipamiento del Laboratorio**

- **Impresoras 3D:**
  - Ender 3-S1 (Creality)
  - P1S (Bambu Lab)

- **Materiales Utilizados:**
  - PLA
---

# **Referencias**

1. Otegui, J. L. (2013). *Análisis de fallas: fundamentos y aplicaciones en componentes mecánicos*. Mar del Plata: EUDEM.
2. MakerBot Support. (n.d.). *3D model design guidelines for printed parts*. Recuperado de: [MakerBot Support](https://support.makerbot.com/s/article/1667337954399)
3. SimScale Documentation. Recuperado de: [SimScale Docs](https://www.simscale.com/docs/simulation-setup/connectors/)
