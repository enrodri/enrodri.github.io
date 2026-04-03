---
layout: splash
title: "Relational Database and MySQL-Python integration"
permalink: portfolio/projects/little-lemon-db/
lang: en
# Social previews
description: "Engineering a 3NF relational database and Python-SQL integration for operational management."
header:
  teaser: "/assets/images/database_schema.png"
# This block communicates directly with the SEO plugin
seo:
  type: "article"
  title: "Relational Database and MySQL-Python integration" # Repeat title here
  image: "/assets/images/database_schema.png"
# Sections
approach:
  - title: "The Engineering Workflow"
  - excerpt: "My proposal centered on a three-phase workflow: Forward Engineering a robust schema, Automated Population via Python, and Logic Layering through SQL stored procedures. By implementing <strong>3rd Normal Form (3NF)</strong>, I engineered a relational ecosystem where data redundancy is eliminated."
results:
  - title: "The Execution Factor: From Storage to Strategy"
  - excerpt: "The success of this structure lies in its ability to convert a static database into a dynamic operational asset. By bridging Python automation with SQL logic, I established a system where data is not just stored, but actively managed to ensure 100% transaction integrity"
highlights_title: 
  - title: "Engineering Milestones"
  - excerpt: "A visual walk-through of the database lifecycle: from ERD schema design and Faker ingestion to the final Tableau reporting layer."
highlights:
  - url: "/assets/images/meta_procedure.jpg"
    image_path: "/assets/images/meta_procedure.jpg"
    alt: "Stored procedures"
    title: "Encapsulating complex business logic within the MySQL backend to automate routine management tasks."
  - url: "/assets/images/meta_connection.jpg"
    image_path: "/assets/images/meta_connection.jpg"
    alt: "Execution bridge"
    title: "Establishing a secure link between Python and MySQL using <code>MySQL Connector/Python</code> for programmatic backend management."
  - url: "/assets/images/meta_insertion.jpg"
    image_path: "/assets/images/meta_insertion.jpg"
    alt: "Ingestion engine"
    title: "Automated data population utilizing the Python <code>Faker</code> library to simulate production-ready datasets with probabilistic logic."
  - url: "/assets/images/meta_validation.jpg"
    image_path: "/assets/images/meta_validation.jpg"
    alt: "Integrity guard"
    title: "Demonstrating the database’s self-correcting logic when faced with invalid or conflicting operational inputs."
  - url: "/assets/images/meta_execution.jpg"
    image_path: "/assets/images/meta_execution.jpg"
    alt: "The bridge in Action"
    title: "Executing backend SQL logic through a Jupyter interface, demonstrating the full integration of the engineering stack."
  - url: "/assets/images/meta_dashboard.jpg"
    image_path: "/assets/images/meta_dashboard.jpg"
    alt: "Actionable analytics"
    title: "Converting raw database records into strategic insights, allowing stakeholders to visualize operational performance at a glance."
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
    <h1>From Faker to Tableau: An End-to-End MySQL Engineering Pipeline</h1>
    <p>A case study on engineering a relational ecosystem from synthetic data generation to interactive business intelligence</p>
</div>

<div class="skills-bar">
    <p><strong>Tech Stack:</strong> 3NF Relational Modeling, <code>MySQL</code>, Stored Procedures, <code>MySQL Connector/Python</code>, <code>Tableau</code></p>
</div>

<h2>The Challenge: Building for Scale and Integrity</h2>
<p>In a high-traffic business environment, data fragmentation is the enemy of efficiency. The core problem was the lack of a centralized system to handle simultaneous bookings and menu updates. The goal was to transform disparate requirements into a <strong>single source of truth</strong> that ensures data consistency and prevents performance bottlenecks.</p>

<hr class="feature-divider">

{% include feature_row id="approach" type="center" %}

<div class="grid-container">
  <div class="grid-item">
      <img src="/assets/images/data_schema.png" alt="Icon: Schema Design" class="grid-icon">
      <h3>Schema Design</h3>
      <p>Engineering a <strong>Third Normal Form (3NF)</strong> relational model to eliminate data redundancy.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/data_population.png" alt="Icon: Data Processing" class="grid-icon">
      <h3>Faker Population</h3>
      <p>Moving beyond static entry by utilizing the <strong>Python Faker library</strong> to generate unique datasets, simulating production-ready variance and probabilistic logic.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/data_transaction.png" alt="Icon: Transaction Security" class="grid-icon">
      <h3>Transaction Security</h3>
      <p>Implementation of <strong>Stored Procedures</strong> to automate inventory checks and secure transaction processing against data corruption.</p>
  </div>
</div>

<hr class="feature-divider">

{% include feature_row id="results" type="center" %}

<div class="mbi-main-plot" style="margin: 3rem 0; text-align: center;">
  <img src="/assets/images/database_schema.png" alt="Database schema in 3NF" style="width: 100%; max-width: 750px; border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
  <p style="font-style: italic; color: #666; margin-top: 1rem; font-size: 0.9rem;">
    Figure 1: Database schema that implements 3rd Normal Form (3NF)
  </p>
</div>

<div class="project-grid">
  <div class="card">
    <h3>Operational integrity</h3>
    <p>Successfully deployed a suite of procedures for consistent booking management, reducing manual entry errors and preventing double-booking conflicts through SQL <strong>stored procedures</strong></p>
  </div>
  <div class="card">
    <h3>MySQL-Python bridge</h3>
    <p>Executed workflows via <strong>MySQL Connector/Python</strong>, demonstrating how backend procedures can be called programmatically to manage restaurant functions.</p>
  </div>
  <div class="card">
    <h3>Intelligence translation</h3>
    <p>Transformed normalized relational data into a interactive <strong>Tableau dashboard</strong>, providing a clear view of sales trends and menu popularity.</p>
  </div>
</div>

<div class="pull-quote">
  "A database is more than a container; it is the <strong>structural integrity</strong> that allows data to transition into actionable intelligence."
</div>

{% include feature_row id="highlights_title" type="center" %}

{% include gallery id="highlights" %}

<div class="see-more-button">
  <a href="https://github.com/enrodri/db-capstone-project" class="btn btn--primary">View Full Repository</a>
</div>

<div class="cta">
  <div style="text-align: center;">
    <h3>Let's Build Your Data Foundation</h3>
    <p>Whether it is clinical research or business operations, a project is only as strong as its database. I specialize in building the bridges that keep your data clean, fast, and accessible.</p>
    <a href="contact/" class="btn btn--primary">Get in Touch</a>
  </div>
</div>