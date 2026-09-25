# Propuesta de Proyecto: Carrito Robot Futbolista

## 1. Objetivo
Diseñar y construir un robot móvil tipo carrito para competir y ganar el torneo de fútbol robótico. El sistema integrará un control inalámbrico preciso mediante Bluetooth, un chasis ergonómico y defensivo, y mecanismos específicos para maniobrar y anotar goles, garantizando una alta competitividad y el cumplimiento estricto de los estándares de seguridad y funcionamiento.

---

## 2. Requisitos del Sistema

### 2.1. Requisitos Obligatorios (Funcionales y de Restricción)
* **R1. Control Bluetooth:** Movimiento en direcciones básicas (adelante, atrás, izquierda, derecha y alto) mediante comandos Bluetooth.
* **R2. Control de Velocidad:** Variación de velocidad mediante PWM con al menos 3 niveles definidos.
* **R3. Documentación del Protocolo:** Documentación técnica completa en el portafolio sobre el mapeo de comandos.
* **R4. Sistema Failsafe:** Detención automática inmediata del vehículo si se pierde la conexión o no se reciben comandos durante un tiempo mayor o igual a 1 segundo.
* **R5. Interruptor Físico:** Interruptor principal de encendido/apagado accesible desde el exterior sin necesidad de desarmar la estructura.
* **R6. Alimentación Separada:** Líneas de alimentación independientes para motores y para el microcontrolador ESP32, compartiendo una línea de tierra (GND) común.
* **R7. Cableado Ordenado:** Enrutamiento de cables sujeto y protegido para evitar enredos o desconexiones durante el juego.
* **R8. Superficie Plana Superior:** Área plana horizontal despejada en la parte superior para colocar el marcador ArUco del proyecto.
* **Restricción de Dimensiones:** Huella máxima de 20 x 20 cm para asegurar maniobrabilidad en cancha.

### 2.2. Requisitos Propios e Innovaciones
* **Tracción Omnidireccional:** Integración de ruedas omnidireccionales para desplazamientos laterales y rotaciones fluidas sin cambiar la orientación del chasis.
* **Aplicación Móvil Propia:** Interfaz de usuario personalizada en App Inventor/Flutter para un control ergonómico mediante botones directos.
* **Mecanismo de Tiro:** Sistema de pateo o impulso para el balón integrado en el frente del chasis.
* **Chasis Defensivo y Protegido:** Diseño exterior ergonómico que proteja la electrónica interna y permita bloquear ataques sin dañar mecánicamente a los oponentes.

---

## 3. Arquitectura del Sistema (Diagrama en Bloques)
+-----------------------------------------------------------------------+
|                            MÓVIL / APP                                |
|           [ Interfaz de Control App Personalizada ]                   |
+-----------------------------------------------------------------------+
                                   |
                                   | (Bluetooth / SPP)
                                   v
+-----------------------------------------------------------------------+
|                         SISTEMA PRINCIPAL                             |
|                                                                       |
|  +-------------------+        PWM / GPIO       +-------------------+  |
|  |                   | ----------------------> | Driver TB6612FNG  |  |
|  | Microcontrolador  |                         +-------------------+  |
|  |   ESP32 DevKit    |                                   |            |
|  |   (Failsafe 1s)   |                                   | Salida     |
|  |                   |                                   v            |
|  +-------------------+                         +-------------------+  |
|            ^                                   |  Motores TT con   |  |
|            |                                   | Caja Reductora y  |  |
|            | Status / Alimentación             |  Ruedas Omni      |  |
|            |                                   +-------------------+  |
+-----------------------------------------------------------------------+
             ^                                             ^
             |                                             |
+--------------------------+                 +--------------------------+
|  Fuente Alimentación     |                 |  Fuente Alimentación     |
|  Lógica (ESP32)          |                 |  Motores (Independiente) |
+--------------------------+                 +--------------------------+
             |                                             |
             +------------------- GND ---------------------+
                                (Común)
---

## 4. Presupuesto Preliminar y BOM (Bill of Materials)

| Componente | Función / Descripción | Estado / Origen | Costo Aprox. (MXN) |
| :--- | :--- | :--- | :--- |
| ESP32 DevKit V1 | Microcontrolador principal con Bluetooth | Prestado | $0.00 |
| Driver TB6612FNG | Controlador de potencia para motores | Prestado | $0.00 |
| Motores TT con caja reductora (2 uds.) | Sistema de tracción | Prestado | $0.00 |
| Ruedas Omnidireccionales | Desplazamiento multidireccional | Comprado | $180.00 |
| Baterías 18650 con portapilas / LiPo | Alimentación de motores y lógica | Reutilizado | $0.00 |
| Interruptor de Encendido/Apagado | Control de energía externo | Reutilizado | $0.00 |
| Chasis Impreso en 3D (20 x 20 cm) | Estructura defensiva y soporte mecánico | Impresión propia | $150.00 |
| Cableado y Material de Sujeción | Ordenamiento (R7) y conexiones | Reutilizado | $0.00 |
| Mecanismo de Tiro | Impulsor mecánico para pelota | Reutilizado / 3D | $50.00 |
| **TOTAL ESTIMADO** | | | **$380.00** |

---

## 5. Plan de Trabajo por Semanas

* **Semana 1: Desarrollo Electrónico, Control y Aplicación**
  * Montaje del circuito base: ESP32, TB6612, motores y fuentes de alimentación con GND común.
  * Programación del protocolo de comunicación Bluetooth y control de velocidad por PWM (3 niveles).
  * Implementación y validación del algoritmo Failsafe (desconexión <= 1 segundo).
  * Creación de la interfaz gráfica en la App móvil personalizada.

* **Semana 2: Diseño Mecánico, Chasis y Mecanismo de Tiro**
  * Diseños CAD del chasis ($20 \times 20$ cm) optimizado para defensa e integración de superficie plana superior (R8).
  * Integración de ruedas omnidireccionales y diseño del mecanismo de tiro.
  * Fabricación mediante impresión 3D y ensamble general de componentes mecánicos y eléctricos.

* **Semana 3: Integración, Pruebas y Calibración**
  * Pruebas de campo (maniobrabilidad, estabilidad y respuesta del mecanismo de tiro).
  * Verificación de requisitos obligatorios (R1 a R8).
  * Corrección de errores de código, ajuste de cableado y balance de peso.

---

## 6. Criterios de Éxito
* Cumplimiento del 100% de los requisitos funcionales (R1 a R8) y restricciones de dimensiones.
* Operación continua de la App móvil personalizada y respuesta inmediata del sistema Failsafe.
* Desempeño efectivo en cancha anotando goles y defendiendo la portería durante el torneo.

---

## 7. Análisis de Riesgos y Plan B

| Riesgo Identificado | Nivel de Impacto | Plan B (Estrategia de Mitigación) |
| :--- | :--- | :--- |
| Falla o retraso en la impresión 3D del chasis | Alto | Fabricación de un chasis liviano utilizando cartón rígido o acrílico mediante corte manual, manteniendo las dimensiones de 20 x 20 cm. |
| Pérdida de paquetes o latencia en Bluetooth | Medio | Optimizar el buffer de recepción en el ESP32 y reajustar el intervalo de envío de comandos en la App. |
| Deslizamiento o falta de tracción en ruedas omnidireccionales | Medio | Añadir bandas de alta fricción en los rodillos o sustituir temporalmente por ruedas estándar de goma. |
| Ruido eléctrico o reinicios del ESP32 por consumo de motores | Alto | Instalar capacitores de desacoplo y verificar el aislamiento eléctrico estricto con GND común. |
