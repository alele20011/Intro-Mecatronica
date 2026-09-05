<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Reporte Semanal: Resumen de la Primera Semana de Universidad</title>
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

  /* Tablas de Resumen */
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
    <h1>Reporte Académico: Resumen de la Primera Semana de Universidad</h1>
    <div class="subtitle">Bitácora de Inicio de Semestre y Proyectos Asignados</div>
  </div>

  <table class="meta-table">
    <tr>
      <td><strong>Período:</strong> Primera Semana Lectiva</td>
      <td><strong>Estatus:</strong> Actividades de Introducción y Prototipado</td>
    </tr>
    <tr>
      <td><strong>Áreas Académicas:</strong> Diseño Asistido por Computadora (CAD) y Servicio Becario</td>
      <td><strong>Herramientas:</strong> SolidWorks, CATIA V5, Escáner 3D Creality</td>
    </tr>
  </table>

  <h2>1. Introducción y Presentación de Cursos</h2>
  <p>Durante los primeros días de la semana universitaria, se llevaron a cabo las sesiones introductorias y la presentación oficial de los <em>syllabi</em> correspondientes a las asignaturas del semestre. Se definieron los criterios de evaluación, reglamentos de laboratorio, fechas de entregas clave y los objetivos generales de aprendizaje.</p>

  <h2>2. Proyecto del Servicio Becario: Cuadrúpedo Unitree Air 2</h2>
  <p>En el marco del servicio becario, se asignó la responsabilidad de trabajar con el robot cuadrúpedo de la universidad (<strong>Unitree Air 2</strong>). El proyecto principal consiste en el diseño y manufactura de protecciones anatómicas (rodilleras) para evitar el desgaste o raspaduras mecánicas en las articulaciones del robot durante sus maniobras.</p>

  <div class="callout-box">
    <p><strong>Flujo de Trabajo Aplicado:</strong></p>
    <ul>
      <li><strong>Escaneo 3D:</strong> Se utilizó un escáner 3D marca <em>Creality</em> para capturar la nube de puntos y la geometría tridimensional precisa de las extremidades del robot.</li>
      <li><strong>Procesamiento Digital:</strong> La información capturada se transfirió a diversos programas especializados de edición para procesar la malla, corregir inconsistencias y preparar el modelo base para el diseño del proyecto.</li>
    </ul>
  </div>

  <h2>3. Fundamentos de CAD: SolidWorks (Clase con Prof. Oliver)</h2>
  <p>En la asignatura impartida por el profesor Oliver, se inició la revisión técnica de las bases de diseño paramétrico utilizando <strong>SolidWorks</strong>:</p>
  <ul>
    <li><strong>Definición de Cotas:</strong> Uso de acotado para establecer las dimensiones exactas y restringir la geometría en el croquis.</li>
    <li><strong>Operación de Extrusión:</strong> Generación de volúmenes tridimensionales a partir de perfiles 2D mediante la función de extrusión.</li>
    <li><strong>Comandos y Acciones Básicas:</strong> Reconocimiento de los comandos esenciales del entorno de trabajo, selección de planos de referencia y comprensión de las acciones dentro del árbol de operaciones.</li>
  </ul>

  <h2>4. Fundamentos de CAD: Dibujo por Computadora en CATIA</h2>
  <p>De forma paralela, en la clase de Dibujo por Computadora se introdujo el software <strong>CATIA</strong>, revisando los conceptos fundamentales para el desarrollo de geometrías vectoriales:</p>
  <table class="data-table">
    <thead>
      <tr>
        <th style="width: 30%;">Concepto</th>
        <th style="width: 70%;">Aplicación y Definición</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><strong>Constraints (Restricciones)</strong></td>
        <td>Aplicación de relaciones geométricas y de posición (coincidencia, paralelismo, tangencia) para fijar el comportamiento de las entidades en el plano.</td>
      </tr>
      <tr>
        <td><strong>Cotas Dimensionales</strong></td>
        <td>Asignación de magnitudes numéricas (diámetros, radios, distancias) para parametrizar las piezas.</td>
      </tr>
      <tr>
        <td><strong>Entorno Sketcher</strong></td>
        <td>Manejo del plano de croquizado base para la construcción limpia de elementos mecánicos.</td>
      </tr>
    </tbody>
  </table>

  <div class="summary-section">
    <h3 style="margin-top:0;">5. Conclusión de la Semana</h3>
    <p>La primera semana de universidad combinó la integración teórica de las asignaturas con la práctica técnica inmediata. El proyecto del servicio becario establece un caso de aplicación real mediante digitalización 3D, mientras que las clases de SolidWorks y CATIA aportan los fundamentos de modelado paramétrico indispensables para la ingeniería de diseño.</p>
  </div>

</body>
</html>