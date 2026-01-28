---
layout: splash
title: "Medication Burden Index (MBI)"
permalink: /en/portfolio/projects/mbi/
lang: en
approach:
  - title: "The Architecture: <code>ClinicalConfig</code>"
  - excerpt: "I developed an analytical engine in Python that translates fragmented medication lists into a Medication Burden Index (MBI). It’s not just code; it’s a digital medical dictionary mapping maximum doses and clinical weights to predict hemodynamic severity before an echocardiogram is even performed."
results:
  - title: "The Impact Factor: Predictive Precision"
  - excerpt: "The model validated that an MBI > 5.25 identifies critical pulmonary hypertension with 85% accuracy. This tool enables 'intake triage,' prioritizing patients who would benefit most from intervention and optimizing the mission's scarcest resource: the specialists' time."
highlights_title: 
  - title: "Data Analysis and Visualization"
  - excerpt: "From raw data processing to statistical validation: the end-to-end workflow for the 2025 'Project Health for Leon' cardiology mission."
highlights:
  - url: "/assets/images/mbi_imputation.jpg"
    image_path: "/assets/images/mbi_imputation.jpg"
    alt: "Density Distribution after Gaussian Imputation"
    title: "Bias Mitigation: Restoring the real physiological distribution through Gaussian noise imputation to correct missing data bias (MNAR)."
  - url: "/assets/images/mbi_roc.jpg"
    image_path: "/assets/images/mbi_roc.jpg"
    alt: "ROC Curve and Threshold Validation"
    title: "Predictive Power: ROC curve with an AUC of 0.73, validating the MBI's efficacy in detecting hemodynamic complexity and cardiac remodeling."
  - url: "/assets/images/mbi_roc_rvsp.jpg"
    image_path: "/assets/images/mbi_roc_rvsp.jpg"
    alt: "MBI vs RVSP Correlation"
    title: "Clinical Significance: Linear correlation between the medication burden index and right ventricular systolic pressure (RVSP), validating MBI as a hemodynamic surrogate."
  - url: "/assets/images/mbi_decomposed.jpg"
    image_path: "/assets/images/mbi_decomposed.jpg"
    alt: "MBI Stratification by Drug Group"
    title: "Contribution Hierarchy: Analysis of weighted drug burden by class, where dark red groups represent the highest clinical weights in the MBI calculation."
  - url: "/assets/images/mbi_code.png"
    image_path: "/assets/images/mbi_code.png"
    alt: "Code architecture for clinical weights"
    title: "Feature Engineering: Snippet of dictionary structures used to standardize therapeutic ceilings and cardiovascular severity weighting in a scalable way."
  - url: "/assets/images/mbi_output.jpg"
    image_path: "/assets/images/mbi_output.jpg"
    alt: "Executive Summary Output"
    title: "Executive Summary: Key metrics overview including MBI for native valve patients, complex case counts, and risk stratification."
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
    <h1>Quantifying Clinical Gaps: MBI as a Surrogate for Cardiac Remodeling</h1>
    <p>Data science applied to the 2025 Cardiology Mission in León, Nicaragua.</p>
</div>

<div class="skills-bar">
    <strong>Tech Stack:</strong> <code>Pandas, NumPy, Statsmodels, Scikit-learn</code>, <code>Matplotlib/Seaborn</code>
</div>

<h2>The Core of the Analysis: What is the 'Medication Burden Index' (MBI)?</h2>
<p>
  The <strong>MBI</strong> is a weighted index that quantifies the intensity of a patient's pharmacological treatment. Rather than simply counting pills, the MBI evaluates the "effort" the cardiovascular system is making under medical support.
</p>

<div class="math-block">
  $$MBI = \sum \left( \text{Class Weight} \times \frac{\text{Total Daily Dose}}{\text{Maximum Clinical Dose}} \right)$$
</div>

<p>To achieve this, the engine processes two critical variables:</p>

<ul>
  <li><strong>Total Daily Dose (TDD):</strong> The total milligrams consumed by the patient in 24 hours. For example, a patient on Furosemide 40mg every 12h has a $TDD = 80mg$.</li>
  <li><strong>Clinical Weights:</strong> The code assigns higher weights (e.g., $3.0$) to loop diuretics and pulmonary vasodilators, and lower weights ($0.5$) to statins or maintenance drugs.</li>
</ul>

<p>
  This architecture allows the MBI to act as a <strong>surrogate for hemodynamic severity</strong>, capturing signs of heart failure well before the patient even reaches the echocardiograph.
</p>

<h3>Weighting Logic: Clinical Weights</h3>
<p>
  The code assigns specific weights based on the severity of the condition being treated, prioritizing signals of cardiac remodeling:
</p>

<div class="table-container">
  <table class="mbi-table" style="width: 65%; border: 1px solid #ddd;">
    <thead>
      <tr style="background-color: #003152; color: white;">
        <th style="padding: 12px; border: 1px solid #ddd;">Weight</th>
        <th style="padding: 12px; border: 1px solid #ddd;">Priority</th>
        <th style="padding: 12px; border: 1px solid #ddd;">Medication Classes</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>3.0</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Critical</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Loop diuretics, Pulmonary vasodilators.</td>
      </tr>
      <tr style="background-color: #f9f9f9;">
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>2.0</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">High</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">RAAS inhibitors, Beta-blockers, SGLT2.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>1.0</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Moderate</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Anticoagulants, Calcium channel blockers.</td>
      </tr>
      <tr style="background-color: #f9f9f9;">
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;"><strong>0.5</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: center;">Maintenance</td>
        <td style="padding: 10px; border: 1px solid #ddd; text-align: left;">Statins, Metabolic drugs.</td>
      </tr>
    </tbody>
  </table>
</div>

<h2>The Challenge: The "Silence of the Normals" (MNAR Bias)</h2>
<p>In high-volume missions, data is often incomplete: if a heart valve is normal, the cardiologist may not record it. This creates a <strong>Missing Not At Random (MNAR)</strong> bias that invalidates standard statistical models. My primary challenge was implementing a <strong>Natural Normal Imputation</strong> (Gaussian noise) to restore the real physiological distribution of the population ($N=152$).</p>

<hr class="feature-divider">

{% include feature_row id="approach" type="center" %}

<div class="grid-container">
  <div class="grid-item">
      <img src="/assets/images/data_management.png" alt="Icon: Data Processing" class="grid-icon">
      <h3>Data Processing</h3>
      <p>Executes Total Daily Dose (TDD) normalization and Gaussian noise imputation to restore real physiological distribution against missing data bias.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/data_architecture.png" alt="Icon: Clinical Architecture" class="grid-icon">
      <h3>Clinical Architecture</h3>
      <p>Governs the weight hierarchy (0.5 to 3.0), prioritizing drugs with high hemodynamic impact like loop diuretics and pulmonary vasodilators.</p>
  </div>
  <div class="grid-item">
      <img src="/assets/images/statistic.png" alt="Icon: Statistical Validation" class="grid-icon">
      <h3>Statistical Validation</h3>
      <p>Generates triage logic based on ROC curves, identifying the optimal cutoff point ($MBI > 4.0$) to predict clinical complexity with precision.</p>
  </div>
</div>

<hr class="feature-divider">

{% include feature_row id="results" type="center" %}

<div class="mbi-main-plot" style="margin: 3rem 0; text-align: center;">
  <img src="/assets/images/mbi_triage.png" alt="MBI Distribution and Triage Zones" style="width: 100%; max-width: 900px; border-radius: 12px; box-shadow: 0 10px 30px rgba(0,0,0,0.1);">
  <p style="font-style: italic; color: #666; margin-top: 1rem; font-size: 0.9rem;">
    Figure 1: Correlation between MBI and hemodynamic severity. The three validated operative triage zones are shown.
  </p>
</div>

<div class="project-grid">
  <div class="card">
    <h3>The Key Zone</h3>
    <p>Identification of <strong>Zone 2 (MBI 4.0 - 5.5)</strong>: patients with mixed pathology who gain the most benefit from valve replacement.</p>
  </div>
  <div class="card">
    <h3>Predictive Power</h3>
    <p>AUC of <strong>0.73/0.82</strong> for detecting hemodynamic compromise. The MBI acts as a preliminary "Chemical Echocardiogram."</p>
  </div>
  <div class="card">
    <h3>Operational Efficiency</h3>
    <p>Relieves pressure on diagnostic stations by prioritizing patients in <strong>Pharmacological Exhaustion</strong> (MBI > 5.5).</p>
  </div>
</div>

<h3 style="text-align: center; margin-top: 3rem;">Decision Protocol: Triage Reference Table</h3>
<p style="text-align: center; color: #666;">Operational validation for intake staff:</p>

<div class="table-container">
  <table class="mbi-table" style="width: 85%; border: 1px solid #ddd;">
    <thead>
      <tr style="background-color: #003152; color: white;">
        <th style="padding: 15px; border: 1px solid #ddd;">MBI Range</th>
        <th style="padding: 15px; border: 1px solid #ddd;">Triage Zone</th>
        <th style="padding: 15px; border: 1px solid #ddd;">Clinical Interpretation</th>
      </tr>
    </thead>
    <tbody>
      <tr style="background-color: #e8f6ee;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">&lt; 2.27</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">Standard</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;">Close to cohort average. Likely compensated.</td>
      </tr>
      <tr style="background-color: #fcf6db;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;"><strong>4.0 – 5.25</strong></td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;"><strong>Complex</strong></td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;"><strong>Optimal intervention area:</strong> High probability of complexity.</td>
      </tr>
      <tr style="background-color: #fceceb;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">5.25 – 5.5</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">Critical</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;">85% Precision for Critical PH (RVSP &gt; 60 mmHg).</td>
      </tr>
      <tr style="background-color: #fceceb;">
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">&gt; 5.5</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: center;">Palliative?</td>
        <td style="padding: 12px; border: 1px solid #ddd; text-align: left;">Pharmacological exhaustion: Elevated risk of futile intervention.</td>
      </tr>
    </tbody>
  </table>
</div>

<div class="pull-quote">
  "The MBI transforms a medication list into a <strong>severity metric</strong>, allowing the mission to operate with statistical precision."
</div>

{% include feature_row id="highlights_title" type="center" %}

{% include gallery id="highlights" %}

<div class="see-more-button">
  <a href="https://github.com/enrodri/phl_2025/blob/main/phl_2025.ipynb" class="btn btn--primary">View Full Jupyter Notebook</a>
</div>

<div class="cta">
  <div style="text-align: center;">
    <h3>Data Architecture for High-Impact Decisions</h3>
    <p>From data processing to predictive model validation, I transform complex variables into operational clarity. If you are looking for a data architect who understands the strategic value of technical precision, let's talk.</p>
    <a href="/en/contact/" class="btn btn--primary">Get in Touch</a>
  </div>
</div>