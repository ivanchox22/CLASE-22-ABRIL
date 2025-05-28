# COMO HACER USO DE LOS GEMELOS DIGITALES (QUANSER)

Los gemelos digitales son representaciones virtuales de sistemas físicos que permiten simular y analizar su comportamiento en un entorno controlado.  

# 1) Definiciones

>Gemelo Digital (Digital Twin: Réplica virtual de un sistema físico que emula su comportamiento en tiempo real mediante modelos computacionales y flujo bidireccional de datos, permitiendo simulación, monitoreo y predicción.

QUARC (Quanser Real-time Control: Plataforma de desarrollo para sistemas de control en tiempo real que se integra con MATLAB/Simulink, proporcionando bloques especializados para adquisición de datos y control de hardware Quanser.

**Qube-Servo 2**  
Definición: Dispositivo didáctico para control de posición angular que consta de un motor DC con encoder de alta resolución (4096 CPR), disco de inercia y circuitos de protección, utilizado en laboratorios de control automático.

**Stall Detection**  
Definición: Mecanismo de protección que detecta cuando un motor eléctrico recibe voltaje pero no gira (bloqueo), activando el apagado automático para prevenir daños por sobrecalentamiento.

**CPR (Counts Per Revolution)**  
Definición: Unidad de medida que indica el número de pulsos que genera un encoder óptico por cada revolución completa (360°) del eje del motor.

**HIL (Hardware-In-the-Loop)**  
Definición: Metodología de prueba que combina componentes físicos reales con modelos simulados, permitiendo validar algoritmos de control en condiciones seguras antes de su implementación final.

**Pulse Generator**  
Definición: Bloque de Simulink que genera señales cuadradas periódicas con parámetros configurables (amplitud, frecuencia y ciclo de trabajo), usado para excitar sistemas de control.

**Simulink Real-Time**  
Definición: Entorno de ejecución determinístico que permite implementar modelos de Simulink en sistemas embebidos o PCs dedicadas para control en tiempo real con precisión de microsegundos.

**Encoder Óptico**  
Definición: Sensor de posición que convierte el movimiento angular en pulsos digitales mediante un disco codificado y fotodetectores, proporcionando mediciones precisas de posición y velocidad.

**Control PID**  
Definición: Algoritmo de control retroalimentado que ajusta la señal de salida en función de tres componentes: Proporcional (error actual), Integral (error acumulado) y Derivativo (tasa de cambio del error).

# 2)  Requisitos Previos  
- **MATLAB** (versión R2021a+)  
- **Cuenta Quanser**: [Registro aquí](https://portal.quanser.com/)  
- **Complemento QUARC**  

# 3) PASO A PASO

En este apartado se podra visualizar el paso a paso para iniciar y utilizar el programa de Quanser y Matlab.

## 3.1 Instalación del Complemento Quanser Interactive Labs
- Abrir MATLAB.

- Descargar el complemento Quanser Interactive Labs desde el portal.

- Instalar el paquete siguiendo las instrucciones del asistente.

![image](https://github.com/user-attachments/assets/5ba8c5e4-a6d4-4e25-ae59-f07311455623)


🔹 Figura 1: Complemento Quanser Interactive Labs para gemelos digitales

# 4) CONCLUSIONES

# 5) REFERENCIAS
