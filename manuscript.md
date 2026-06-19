---
title: Prospective Evaluation of Foundation Model Performance in Precision Medicine
keywords:
- markdown
- publishing
- manubot
lang: en-US
date-meta: '2026-06-19'
author-meta:
- Lucas A. Gillenwater
header-includes: |
  <!--
  Manubot generated metadata rendered from header-includes-template.html.
  Suggest improvements at https://github.com/manubot/manubot/blob/main/manubot/process/header-includes-template.html
  -->
  <meta name="dc.format" content="text/html" />
  <meta property="og:type" content="article" />
  <meta name="dc.title" content="Prospective Evaluation of Foundation Model Performance in Precision Medicine" />
  <meta name="citation_title" content="Prospective Evaluation of Foundation Model Performance in Precision Medicine" />
  <meta property="og:title" content="Prospective Evaluation of Foundation Model Performance in Precision Medicine" />
  <meta property="twitter:title" content="Prospective Evaluation of Foundation Model Performance in Precision Medicine" />
  <meta name="dc.date" content="2026-06-19" />
  <meta name="citation_publication_date" content="2026-06-19" />
  <meta property="article:published_time" content="2026-06-19" />
  <meta name="dc.modified" content="2026-06-19T23:38:40+00:00" />
  <meta property="article:modified_time" content="2026-06-19T23:38:40+00:00" />
  <meta name="dc.language" content="en-US" />
  <meta name="citation_language" content="en-US" />
  <meta name="dc.relation.ispartof" content="Manubot" />
  <meta name="dc.publisher" content="Manubot" />
  <meta name="citation_journal_title" content="Manubot" />
  <meta name="citation_technical_report_institution" content="Manubot" />
  <meta name="citation_author" content="Lucas A. Gillenwater" />
  <meta name="citation_author_institution" content="Department of Biomedical Informatics, University of Colorado School of Medicine, Aurora, CO, USA" />
  <meta name="citation_author_orcid" content="0000-0002-6995-0130" />
  <link rel="canonical" href="https://lagillenwater.github.io/fm-pm-eval-manuscript/" />
  <meta property="og:url" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/" />
  <meta property="twitter:url" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/" />
  <meta name="citation_fulltext_html_url" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/" />
  <meta name="citation_pdf_url" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/manuscript.pdf" />
  <link rel="alternate" type="application/pdf" href="https://lagillenwater.github.io/fm-pm-eval-manuscript/manuscript.pdf" />
  <link rel="alternate" type="text/html" href="https://lagillenwater.github.io/fm-pm-eval-manuscript/v/9f0414571e3593976e9b535eea2083edf1ac8c5e/" />
  <meta name="manubot_html_url_versioned" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/v/9f0414571e3593976e9b535eea2083edf1ac8c5e/" />
  <meta name="manubot_pdf_url_versioned" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/v/9f0414571e3593976e9b535eea2083edf1ac8c5e/manuscript.pdf" />
  <meta property="og:type" content="article" />
  <meta property="twitter:card" content="summary_large_image" />
  <link rel="icon" type="image/png" sizes="192x192" href="https://manubot.org/favicon-192x192.png" />
  <link rel="mask-icon" href="https://manubot.org/safari-pinned-tab.svg" color="#ad1457" />
  <meta name="theme-color" content="#ad1457" />
  <!-- end Manubot generated metadata -->
bibliography:
- content/manual-references.json
manubot-output-bibliography: output/references.json
manubot-output-citekeys: output/citations.tsv
manubot-requests-cache-path: ci/cache/requests-cache
manubot-clear-requests-cache: false
...






<small><em>
This manuscript
([permalink](https://lagillenwater.github.io/fm-pm-eval-manuscript/v/9f0414571e3593976e9b535eea2083edf1ac8c5e/))
was automatically generated
from [lagillenwater/fm-pm-eval-manuscript@9f04145](https://github.com/lagillenwater/fm-pm-eval-manuscript/tree/9f0414571e3593976e9b535eea2083edf1ac8c5e)
on June 19, 2026.
</em></small>



## Authors



+ **Lucas A. Gillenwater**
  ^[✉](#correspondence)^<br>
    ![ORCID icon](images/orcid.svg){.inline_icon width=16 height=16}
    [0000-0002-6995-0130](https://orcid.org/0000-0002-6995-0130)
    · ![GitHub icon](images/github.svg){.inline_icon width=16 height=16}
    [lagillenwater](https://github.com/lagillenwater)
    <br>
  <small>
     Department of Biomedical Informatics, University of Colorado School of Medicine, Aurora, CO, USA
     · Funded by R01 HD109765
  </small>


::: {#correspondence}
✉ — Correspondence possible via [GitHub Issues](https://github.com/lagillenwater/fm-pm-eval-manuscript/issues)
or email to
Lucas A. Gillenwater \<lucas.gillenwater@cuanschutz.edu\>.


:::


## Abstract {.page_break_before}




## Introduction
The most recent iteration of AI models (‘foundation’ and ‘world’ models) is exciting, and the field is constantly putting out newer, larger models; however, the models do not generalize to out-of-distribution tests and do not outperform simpler models across tasks. 
For example, Steiner et al. [@doi:10.1145/3701551.3708811] and Ahlmann-Eltze et al. [@doi:10.1038/s41592-025-02772-6] both reported that linear baselines outperformed single-cell foundation models [@doi:10.1038/s41592-024-02201-0; @doi:10.1038/s41586-023-06139-9; @doi:10.1038/s41592-024-02305-7; @doi:10.1038/s41587-023-01905-6; @doi:10.1038/s42256-022-00534-z] on downstream tasks using data the models had not yet seen. 
The Virtual Cell Challenge in 2025 found similar results on a crowd sourced model evaluation for prediction in an unseen stem cell context [@url:https://arcinstitute.org/news/virtual-cell-challenge-2025-wrap-up]. 
Translation to personalized medicine is an even more difficult goal. 
The prediction sets are out-of-distribution of the training data (i.e., transcriptional profiles from observational samples or interventions on immortalized cell lines). 
Therefore, generalization is the bar these models must meet to impact personalized medicine. 

This proposal creates the evaluation framework to prospectively evaluate personalized medicine applications for foundation models, with a particular focus in precision oncology. 
We are recruiting collaborators to contribute across the evaluation framework: new tasks and held-out data tranches, foundation or world models to benchmark, and evaluation harnesses that adapt scoring to new phenotypes and modalities, all to test out-of-distribution generalization. 
Our goal is a precision medicine “acid test” [@url:https://en.wikipedia.org/wiki/Acid2] for foundation models, encouraging model builders and users to demonstrate their performance on the prospective releases of test data tranches. 
We will pair the continual evaluation results from the [companion repository](https://github.com/greenelab/fm-pm-evaluator) with the collaborative creation of a benchmarking manuscript. 


## Data tranches for model evaluation

Each tranche predicts response from pre-treatment expression.

| Tranche | Data source | Input | Output | Prediction expectation | Held-out axis | Leakage |
|:--------|:------------|:------|:-------|:-----------------------|:--------------|:--------|
| **Pre-Tranche**  Retrospective community data | Retrospective PDTO and cell line drug response datasets [@url:https://pnnl-compbio.github.io/coderdata/index.html]. | Pre-treatment expression and the compound identity. | Drug response as one fixed sensitivity metric (dose-response AUC). | Predict across cohorts, drugs, organoids/subtype, and protocols. | Held-out cohort, drug, organoid/subtype, model system. | Need to assess. Transcriptomic models may train on perturbation data from cell lines. |
| **Tranche 1**  CRC drug PDO lines | CRC drug screen: 2 cell lines and 9 patient organoids, 100 compounds, pre-treatment expression per line. | Pre-treatment expression of the line, plus compound identity. | Drug response as one fixed sensitivity metric (dose-response AUC). | Given a line's baseline expression and a compound, predict that line's response. | Held-out compound, organoid, drug. | Retrospective but unpublished, so unseen. Lock splits and predictions before unblinding. |
| **Tranche 2**  ER+ breast, mechanism | Oliphant ER+ patient-derived xenograft organoids in BTOM-ER medium [@doi:10.1186/s13058-024-01798-6], with pre-treatment expression. | Pre-treatment expression, plus the ER-pathway perturbation (fulvestrant dose, or estrogen withdrawal). | Response as CellTiter-Glo viability dose-response, same metric as Tranche 1. | Predict response to the ER-pathway perturbation, and test whether the prediction tracks the ER-dependence mechanism. | Held-out mechanism: an ER-pathway or resistance state not in training. Assess explainability of predictions. | Need to assess. Existing and curated mechanism data. May leak into training. |
| **Tranche 3**  Prospective experiment | A prospective organoid experiment designed and run after predictions are locked. | Pre-treatment expression and compound identity. | Drug response as one fixed sensitivity metric (dose-response AUC). | Predict response on a not-yet-run, sealed experiment. | New patients and new contexts, tested prospectively. | Prospective and sealed. No leakage possible. Predictions registered before the assay. |
| **Future Periodic Tranches** | Prospective experiments and multi-lab datasets across multiple personalized medicine modalities. | Pre-treatment expression and the compound identity. | Perturbation response. The particular phenotype is a moving target requiring a proper evaluation adapter. | Predict response on a not-yet-run, sealed experiment or across cohorts and centers contributed by the community. | New patients and new contexts, tested prospectively, or new centers and new cohorts. Held-out mechanisms. | Prospective and sealed or unpublished. |

Table: Data tranches for evaluating foundation model generalization to personalized medicine.
Each tranche predicts drug response from pre-treatment expression, with a defined held-out axis and a leakage assessment.
{#tbl:data-tranches}

**Data.**
Pre-perturbation state (e.g., transcriptome).
Add other modalities or clinical features in the future.

**Benchmarks.**
Baseline linear and nonlinear statistical models on expression.
Foundation and world models (STACK, STATE, X-Cell).
Reported prediction performance motivates future model inclusion.

**Controls.**
Negative: shuffled response among organoids within each drug.
Positive: injected perturbation-specific effects to recapitulate.

**Scoring.**
Perturbation by substrate interaction. For example, does the model predict that an organoid responds to a drug?

**Community call.**
Find interested collaborators with unpublished data to assess prior to publication through social media platforms like LinkedIn.
Include collaborators in Manubot-style evaluation for interpretation of results.


## References {.page_break_before}

<!-- Explicitly insert bibliography here -->
<div id="refs"></div>

