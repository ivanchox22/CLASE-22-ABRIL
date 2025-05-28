# COMO HACER USO DE LOS GEMELOS DIGITALES (QUANSER)

![image](https://github.com/user-attachments/assets/01916511-5fb9-4e7f-bc56-84fca18238f4)

🔹 *Figura 1: Quanser.* 

Los gemelos digitales son representaciones virtuales de sistemas físicos que permiten simular y analizar su comportamiento en un entorno controlado.  

# 1) Definiciones

> 🔑 Gemelo Digital (Digital Twin: Réplica virtual de un sistema físico que emula su comportamiento en tiempo real mediante modelos computacionales y flujo bidireccional de datos, permitiendo simulación, monitoreo y predicción.

> 🔑 QUARC (Quanser Real-time Control: Plataforma de desarrollo para sistemas de control en tiempo real que se integra con MATLAB/Simulink, proporcionando bloques especializados para adquisición de datos y control de hardware Quanser.

> 🔑 Qube-Servo 2: Dispositivo didáctico para control de posición angular que consta de un motor DC con encoder de alta resolución (4096 CPR), disco de inercia y circuitos de protección, utilizado en laboratorios de control automático.

> 🔑 Stall Detection: Mecanismo de protección que detecta cuando un motor eléctrico recibe voltaje pero no gira (bloqueo), activando el apagado automático para prevenir daños por sobrecalentamiento.

> 🔑 CPR (Counts Per Revolution): Unidad de medida que indica el número de pulsos que genera un encoder óptico por cada revolución completa (360°) del eje del motor.

> 🔑 HIL (Hardware-In-the-Loop): Metodología de prueba que combina componentes físicos reales con modelos simulados, permitiendo validar algoritmos de control en condiciones seguras antes de su implementación final.

> 🔑 Pulse Generator: Bloque de Simulink que genera señales cuadradas periódicas con parámetros configurables (amplitud, frecuencia y ciclo de trabajo), usado para excitar sistemas de control.

# 2) Requisitos Previos  

A continuación se detallan los requisitos mínimos necesarios para poder utilizar el software Quanser en conjunto con MATLAB. Es importante cumplir con estas especificaciones para garantizar el correcto funcionamiento de las herramientas.  

- **MATLAB** (versión R2021a+)  
  *Se requiere una versión reciente de MATLAB debido a las dependencias de librerías y funciones utilizadas por QUARC.*  
- **Cuenta Quanser**: [Registro aquí](https://portal.quanser.com/)  
  *Es necesario registrarse en el portal de Quanser para acceder a descargas de software, licencias y documentación técnica.*  
- **Complemento QUARC**  
  *QUARC es un middleware esencial para la comunicación en tiempo real entre MATLAB/Simulink y los dispositivos Quanser.*  

# 3) PASO A PASO  

En este apartado se detalla el proceso de configuración inicial para integrar Quanser Interactive Labs con MATLAB, incluyendo capturas ilustrativas.  

## 3.1 Instalación del Complemento Quanser Interactive Labs  

*Este procedimiento instala las bibliotecas necesarias para la creación y operación de gemelos digitales en entornos Quanser:*  

- **Abrir MATLAB**  
  *Inicie MATLAB con privilegios de administrador para evitar conflictos durante la instalación.*  

- **Descargar el complemento Quanser Interactive Labs desde el portal**  
  *El paquete de instalación está disponible en la sección "Downloads" de su cuenta Quanser después del login.*  

- **Instalar el paquete siguiendo las instrucciones del asistente**  
  *Acepte los términos de licencia y seleccione la opción "Typical Install" a menos que necesite componentes personalizados.*  

![image](https://github.com/user-attachments/assets/5ba8c5e4-a6d4-4e25-ae59-f07311455623)  
🔹 *Figura 2: Interfaz del complemento Quanser Interactive Labs para gemelos digitales, mostrando el panel de control de dispositivos virtuales.*  


## 3.2 Fases de la Simulación en Simulink con Bloques QUARC

En el presente laboratorio se desarrollará un modelo básico en Simulink utilizando bloques pertenecientes al entorno QUARC, con el objetivo principal de controlar un motor de corriente continua (DC) y medir en tiempo real el ángulo de rotación de su eje. Esta práctica forma parte fundamental del proceso de aprendizaje en sistemas de control en tiempo real, permitiendo al estudiante integrar conocimientos teóricos con su aplicación práctica en entornos de simulación interactiva.

El sistema se construirá mediante la lectura de datos de un encoder conectado al eje del motor, cuya señal será procesada para obtener el desplazamiento angular. A través de un bloque de ganancia, estos pulsos se transformarán a unidades físicas como grados o radianes. Posteriormente, la señal será utilizada como retroalimentación dentro de un lazo de control, el cual puede configurarse manualmente o mediante un controlador automático (como un PID), permitiendo generar una salida analógica que gobierna el comportamiento del motor.

Asimismo, se implementarán mecanismos de visualización que permiten monitorear las variables clave del sistema, así como herramientas de conmutación y detección de fallos, como la detección de estancamiento del motor (stall detection). Esta última funcionalidad es esencial para garantizar la seguridad del sistema, ya que puede alertar si el motor deja de moverse pese a recibir una señal de control.

En conjunto, esta experiencia permitirá a los participantes familiarizarse con el flujo de trabajo en un entorno de programación en tiempo real, comprender la importancia de la adquisición de datos y el control digital, y establecer una comunicación efectiva entre el modelo computacional y la planta física o simulada, mediante el uso de sensores y actuadores virtuales conectados a través de hardware-in-the-loop (HIL). El conocimiento adquirido en esta práctica es directamente aplicable en áreas como automatización industrial, robótica y control de procesos.

![image](https://github.com/user-attachments/assets/67cdb41b-7ac0-431d-b958-cd658dfe51ee)

🔹 *Figura 3: Simulación de prueba.*  

A continuación, se describen las principales fases de la simulación realizada para el control de un motor de corriente continua utilizando bloques QUARC en Simulink:

### 1. HIL Read Encoder (Lectura del encoder)
- **Función:** Lee la posición angular del eje del motor en tiempo real a través de un encoder. Este dispositivo emite pulsos en función del desplazamiento del eje.

### 2. Gain (Ganancia)
- **Función:** Convierte los pulsos del encoder en unidades físicas como grados o radianes. Esto facilita la interpretación y el procesamiento de la señal en el sistema de control.

### 3. Display / Scope (Visualización)
- **Función:** Muestra la señal de posición angular del motor para facilitar el monitoreo durante la simulación.

### 4. Controlador (PID u otro)
- **Función:** Genera una señal de control a partir del error entre la posición deseada y la posición real. Su objetivo es minimizar ese error para lograr un comportamiento deseado del motor.

### 5. Manual Switch (Conmutador manual)
- **Función:** Permite seleccionar entre una entrada de control manual (por ejemplo, un valor constante) o la salida del controlador automático.

### 6. HIL Write Analog (Salida analógica)
- **Función:** Envía la señal analógica al motor. Esta señal controla el comportamiento del motor, como la velocidad o el torque.

### 7. Stall Detection (Detección de estancamiento)
- **Función:** Monitorea si el motor se encuentra detenido cuando debería estar en movimiento. Si se detecta una condición de estancamiento, puede generar una alarma o interrumpir la operación.



# 4) CONCLUSIONES  

*La integración de Quanser con MATLAB mediante QUARC permite desarrollar sistemas de control avanzados con capacidades de simulación en tiempo real. Es fundamental seguir los requisitos y pasos detallados para evitar errores de compatibilidad. Esta herramienta es particularmente útil para prototipado rápido en entornos académicos e industriales.*  

# 5) REFERENCIAS  

*En esta sección se listan las fuentes técnicas utilizadas para la elaboración de la guía:*  
- Documentación oficial de Quanser Interactive Labs (2023)  
- MATLAB R2021a+ System Requirements (MathWorks)  
- QUARC Installation Guide v2.4 (Quanser Inc.)  
