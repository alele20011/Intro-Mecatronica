<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Reporte de Práctica: Ensambles en SolidWorks y Corte Láser</title>
<style>
  @page {
    size: A4;
    margin: 20mm 18mm 20mm 18mm;
  }

  body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    font-size: 10pt;
    line-height: 1.6;
    color: #2D3748;
    margin: 0;
    padding: 20px;
    background-color: #FFFFFF;
  }

  /* Encabezado Principal */
  .header-container {
    border-bottom: 3px solid #2B6CB0;
    padding-bottom: 12px;
    margin-bottom: 24px;
  }

  .header-container h1 {
    font-size: 18pt;
    color: #1A365D;
    margin: 0 0 6px 0;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  .header-container .subtitle {
    font-size: 11pt;
    color: #4A5568;
    font-weight: 600;
  }

  /* Tabla de Datos / Metadatos */
  .meta-table {
    width: 100%;
    margin-bottom: 20px;
    border-collapse: collapse;
    background-color: #F7FAFC;
    border: 1px solid #E2E8F0;
    border-radius: 4px;
  }

  .meta-table td {
    padding: 8px 12px;
    font-size: 9.5pt;
    border: none;
  }

  .meta-table td strong {
    color: #2D3748;
  }

  /* Secciones y Subsecciones */
  h2 {
    font-size: 12pt;
    color: #1A365D;
    border-left: 4px solid #2B6CB0;
    padding-left: 8px;
    margin-top: 22px;
    margin-bottom: 10px;
    text-transform: uppercase;
  }

  h3 {
    font-size: 10.5pt;
    color: #2B6CB0;
    margin-top: 14px;
    margin-bottom: 6px;
  }

  p {
    margin: 0 0 10px 0;
    text-align: justify;
  }

  /* Cajas de Destaque / Conceptos Clave */
  .callout-box {
    background-color: #EBF8FF;
    border-left: 4px solid #3182CE;
    padding: 10px 14px;
    margin: 12px 0;
    border-radius: 0 4px 4px 0;
  }

  .callout-box p {
    margin: 0;
    color: #2C5282;
  }

  /* Tablas de Materiales */
  table.data-table {
    width: 100%;
    border-collapse: collapse;
    margin: 12px 0 18px 0;
    font-size: 9pt;
  }

  table.data-table th {
    background-color: #2D3748;
    color: #FFFFFF;
    text-align: left;
    padding: 8px 10px;
    font-weight: 600;
  }

  table.data-table td {
    padding: 8px 10px;
    border-bottom: 1px solid #E2E8F0;
    vertical-align: top;
  }

  table.data-table tr:nth-child(even) {
    background-color: #F7FAFC;
  }

  .table-danger th {
    background-color: #9B2C2C;
  }

  .table-success th {
    background-color: #276749;
  }

  /* Etiquetas / Badges */
  .badge-danger {
    background-color: #FED7D7;
    color: #9B2C2C;
    padding: 2px 6px;
    border-radius: 3px;
    font-size: 8pt;
    font-weight: bold;
    display: inline-block;
  }

  .badge-success {
    background-color: #C6F6D5;
    color: #22543D;
    padding: 2px 6px;
    border-radius: 3px;
    font-size: 8pt;
    font-weight: bold;
    display: inline-block;
  }

  /* Listas */
  ul, ol {
    margin: 0 0 12px 0;
    padding-left: 20px;
  }

  li {
    margin-bottom: 4px;
  }

  .summary-section {
    background-color: #EDF2F7;
    padding: 12px 15px;
    border-radius: 4px;
    margin-top: 20px;
  }

  code {
    font-family: Consolas, Monaco, monospace;
    background-color: #EDF2F7;
    padding: 2px 4px;
    border-radius: 3px;
    font-size: 8.5pt;
    color: #805AD5;
  }
</style>
</head>
<body>

  <div class="header-container">
    <h1>Reporte de Práctica: Ensambles en SolidWorks y Corte Láser</h1>
    <div class="subtitle">Laboratorio de Diseño y Manufactura Digital</div>
  </div>

  <table class="meta-table">
    <tr>
      <td><strong>Asignatura:</strong> Diseño Asistido por Computadora</td>
      <td><strong>Tema:</strong> Tolerancias, Kerf y Dibujo Técnico</td>
    </tr>
    <tr>
      <td><strong>Software:</strong> SolidWorks</td>
      <td><strong>Proceso:</strong> Corte y Grabado Láser CO₂</td>
    </tr>
  </table>

  <h2>1. Objetivos de la Práctica</h2>
  <ul>
    <li>Comprender los conceptos de <strong>tolerancia dimensional</strong> y ancho de sangría (<strong>kerf</strong>) aplicados a la manufactura por corte láser.</li>
    <li>Identificar los materiales autorizados para su uso en las máquinas láser de la escuela y reconocer los materiales prohibidos junto con sus riesgos de seguridad y daños al equipo.</li>
    <li>Utilizar herramientas avanzadas de modelado en SolidWorks (simetrías y matrices) para agilizar el diseño de piezas vectoriales.</li>
    <li>Efectuar ensambles tridimensionales para verificar el correcto ajuste mecánico de las piezas previo al corte.</li>
    <li>Generar la documentación técnica mediante el módulo de dibujo 2D para la posterior exportación de los perfiles de corte.</li>
  </ul>

  <h2>2. Fundamentos Técnicos: Tolerancia y Kerf</h2>
  <p>En el proceso de corte láser, la herramienta de corte es un haz de luz focalizado que vaporiza o derrite el material. Debido a este fenómeno, el láser remueve una pequeña franja de material a lo largo de la trayectoria de corte.</p>

  <div class="callout-box">
    <p><strong>El Kerf (Ancho de Sangría):</strong> Es el grosor del material que el láser "se come" o destruye al cortar. Para asegurar un ajuste adecuado en ensambles (como uniones macho-hembra o encastres a presión), las dimensiones del croquis en SolidWorks deben compensar el valor del kerf (añadiendo o restando la mitad del kerf según se trate de contornos exteriores o cavidades interiores).</p>
  </div>

  <p>La <strong>tolerancia</strong> representa el margen permitido de variación dimensional para que dos piezas embonen correctamente sin juego excesivo ni interferencias imprevistas.</p>

  <h2>3. Clasificación de Materiales para Corte Láser</h2>

  <h3>3.1. Materiales Permitidos en la Escuela</h3>
  <table class="data-table table-success">
    <thead>
      <tr>
        <th>Material</th>
        <th>Estado</th>
        <th>Observaciones / Usos</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Papel y Cartón (Paper / Cardboard)</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Prototipado rápido y maquetación.</td>
      </tr>
      <tr>
        <td>Foaming (Goma EVA)</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Piezas flexibles y empaques.</td>
      </tr>
      <tr>
        <td>Fieltro (Felt)</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Aplicaciones textiles y protecciones.</td>
      </tr>
      <tr>
        <td>Telas de algodón y fibras mixtas</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Corte textil limpio.</td>
      </tr>
      <tr>
        <td>Telas sintéticas gruesas</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Sella los bordes al cortar.</td>
      </tr>
      <tr>
        <td>Lycra y telas sintéticas delgadas</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Requiere ajuste fino de potencia.</td>
      </tr>
      <tr>
        <td>Cuero natural y cuero sintético (Leather)</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Genera olor intenso; requiere extracción de aire.</td>
      </tr>
      <tr>
        <td>Caucho / Látex (Rubber)</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Apto para empaques y sellos.</td>
      </tr>
      <tr>
        <td>Corcho (Cork)</td>
        <td><span class="badge-success">PERMITIDO</span></td>
        <td>Corte limpio y preciso.</td>
      </tr>
    </tbody>
  </table>

  <h3>3.2. Materiales Estrictamente Prohibidos y sus Riesgos</h3>
  <table class="data-table table-danger">
    <thead>
      <tr>
        <th>Material Prohibido</th>
        <th>Peligro Principal</th>
        <th>Efectos y Consecuencias</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>PVC / Vinil / Cuerina artificial</strong></td>
        <td>Gas Cloro</td>
        <td><span class="badge-danger">NUNCA CORTAR</span> Emite gas cloro que destruye las ópticas, corroe la estructura metálica de la máquina, arruina los motores y es tóxico.</td>
      </tr>
      <tr>
        <td><strong>Policarbonato / Lexan (> 1mm)</strong></td>
        <td>Mala absorción / Fuego</td>
        <td>Absorbe la luz infrarroja del láser (por ello las ventanas de la máquina son de este material). Se quema, produce humo espeso con hollín y arruina los espejos.</td>
      </tr>
      <tr>
        <td><strong>ABS</strong></td>
        <td>Gas Cianuro / Fusión</td>
        <td>Se derrite en lugar de cortar, se inflama con facilidad y libera <em>cianuro de hidrógeno</em>, altamente peligroso.</td>
      </tr>
      <tr>
        <td><strong>HDPE (Plástico de botellas de leche)</strong></td>
        <td>Incendio y Fusión</td>
        <td>Se derrite, forma plastas viscosas e inflamables en la mesa de trabajo.</td>
      </tr>
      <tr>
        <td><strong>Espuma de Poliestireno (Unicel)</strong></td>
        <td>Combustión Instantánea</td>
        <td><strong>Causa #1 de incendios en cortadoras láser.</strong> Se inflama y quema de forma extremadamente rápida.</td>
      </tr>
      <tr>
        <td><strong>Espuma de Polipropileno</strong></td>
        <td>Fuego y Goteo</td>
        <td>Se derrite, se enciende y genera gotas incandescentes que se petrifican en la rejilla.</td>
      </tr>
      <tr>
        <td><strong>Resina Epóxica (Epoxy)</strong></td>
        <td>Gases Tóxicos / Fumo</td>
        <td>El láser CO₂ no logra cortarlo; produce quemaduras y vapores altamente tóxicos (similares al cianuro).</td>
      </tr>
      <tr>
        <td><strong>Fibra de Vidrio</strong></td>
        <td>Vapores Nocivos</td>
        <td>Combinación de vidrio (solo se graba) y resina epóxica (desprende gases nocivos).</td>
      </tr>
      <tr>
        <td><strong>Fibra de Carbono Recubierta</strong></td>
        <td>Gases Nocivos</td>
        <td>El recubrimiento plástico/resinoso reacciona emitiendo vapores peligrosos.</td>
      </tr>
      <tr>
        <td><strong>Alimentos (Carne, pan, tortillas, etc.)</strong></td>
        <td>Contaminación Cruzada</td>
        <td>Aunque se pueden cortar, la máquina acumula residuos tóxicos de madera y acrílico, contaminando los alimentos.</td>
      </tr>
    </tbody>
  </table>

  <h2>4. Desarrollo del Trabajo en SolidWorks</h2>

  <h3>4.1. Modelado de Piezas y Herramientas de Rapidez</h3>
  <p>Se diseñaron las piezas individuales aplicando herramientas para optimizar el tiempo de bocetado y modelado:</p>
  <ul>
    <li><strong>Simetría de Croquis y Operaciones:</strong> Duplicación automática de geometrías respecto a ejes planos, asegurando consistencia matemática y reduciendo el trabajo manual.</li>
    <li><strong>Matrices Lineales y Circulares:</strong> Generación repetitiva de patrones para dientes de encastre, ranuras de ventilación y conectores.</li>
  </ul>

  <h3>4.2. Ensamble y Verificación de Ajustes</h3>
  <p>Con las piezas modeladas, se creó un archivo de ensamble (<code>.SLDASM</code>) para comprobar el ajuste real antes del corte:</p>
  <ol>
    <li>Inserción de la pieza principal como base fija y alineación de las piezas secundarias mediante relaciones de posición (coincidencia, paralelismo, distancia).</li>
    <li>Verificación del encaje entre pestañas y ranuras, considerando el margen de tolerancia asignado para el kerf.</li>
    <li>Uso de la herramienta de detección de interferencias para evitar solapamientos no deseados en la estructura final.</li>
  </ol>

  <h3>4.3. Conversión a Dibujo 2D para Corte</h3>
  <p>Para transferir el diseño a la cortadora láser:</p>
  <ul>
    <li>Se generó un plano en el módulo de dibujo de SolidWorks (<code>.SLDDRW</code>).</li>
    <li>Se insertaron las vistas 2D perpendiculares a cada cara de las piezas.</li>
    <li>Se aseguró la escala estricta <strong>1:1</strong> para conservar las cotas reales.</li>
    <li>Se exportó el plano a formato vectorial <code>.DXF</code> o <code>.DWG</code>, dejando únicamente las líneas de corte limpias para el controlador del láser.</li>
  </ul>

  <div class="summary-section">
    <h3 style="margin-top:0;">5. Conclusión</h3>
    <p>E
    l diseño de piezas para manufactura por corte láser en SolidWorks requiere contemplar las variables físicas del proceso desde la etapa de croquis. Asignar tolerancias correctas en función del kerf asegura un ensamble físico perfecto sin necesidad de retrabajos. Por otro lado, la identificación responsable de los materiales aptos protege la salud de los alumnos y alarga la vida útil de los equipos del laboratorio.</p>
  </div>

</body>
</html> 