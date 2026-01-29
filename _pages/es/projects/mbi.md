---
layout: splash
title: "Índice de carga farmacológica"
permalink: portfolio/projects/mbi/
lang: es
approach:
  - title: "La Arquitectura: <code>ClinicalConfig</code>"
  - excerpt: "Desarrollé un motor analítico en Python que traduce listas de medicación fragmentadas en un índice de carga farmacológica (MBI). No es solo código; es un diccionario médico digital que mapea dosis máximas y pesos clínicos para predecir la gravedad hemodinámica antes de realizar un ecocardiograma."
results:
  - title: "El Factor Impacto: Precisión Predictiva"
  - excerpt: "El modelo validó que un MBI > 5.25 identifica hipertensión pulmonar crítica con un 85% de precisión. Esta herramienta permite un 'triaje de recepción', priorizando a los pacientes con mayor beneficio de intervención y optimizando el recurso más escaso de la misión: el tiempo de los especialistas."
highlights_title: 
  - title: "Análisis de Datos y Visualización"
  - excerpt: "Del procesamiento de crudos a la validación estadística: el proceso completo de la brigada de cardiología 'Project Health for Leon' 2025."
highlights:
  - url: "/assets/images/mbi_imputation.jpg"
    image_path: "/assets/images/mbi_imputation.jpg"
    alt: "Distribución de Densidad tras Imputación Gaussiana"
    title: "Mitigación de Sesgos: Restauración de la distribución fisiológica real mediante imputación de ruido gaussiano para corregir el sesgo de registros incompletos (MNAR)."
  - url: "/assets/images/mbi_roc.jpg"
    image_path: "/assets/images/mbi_roc.jpg"
    alt: "Curva ROC y Validación de Umbral"
    title: "Poder Predictivo: Curva ROC con AUC de 0.73, validando la eficacia del MBI para detectar complejidad hemodinámica y/o remodelado cardíaco."
  - url: "/assets/images/mbi_roc_rvsp.jpg"
    image_path: "/assets/images/mbi_roc_rvsp.jpg"
    alt: "Correlación MBI vs RVSP"
    title: "Significancia Clínica: Correlación lineal entre el índice de carga farmacológica y la presión sistólica de la arteria pulmonar (RVSP), validando el MBI como sucedáneo hemodinámico."
  - url: "/assets/images/mbi_decomposed.jpg"
    image_path: "/assets/images/mbi_decomposed.jpg"
    alt: "Estratificación de MBI por grupo farmacológico"
    title: "Jerarquía de Contribución: Análisis de la carga farmacológica ponderada por clase, donde los grupos en rojo oscuro representan los mayores pesos clínicos en el cálculo del MBI."
  - url: "/assets/images/mbi_code.png"
    image_path: "/assets/images/mbi_code.png"
    alt: "Fragmento de arquitectura de código para de pesos clínicos"
    title: "Ingeniería de Características: Fragmento de estructura de diccionarios para estandarizar techos terapéuticos y ponderaciones de severidad cardiovascular de forma escalable."
  - url: "/assets/images/mbi_output.jpg"
    image_path: "/assets/images/mbi_output.jpg"
    alt: "Salida de resumen ejecutivo"
    title: "Resumen ejecutivo: Resumen de métricas clave como el MBI para pacientes con válvulas nativas, cantidad de casos complejos y estratificación de los mismos."
---

<style>
.feature-divider { 
    margin-top: 5rem; margin-bottom: 2rem; 
}

.cta {
    margin-top: 5rem !important;
}

.mbi-table {
    margin-left: auto !important;
    margin-right: auto !important;
    border-collapse: collapse !important;
    display: table !important;
}
</style>

<div class="headline">
    <h1>Cuantificando las brechas clínicas: MBI como sucedáneo <br>de remodelado cardíaco</h1>
    <p>Análisis de datos aplicada a la brigada cardiológica 2025 en León, Nicaragua.</p>
</div>

<div class="skills-bar">
    <strong>Tech Stack:</strong> <code>Pandas, NumPy, Statsmodels, Scikit-learn</code>, <code>Matplotlib/Seaborn</code>
</div>

<h2>El corazón del análisis: ¿Qué es el 'Medication Burden Index' (MBI)?</h2>
<p>
  El <strong>MBI</strong> es un índice ponderado que cuantifica la intensidad del tratamiento farmacológico de un paciente. En lugar de solo contar cuántas pastillas toma una persona, el MBI evalúa el "esfuerzo" que el sistema cardiovascular está realizando bajo soporte médico.
</p>

<div class="math-block">
  $$MBI = \sum \left( \text{Peso de Clase} \times \frac{\text{Dosis Total Diaria}}{\text{Dosis Clínica Máxima}} \right)$$
</div>

<p>Para lograr este cálculo, el motor procesa dos variables críticas:</p>

<ul>
  <li><strong>Dosis Total Diaria (DTD):</strong> Es la sumatoria de miligramos que el paciente consume en 24 horas. Por ejemplo, un paciente con Furosemida 40mg cada 12h tiene un $DTD = 80mg$.</li>
  <li><strong>Pesos Clínicos:</strong> El código asigna pesos mayores (e.j. $3.0$) a diuréticos de asa y vasodilatadores pulmonares, y pesos menores ($0.5$) a estatinas o fármacos de mantenimiento.</li>
</ul>

<p>
  Esta arquitectura permite que el MBI actúe como un <strong>sucedáneo de severidad hemodinámica</strong>, capturando la señal de falla cardíaca antes de que el paciente llegue al ecocardiógrafo.
</p>

<h3>Lógica de Ponderación: Pesos clínicos</h3>
<p>
  No todos los fármacos indican la misma gravedad. El código asigna un peso específico basado en la severidad de la condición que tratan, priorizando señales de remodelación cardíaca:
</p>

<div class="table-container">
  <table class="mbi-table" style="width: 65%; border: 1px solid #ddd;">
    <thead>
      <tr style="background-color: #003152; color: white;">
        <th style="padding: 12px; border: 1px solid #ddd;">Peso</th>
        <th style="padding: 12px; border: 1px solid #ddd;">Prioridad</th>
        <th style="padding: 12px; border: 1px solid #ddd;">Clases de Medicación</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>3.0</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Crítico</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Diuréticos de asa, Vasodilatadores pulmonares.</td>
      </tr>
      <tr style="background-color: #f9f9f9;">
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>2.0</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Alta</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Inhibidores RAAS, Beta-bloqueadores, SGLT2.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>1.0</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Moderada</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Anticoagulantes, Calcioantagonistas.</td>
      </tr>
      <tr style="background-color: #f9f9f9;">
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>0.5</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Mantenimiento</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Estatinas, Fármacos metabólicos.</td>
      </tr>
    </tbody>
  </table>
</div>

<h2>El Reto: El "Silencio de los Normales" (Sesgo MNAR)</h2>
<p>En el caos de una brigada de alto volumen, los datos suelen estar incompletos: si una válvula es normal, el cardiólogo no va a perder su tiempo registrándolo. Esto genera un sesgo de <strong>Missing Not At Random (MNAR)</strong> que invalida cualquier modelo estadístico. Mi primer desafío fue implementar una <strong>Imputación Normal Natural</strong> (ruido gaussiano) para restaurar la distribución fisiológica real de la población ($N=152$).</p>

<hr class="feature-divider">

{% include feature_row id="approach" type="center" %}

<div class="grid-container">
  <div class="grid-item">
      <img src="/assets/images/data_management.png" alt="Imagen: Procesamiento de Datos" class="grid-icon">
      <h3>Procesamiento de Datos</h3>
      <p>Ejecuta la normalización de dosis diarias (TDD) y la imputación de ruido gaussiano para restaurar la distribución fisiológica real frente al sesgo de datos faltantes.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/data_architecture.png" alt="Imagen: Arquitectura Clínica " class="grid-icon">
      <h3>Arquitectura Clínica</h3>
      <p>Gobierna la jerarquía de pesos (0.5 a 3.0), priorizando fármacos de alto impacto hemodinámico como diuréticos de asa y vasodilatadores pulmonares.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/statistic.png" alt="Imagen: Validación Estadística " class="grid-icon">
      <h3>Validación Estadística</h3>
      <p>Genera la lógica de triaje basada en curvas ROC, identificando el punto de corte óptimo ($MBI > 4.0$) para predecir complejidad clínica con precisión.</p>
  </div>
</div>

<hr class="feature-divider">

{% include feature_row id="results" type="center" %}

<div class="mbi-main-plot" style="margin: 3rem 0; text-align: center;">
  <img src="/assets/images/mbi_triage.png" alt="Distribución MBI y Zonas de Triaje" style="width: 100%; max-width: 900px; border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
  <p style="font-style: italic; color: #666; margin-top: 1rem; font-size: 0.9rem;">
    Figura 1: Correlación entre el MBI y la severidad hemodinámica. Se aprecian las tres zonas operativas de triaje validadas.
  </p>
</div>

<div class="project-grid">
  <div class="card">
    <h3>La Zona clave</h3>
    <p>Identificación de la <strong>Zona 2 (MBI 4.0 - 5.5)</strong>: pacientes con patología mixta que obtienen el mayor beneficio del recambio valvular.</p>
  </div>
  <div class="card">
    <h3>Poder Predictivo</h3>
    <p>AUC de <strong>0.73/0.82</strong> para detectar compromiso hemodinámico. El MBI actúa como un "Ecocardiograma Químico" preliminar.</p>
  </div>
  <div class="card">
    <h3>Eficiencia Operativa</h3>
    <p>Reducción de la carga en estaciones de diagnóstico al priorizar pacientes en <strong>Agotamiento Farmacológico</strong> (MBI > 5.5).</p>
  </div>
</div>

<h3 style="text-align: center; margin-top: 3rem;">Protocolo de Decisión: Tabla de referencia para triage</h3>
<p style="text-align: center; color: #666;">Validación operativa para el personal de recepción:</p>

<div class="table-container">
  <table class="mbi-table" style="width: 85%; border: 1px solid #ddd;">
    <thead>
      <tr style="background-color: #003152; color: white;">
        <th style="padding: 15px; border: 1px solid #ddd;">Rango MBI</th>
        <th style="padding: 15px; border: 1px solid #ddd;">Zona de Triaje</th>
        <th style="padding: 15px; border: 1px solid #ddd;">Interpretación Clínica</th>
      </tr>
    </thead>
    <tbody>
      <tr style="background-color: #e8f6ee;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">&lt; 2.27</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">Estándar</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;">Cercano al promedio de la cohorte. Probablemente compensado.</td>
      </tr>
      <tr style="background-color: #fcf6db;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;"><strong>4.0 – 5.25</strong></td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;"><strong>Complejo</strong></td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;"><strong>Área óptima de intervención:</strong> Alta probabilidad de complejidad.</td>
      </tr>
      <tr style="background-color: #fceceb;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">5.25 – 5.5</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">Crítico</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;">85% de Precisión para PH Crítica (RVSP &gt; 60 mmHg).</td>
      </tr>
      <tr style="background-color: #fceceb;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">&gt; 5.5</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">¿Paliativo?</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;">Agotamiento farmacológico: Riesgo elevado de intervención futil.</td>
      </tr>
    </tbody>
  </table>
</div>

<div class="pull-quote">
  "El MBI transforma una lista de medicamentos en una <strong>métrica de severidad</strong>, permitiendo que la brigada opere con precisión estadística."
</div>

{% include feature_row id="highlights_title" type="center" %}

{% include gallery id="highlights" %}

<div class="see-more-button">
  <a href="https://github.com/enrodri/phl_2025/blob/main/phl_2025.ipynb" class="btn btn--primary">Ver Cuaderno Jupyter Completo</a>
</div>

<div class="cta">
  <div style="text-align: center;">
    <h3>Arquitectura de datos para decisiones de alto impacto</h3>
    <p>Desde el procesamiento de datos hasta la validación de modelos predictivos, transformo variables complejas en claridad operativa. Si buscas un arquitecto de datos que entienda el valor estratégico de la precisión técnica, hablemos.</p>
    <a href="/es/contact/" class="btn btn--primary">Contáctame</a>
  </div>
</div>