# Reporte de Práctica: Moldes y Vaciado (Molding and Casting)

**Institución:** Universidad Iberoamericana Puebla  
**Materia:** [Nombre de la Asignatura]  
**Profesor:** Oliver  
**Fecha:** 17 de Abril, 2024  
**Semana:** Week 12  

---

## 1. Objetivos

* Revisar las Hojas de Datos de Seguridad (MSDS/SDS) de cada material de moldeo y vaciado.
* Realizar y comparar piezas de prueba utilizando distintos procesos (Maquinado CNC vs. Impresión 3D en resina SLA).
* Diseñar un contramolde en **SolidWorks** para ser impreso en una impresora 3D de resina SLA.

---

## 2. Materiales y Fichas de Seguridad (MSDS)

### Smooth-On Silicone 3030
* **Descripción:** Caucho de silicona con excelentes propiedades de trabajo.
* **Características:**
  * **Pot Life (Vida útil de mezcla):** 45 minutos.
  * **Tiempo de curado:** Curado completo durante la noche a temperatura ambiente.
  * **Proporción de mezcla:** 100A : 10B.

### Anycubic High-Speed UV Resin
* **Descripción:** Resina fotosensible para impresión SLA/DLP.
* **Características:**
  * **Temperatura de operación sugerida:** 18 – 35 °C.
  * **Precalentamiento opcional:** Máximo 60 °C.

### Cera de Tallado (Ferris Carving Wax Block - 1L)
* **Descripción:** Bloque de cera utilizable para fresado e inspección de acabados finos.

---

## 3. Comparativa de Procesos y Materiales

| Criterio | Cera Maquinada (Milled Wax) | Resina UV Anycubic (SLA) |
| :--- | :--- | :--- |
| **Reproduce detalles finos** | Sí | Sí (Resolución Z: 25 - 200 micras) |
| **Reglas de Diseño** | Solo ángulos positivos para maquinado. | Pieza hueca con agujeros, soportes y muros estructurados. |
| **Ventajas (Pros)** | - Área de trabajo grande (1.22 x 2.44 m).<br>- Variedad de acabados según la herramienta.<br>- Diferentes materiales utilizables.<br>- Reutilizable (se puede fundir la cera). | - Permite ángulos negativos (si la pieza es flexible para desmoldar).<br>- Proceso de preparación simple. |
| **Desventajas (Contras)** | - No reproduce ángulos negativos.<br>- Requiere cambio de herramientas para distintos acabados. | - Volumen de impresión reducido.<br>- Mayor costo.<br>- Fragilidad en los materiales. |
| **Agente Desmoldante** | No requiere. | No requiere. |
| **Costo Relativo** | ++ | +++ |
| **Tiempo Relativo** | 1:54 h | 1:43 h |

---

## 4. Metodología y Procesos

### A. Proceso de Maquinado de Molde (Router CNC)
1. **Diseño:** Diseñar el molde utilizando el software CAD preferido.
2. **Postprocesamiento:** Crear dos trayectorias de herramienta (*toolpaths*) a partir del CAD: una para desbaste (*roughing*) y otra para acabado (*finishing*).
3. **Setup:** Montar las herramientas y sujetar la pieza en el área de trabajo, asegurando rigidez total.
4. **Desbaste:** Ejecutar el maquinado con la herramienta de desbaste.
5. **Acabado:** Ejecutar el maquinado con la herramienta de acabado.

### B. Proceso de Impresión de Contramolde (SLA en SolidWorks)
1. **Diseño CAD:** Modelado del contramolde en **SolidWorks**.
2. **Postprocesamiento:** Preparación del archivo STL / Slicing para la impresora SLA.
3. **Preparación de Resina:** Ajuste de temperatura e inspección del tanque.
4. **Impresión 3D:** Proceso de fotopolimerización capa por capa.
5. **Drenado y Limpieza:** Lavado con alcohol isopropílico para eliminar exceso de resina.
6. **Curado:** Tratamiento UV posterior para alcanzar propiedades mecánicas finales.

### C. Proceso de Vaciado de Resina / Silicona
1. Preparación del equipo de protección personal (EPI) y ventilación del área.
2. Preparación de la mezcla (Proporción 100 A : 10 B).
3. Vertido del material dentro del molde.
4. Tiempo de reposo y curado.
5. Desmoldeo de la pieza final.

---

## 5. Conclusiones

* **Maquinado CNC (Cera):** El proceso mediante router CNC permite fabricar moldes de formatos más grandes. Al utilizar el bloque de cera, se evita el uso de agente desmoldante, obteniendo un acabado brillante y detallado. Además, presenta la ventaja sustentable de poder reutilizar el material fundiéndolo nuevamente.
* **Impresión en Resina SLA:** Presenta limitaciones de volumen de trabajo y fragilidad en el molde. Sin embargo, para la elaboración del contramolde diseñado en **SolidWorks**, permite obtener geometrías complejas que el maquinado CNC tradicional no puede lograr en ángulos negativos.