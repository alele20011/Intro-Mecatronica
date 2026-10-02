# Ficha de Estación - Mecanismos Aplicados

**Asignatura:** Introducción a la Mecatrónica  
**Proyecto:** Carro de Fútbol Bluetooth ($20 \times 20\text{ cm}$) con 2 Motores Reductores Amarillos (TT Motors) y Puente H  
**Objetivo:** Jugar fútbol robótico y anotar una pelota de ping-pong en la portería  

---

## Tabla de Evaluación de Estaciones

| Estación / Mecanismo | ¿Qué transforma? <br> *(vel $\leftrightarrow$ par, rot $\leftrightarrow$ trasl, cont $\leftrightarrow$ inter, cambio de eje)* | Relación estimada <br> *(cuenta dientes o vueltas)* | ¿Reversible o autobloqueante? | ¿Dónde lo has visto en la vida real? *(Ejemplos cotidianos)* | ¿Dónde serviría en el carro de fútbol ($20 \times 20\text{ cm}$)? |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **1. Diferencial** *(Differential)* | **Cambio de eje ($90^\circ$) + Reparto de Par:** Distribuye el giro del motor a dos ejes independientes ajustando la velocidad de cada uno según la resistencia. | $1:1$ (piñón impulsor a caja diferencial); variación dinámica en las salidas. | **Reversible:** Si giras las ruedas con la mano, el eje de entrada gira. | **Autos familiares / Camionetas:** Permite que la rueda externa gire más rápido que la interna al dar una vuelta en una esquina. | **No se usa físicamente:** El carro usa dirección diferencial por software (2 motores amarillos independientes). Serviría si usáramos 1 solo motor principal. |
| **2. Cicloidal** *(Cycloidal drive)* | **Vel $\leftrightarrow$ Par:** Reduce drásticamente la velocidad para multiplicar la fuerza de giro (torque) en un tamaño muy compacto. | $10\text{ pernos / lóbulos}$. Relación aproximada $10:1$ ($1\text{ paso}$ por vuelta completa). | **Autobloqueante / Difícil de revertir:** Debido al roce y contacto constante de los lóbulos. | **Desarmador eléctrico inalámbrico / Taladros pequeños:** Para entregar mucha fuerza para atornillar en un espacio reducido. | **Mecanismo pateador:** Para acumular suficiente fuerza con un motor pequeño y golpear la pelota de ping-pong hacia la portería. |
| **3. Cardán** *(Universal joint)* | **Transmisión angular:** Transmite rotación continua entre dos ejes que están desalineados o formando un ángulo. | $1:1$ (Gira a la misma velocidad en entrada y salida). | **Reversible:** Al girar un eje, el otro responde inmediatamente. | **Extensión flexible de desarmador / Barra de camioneta:** Para apretar tornillos en esquinas o enviar fuerza a las ruedas traseras. | **Ejes inclinados:** Para conectar los motores a las ruedas si el carro tuviera suspensión o las ruedas estuvieran inclinadas. |
| **4. Obturador de láminas** *(Aperture / Iris)* | **Rotación $\rightarrow$ Cierre coordinado:** La rotación de una palanca/anillo abre o cierra varias láminas concéntricamente. | $5\text{ láminas}$ sincronizadas por $1\text{ palanca/anillo}$. | **Reversible:** Se abre y cierra manualmente sin trabarse. | **Cámara del celular / Rejilla de aire:** Regula la entrada de luz en la cámara o el paso de aire en una ventilación. | **Atrapador de pelota:** Instalado en el frente para cerrar las láminas levemente sobre la pelota de ping-pong y asegurarla antes de tirar. |
| **5. Cruz de Génova** *(Geneva drive)* | **Cont $\rightarrow$ Inter:** Transforma giro continuo en impulsos paso a paso deteniéndose entre cada ciclo. | $6\text{ ranuras}$. $1\text{ vuelta}$ del disco mueve la cruz $\frac{1}{6}$ de vuelta ($60^\circ$). Relación $6:1$. | **Autobloqueante:** Entre giros la rueda queda fija y trancada mecánicamente. | **Reloj de pared / Dispensador de dulces:** Para mover las manecillas a pasos o soltar una pastilla/dulce a la vez. | **Dispensador de pelotas:** Para alimentar pelotas de ping-pong de una en una al sistema de disparo. |
| **6. Corona** *(Crown gear)* | **Cambio de eje ($90^\circ$) + Vel $\leftrightarrow$ Par:** Cambia la dirección del giro a $90^\circ$ usando un engrane plano. | $\approx 28\text{ dientes}$ en la corona y $14$ en el piñón. Relación $2:1$. | **Reversible:** Puedes girar el mecanismo desde la corona o desde el piñón. | **Batidora manual de cocina / Taladro de mano:** El mango gira de forma horizontal y mueve los batidores verticales. | **Aprovechamiento de espacio:** Para acostar los motores amarillos dentro del chasis de $20 \times 20\text{ cm}$ y transmitir el giro a las ruedas. |

---

## Análisis Técnico Aplicado al Proyecto

### 1. Dimensiones y Restricciones del Carro
* **Chasis:** $20 \times 20\text{ cm}$.
* **Actuadores:** $2$ Motores reductores amarillos (relación interna $1:48$).
* **Controlador de Potencia:** Puente H (L298N / TB6612FNG) controlado por Bluetooth.
* **Objetivo Dinámico:** Manipular y anotar una pelota de ping-pong (diámetro $\approx 40\text{ mm}$, masa $\approx 2.7\text{ g}$).

### 2. Dirección Diferencial por Software
En lugar de utilizar un mecanismo físico de **Diferencial (Mecanismo 1)**, el proyecto implementa dirección diferencial electrónica.
* **Avance en línea recta:**  
  $$v_{\text{der}} = v_{\text{izq}} \implies \omega = 0$$
* **Giro sobre su propio eje (rotación dentro del espacio de $20 \times 20\text{ cm}$):**  
  $$v_{\text{der}} = -v_{\text{izq}} \implies v_{\text{centro}} = 0, \quad \omega = \frac{2 \cdot v_{\text{der}}}{L}$$
  Donde $L$ es la distancia entre ruedas ($L \approx 0.16\text{ m}$).

### 3. Integración de Mecanismos en el Proyecto
1. **Reductor Cicloidal (Mecanismo 2):** Permite obtener gran par en un tamaño compacto para accionar el percutor o pateador de la pelota.
2. **Obturador de Láminas (Mecanismo 4):** Ubicado en la bahía frontal para sujetar la pelota de ping-pong mientras el carro maniobra en la cancha.
3. **Engranaje Corona (Mecanismo 6):** Ayuda a reorientar la transmisión de potencia a $90^\circ$ optimizando la distribución de componentes en el chasis de $20 \times 20\text{ cm}$.