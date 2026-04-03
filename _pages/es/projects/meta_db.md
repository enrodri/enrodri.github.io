---
layout: splash
title: "Base de Datos Relacional e integración MySQL-Python"
permalink: portfolio/projects/little-lemon-db/
lang: es
approach:
  - title: "El Flujo de Ingeniería"
  - excerpt: "Mi propuesta se centró en un flujo de trabajo de tres fases: Ingeniería de un esquema robusto, Población Automatizada mediante Python y Capas de Lógica a través de procedimientos almacenados en SQL. Al implementar la <strong>Tercera Forma Normal (3NF)</strong>, diseñé un ecosistema relacional donde se elimina la redundancia de datos."
results:
  - title: "El Factor de Ejecución: Del Almacenamiento a la Estrategia"
  - excerpt: "El éxito de esta estructura reside en su capacidad para convertir una base de datos estática en un activo operacional dinámico. Al conectar la automatización de Python con la lógica de SQL, establecí un sistema donde los datos no solo se almacenan, sino que se gestionan activamente para garantizar un 100% de integridad transaccional."
highlights_title: 
  - title: "Hitos de Ingeniería"
  - excerpt: "Un recorrido visual por el ciclo de vida de la base de datos: desde el diseño del esquema ERD y la ingesta con Faker hasta la capa final de reportes en Tableau."
highlights:
  - url: "/assets/images/meta_procedure.jpg"
    image_path: "/assets/images/meta_procedure.jpg"
    alt: "Procedimientos almacenados"
    title: "Encapsulamiento de lógica de negocio compleja dentro del backend de MySQL para automatizar tareas de gestión rutinarias."
  - url: "/assets/images/meta_connection.jpg"
    image_path: "/assets/images/meta_connection.jpg"
    alt: "Puente de ejecución"
    title: "Establecimiento de un enlace seguro entre Python y MySQL mediante <code>mysql-connector-python</code> para la gestión programática backend."
  - url: "/assets/images/meta_insertion.jpg"
    image_path: "/assets/images/meta_insertion.jpg"
    alt: "Ingesta de datos"
    title: "Uso de la librería <code>Faker</code> de Python y lógica probabilística para simular entornos de producción con datos realistas."
  - url: "/assets/images/meta_validation.jpg"
    image_path: "/assets/images/meta_validation.jpg"
    alt: "Guardián de integridad"
    title: "Demostración de la lógica de autocorrección de la base de datos ante entradas operativas inválidas o conflictivas."
  - url: "/assets/images/meta_execution.jpg"
    image_path: "/assets/images/meta_execution.jpg"
    alt: "El puente en acción"
    title: "Ejecución de lógica SQL de backend a través de una interfaz de Jupyter, demostrando la integración total del stack de ingeniería."
  - url: "/assets/images/meta_dashboard.jpg"
    image_path: "/assets/images/meta_dashboard.jpg"
    alt: "Analítica accionable"
    title: "Conversión de registros de base de datos en crudo en insights estratégicos, permitiendo a los interesados visualizar el rendimiento operativo de un vistazo."
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

.math-block {
    text-align: center;
    font-size: clamp(0.8rem, 4vw, 1.2rem); 
    overflow-x: auto;
    white-space: nowrap;
}
</style>

<div class="headline">
    <h1>De Faker a Tableau: Un Pipeline de Ingeniería MySQL End-to-End</h1>
    <p>Un estudio de caso sobre la ingeniería de un ecosistema relacional, desde la generación de datos sintéticos hasta la inteligencia de negocios interactiva.</p>
</div>

<div class="skills-bar">
    <p><strong>Stack Tecnológico:</strong> MySQL, Modelado Relacional 3NF, Procedimientos Almacenados, MySQL Connector/Python, Tableau</p>
</div>

<h2>El Desafío: Construir para la Escala y la Integridad</h2>
<p>En un entorno empresarial de alto tráfico, la fragmentación de datos es el enemigo de la eficiencia. El problema central era la falta de un sistema centralizado para gestionar reservas simultáneas y actualizaciones de menú. El objetivo fue transformar requisitos operativos dispersos en una <strong>fuente única de verdad</strong> que garantice la consistencia de los datos y evite los cuellos de botella.</p>

<hr class="feature-divider">

{% include feature_row id="approach" type="center" %}

<div class="grid-container">
  <div class="grid-item">
      <img src="/assets/images/data_schema.png" alt="Icono: Diseño de Esquema" class="grid-icon">
      <h3>Esquema de diseño</h3>
      <p>Ingeniería de un modelo relacional de <strong>Tercera Forma Normal (3NF)</strong> para eliminar la redundancia de datos.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/data_population.png" alt="Icono: Procesamiento de Datos" class="grid-icon">
      <h3>Población con Faker</h3>
      <p>Superando la entrada estática mediante el uso de la <strong>librería Faker de Python</strong> para generar conjuntos de datos únicos, simulando variaciones de producción y lógica probabilística.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/data_transaction.png" alt="Icono: Seguridad Transaccional" class="grid-icon">
      <h3>Seguridad Transaccional</h3>
      <p>Implementación de <strong>Procedimientos Almacenados</strong> para automatizar verificaciones de inventario y asegurar el procesamiento de transacciones contra la corrupción de datos.</p>
  </div>
</div>

<hr class="feature-divider">

{% include feature_row id="results" type="center" %}

<div class="mbi-main-plot" style="margin: 3rem 0; text-align: center;">
  <img src="/assets/images/database_schema.png" alt="Database schema in 3NF" style="width: 100%; max-width: 750px; border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
  <p style="font-style: italic; color: #666; margin-top: 1rem; font-size: 0.9rem;">
    Figura 1: Esquema de base de datos que implementa Tercera Forma Normal (3NF)
  </p>
</div>

<div class="project-grid">
  <div class="card">
    <h3>Integridad Operacional</h3>
    <p>Despliegue exitoso de una suite de procedimientos para la gestión consistente de reservas, reduciendo errores manuales y evitando conflictos de duplicidad mediante <strong>procedimientos almacenados</strong> en SQL.</p>
  </div>
  <div class="card">
    <h3>Puente MySQL-Python</h3>
    <p>Ejecución de flujos de trabajo a través de <strong>MySQL Connector/Python</strong>, demostrando cómo los procedimientos del backend pueden llamarse programáticamente para gestionar funciones del restaurante.</p>
  </div>
  <div class="card">
    <h3>Traducción de Inteligencia</h3>
    <p>Transformación de datos relacionales normalizados en un <strong>dashboard interactivo de Tableau</strong>, proporcionando una visión clara de las tendencias de ventas y popularidad del menú.</p>
  </div>
</div>

<div class="pull-quote">
  "Una base de datos es más que un contenedor; es la <strong>integridad estructural</strong> que permite que los datos transicionen hacia una inteligencia accionable."
</div>

{% include feature_row id="highlights_title" type="center" %}

{% include gallery id="highlights" %}

<div class="see-more-button">
  <a href="https://github.com/enrodri/db-capstone-project" class="btn btn--primary">Ver Repositorio Completo</a>
</div>

<div class="cta">
  <div style="text-align: center;">
    <h3>Construyamos tu Base de Datos</h3>
    <p>Ya sea en investigación clínica u operaciones comerciales, un proyecto es tan sólido como su base de datos. Me especializo en construir los puentes que mantienen tus datos limpios, rápidos y accesibles.</p>
    <a href="contact/" class="btn btn--primary">Ponerse en Contacto</a>
  </div>
</div>