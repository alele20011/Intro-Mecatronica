# Reporte de Práctica: Temporizador 555 en Modo Astable

## 1. Tabla de Medición vs. Teoría

Para el cálculo teórico de la corriente del LED ($I_{LED}$), se toma un voltaje directo del LED $V_f \approx 2.0\text{ V}$:

$$I_{LED (teórico)} = \frac{V_{out} - V_f}{R_{LED}} = \frac{3.5\text{ V} - 2.0\text{ V}}{330\ \Omega} \approx 4.55\text{ mA}$$

$$I_{LED (medido)} = \frac{2.9\text{ V} - 2.0\text{ V}}{330\ \Omega} \approx 2.73\text{ mA}$$

$$\% \text{ de Error} = \left| \frac{\text{Valor Teórico} - \text{Valor Medido}}{\text{Valor Teórico}} \right| \times 100$$

| Magnitud | Teórico (calculado) | Medido | % de error | ¿Con qué lo mediste? |
| :--- | :--- | :--- | :--- | :--- |
| **Vcc (V)** | $5.0\text{ V}$ | $5.01\text{ V}$ | $0.20\%$ | Multímetro (V, en paralelo) |
| **V de salida en ALTO (V)** | $3.5\text{ V}$ ($\approx Vcc - 1.5$) | $2.90\text{ V}$ | $17.14\%$ | Osciloscopio / Multímetro |
| **Frecuencia (Hz)** | $0.69\text{ Hz}$ | $0.685\text{ Hz}$ ($684.9\text{ mHz}$) | $0.72\%$ | Osciloscopio (Measure) |
| **Duty (%)** | $52.40\%$ | $49.53\%$ | $5.48\%$ | Osciloscopio (Measure) |
| **I del LED (mA)** | $4.55\text{ mA}$ | $2.73\text{ mA}$ | $40.00\%$ | Multímetro (A, en serie) / Calculado con $V_{out}$ medido |

---

## 2. Análisis del Error: ¿Por qué no dio exacto?

El componente que **domina el error** en la temporización del circuito es el **capacitor electrolítico de $100\ \mu\text{F}$**.

* **Tolerancia del capacitor:** Los capacitores electrolíticos tienen una tolerancia muy amplia (típicamente entre $-20\%$ y $+80\%$). Una ligera variación respecto al valor nominal de $100\ \mu\text{F}$ altera directamente las constantes de tiempo de carga ($t_{ALTO}$) y descarga ($t_{BAJO}$), desviando la frecuencia teórica y el ciclo de trabajo (*duty cycle*).
* **Tolerancia de resistores:** Las resistencias de película de carbón comerciales tienen una tolerancia de solo $\pm 5\%$, por lo que su contribución al porcentaje de error global es considerablemente menor comparada con la del capacitor.
* **Caída de voltaje en la salida del 555:** La etapa de salida interna del transistor bipolar del NE555 presenta una caída de tensión en estado ALTO. Aunque en teoría se aproxima como $Vcc - 1.5\text{ V}$ ($3.5\text{ V}$), en la medición real se registraron $2.90\text{ V}$ debido a la carga que demanda el LED y la resistencia limitadora, lo que explica la diferencia en la corriente calculada.

---

## 3. Bitácora de Errores

### Error 1: Polarización del LED
* **Qué falló:** Al alimentar la protoboard con los $5\text{ V}$ regulados, el LED no parpadeaba ni emitía luz.
* **Cómo se encontró:** Se comprobó con el osciloscopio que la patilla 3 de salida del NE555 sí estaba entregando la onda cuadrada esperada. Al inspeccionar físicamente el componente, se identificó que las terminales del LED (ánodo y cátodo) estaban invertidas.
* **Cómo se resolvió:** Se rotó el LED $180^\circ$ en la protoboard, conectando correctamente el ánodo al nodo de la resistencia de $330\ \Omega$ (proveniente del pin 3) y el cátodo a la línea de tierra ($GND$).

### Error 2: Colocación Errónea de las Resistencias Temporizadoras ($R_A$ y $R_B$)
* **Qué falló:** El circuito no oscilaba al inicio debido a una conexión errónea de nodos entre las resistencias temporizadoras y el integrado.
* **Cómo se encontró:** Se siguió el diagrama esquemático línea por línea con el multímetro en modo continuidad. Se observó que el puente entre el pin 2 (*TRIGGER*) y el pin 6 (*THRESHOLD*) no estaba conectado al nodo común entre $R_B$ y el capacitor $C$.
* **Cómo se resolvió:** Se reubicaron los terminales en la protoboard de modo que $R_A$ ($1\text{ k}\Omega$) quedara entre $Vcc$ y el pin 7 (*DISCHARGE*), $R_B$ ($10\text{ k}\Omega$) entre el pin 7 y la unión de los pines 2 y 6, y el capacitor de $100\ \mu\text{F}$ entre ese mismo nodo y tierra.





//Se usó Claude para la elaboracion del codigo en Visual Studio y formato de la practica//