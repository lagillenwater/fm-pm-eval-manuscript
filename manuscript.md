---
title: Evaluation of Foundation Model Generalization to Personalized Medicine
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
  <meta name="dc.title" content="Evaluation of Foundation Model Generalization to Personalized Medicine" />
  <meta name="citation_title" content="Evaluation of Foundation Model Generalization to Personalized Medicine" />
  <meta property="og:title" content="Evaluation of Foundation Model Generalization to Personalized Medicine" />
  <meta property="twitter:title" content="Evaluation of Foundation Model Generalization to Personalized Medicine" />
  <meta name="dc.date" content="2026-06-19" />
  <meta name="citation_publication_date" content="2026-06-19" />
  <meta property="article:published_time" content="2026-06-19" />
  <meta name="dc.modified" content="2026-06-19T20:44:50+00:00" />
  <meta property="article:modified_time" content="2026-06-19T20:44:50+00:00" />
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
  <link rel="alternate" type="text/html" href="https://lagillenwater.github.io/fm-pm-eval-manuscript/v/50c4dabd865f679b03095b8530b4f3fe4ec8c1cc/" />
  <meta name="manubot_html_url_versioned" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/v/50c4dabd865f679b03095b8530b4f3fe4ec8c1cc/" />
  <meta name="manubot_pdf_url_versioned" content="https://lagillenwater.github.io/fm-pm-eval-manuscript/v/50c4dabd865f679b03095b8530b4f3fe4ec8c1cc/manuscript.pdf" />
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
([permalink](https://lagillenwater.github.io/fm-pm-eval-manuscript/v/50c4dabd865f679b03095b8530b4f3fe4ec8c1cc/))
was automatically generated
from [lagillenwater/fm-pm-eval-manuscript@50c4dab](https://github.com/lagillenwater/fm-pm-eval-manuscript/tree/50c4dabd865f679b03095b8530b4f3fe4ec8c1cc)
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
The most recent iteration of AI models (‘foundation’ and ‘world’ models) is exciting, and the field is constantly putting out newer, larger models. But the models do not generalize to out of distribution tests and do not outperform more simple models across tasks. For example, Steiner et al. [@doi:10.1145/3701551.3708811] and Ahlmann-Eltze et al. [@doi:10.1038/s41592-025-02772-6] both reported that linear baselines outperformed single-cell foundation models [@doi:10.1038/s41592-024-02201-0; @doi:10.1038/s41586-023-06139-9; @doi:10.1038/s41592-024-02305-7; @doi:10.1038/s41587-023-01905-6; @doi:10.1038/s42256-022-00534-z] on downstream tasks using data the models had not yet seen. The Virtual Cell Challence in 2025 found similar results on a crowd sourced model evaluation for prediction in an unseen stem cell context [@url:https://arcinstitute.org/news/virtual-cell-challenge-2025-wrap-up]. Translation to personalized medicine is an even more difficult goal. The prediction sets are out of distribution of the training data (i.e., transcriptional profiles from observational samples or interventions on immortalized cell lines.) Therefore,generalization is the bar these models must meet to impact personalized medicine. 

This proposal creates the evaluation framework for generalization to personalized medicine. We are recruiting collaborators to contribute more tasks to test out of distribution generalization. The collective would create the biomedical AI model “acid test” [@url:https://en.wikipedia.org/wiki/Acid2] for precision medicine, encouraging models to demonstrate their performance on the prospective releases of test data tranches. We will pair the continual evaluation results from the [companion repository](https://github.com/greenelab/fm-pm-evaluator) with the collaborative creation of a benchmarking manuscript. 


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


This manuscript is a template (aka "rootstock") for [Manubot](https://manubot.org/ "Manubot"), a tool for writing scholarly manuscripts.
Use this template as a starting point for your manuscript.

The rest of this document is a full list of formatting elements/features supported by Manubot.
Compare the input (`.md` files in the `/content` directory) to the output you see below.

## Basic formatting

**Bold** __text__

[Semi-bold text]{.semibold}

[Centered text]{.center}

[Right-aligned text]{.right}

*Italic* _text_

Combined *italics and __bold__*

~~Strikethrough~~

1. Ordered list item
2. Ordered list item
    a. Sub-item
    b. Sub-item
        i. Sub-sub-item
3. Ordered list item
    a. Sub-item

- List item
- List item
- List item

subscript: H~2~O is a liquid

superscript: 2^10^ is 1024.

[unicode superscripts](https://www.google.com/search?q=superscript+generator)⁰¹²³⁴⁵⁶⁷⁸⁹

[unicode subscripts](https://www.google.com/search?q=superscript+generator)₀₁₂₃₄₅₆₇₈₉

A long paragraph of text.
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

Putting each sentence on its own line has numerous benefits with regard to [editing](https://asciidoctor.org/docs/asciidoc-recommended-practices/#one-sentence-per-line) and [version control](https://rhodesmill.org/brandon/2012/one-sentence-per-line/).

Line break without starting a new paragraph by putting  
two spaces at end of line.

## Document organization

Document section headings:

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

### A heading centered on its own printed page{.center .page_center}

<!-- an arbitrary comment. visible in input, but not visible in output. -->

Horizontal rule:

---

`Heading 1`'s are recommended to be reserved for the title of the manuscript.

`Heading 2`'s are recommended for broad sections such as *Abstract*, *Methods*, *Conclusion*, etc.

`Heading 3`'s and `Heading 4`'s are recommended for sub-sections.

## Links

Bare URL link: <https://manubot.org>

[Long link with lots of words and stuff and junk and bleep and blah and stuff and other stuff and more stuff yeah](https://manubot.org)

[Link with text](https://manubot.org)

[Link with hover text](https://manubot.org "Manubot Homepage")

[Link by reference][manubot homepage]

[Manubot Homepage]: https://manubot.org

## Citations

Citation by DOI [@doi:10.7554/eLife.32822].

Citation by PubMed Central ID [@pmc:PMC6103790].

Citation by PubMed ID [@pubmed:30718888].

Citation by Wikidata ID [@wikidata:Q56458321].

Citation by ISBN [@isbn:9780262517638].

Citation by URL [@{https://greenelab.github.io/meta-review/}].

Citation by alias [@deep-review].

Multiple citations can be put inside the same set of brackets [@doi:10.7554/eLife.32822; @deep-review; @isbn:9780262517638].
Manubot plugins provide easier, more convenient visualization of and navigation between citations [@doi:10.1371/journal.pcbi.1007128; @pubmed:30718888; @pmc:PMC6103790; @deep-review].

Citation tags (i.e. aliases) can be defined in their own paragraphs using Markdown's reference link syntax:

[@deep-review]: doi:10.1098/rsif.2017.0387

## Referencing figures, tables, equations

Figure @fig:square-image

Figure @fig:wide-image

Figure @fig:tall-image

Figure @fig:vector-image

Table @tbl:bowling-scores

Equation @eq:regular-equation

Equation @eq:long-equation

## Quotes and code

> Quoted text

> Quoted block of text
>
> Two roads diverged in a wood, and I—  
> I took the one less traveled by,  
> And that has made all the difference.

Code `in the middle` of normal text, aka `inline code`.

Code block with Python syntax highlighting:

```python
from manubot.cite.doi import expand_short_doi

def test_expand_short_doi():
    doi = expand_short_doi("10/c3bp")
    # a string too long to fit within page:
    assert doi == "10.25313/2524-2695-2018-3-vliyanie-enhansera-copia-i-insulyatora-gypsy-na-sintez-ernk-modifikatsii-hromatina-i-svyazyvanie-insulyatornyh-belkov-vtransfetsirovannyh-geneticheskih-konstruktsiyah"
```

Code block with no syntax highlighting:

```
Exporting HTML manuscript
Exporting DOCX manuscript
Exporting PDF manuscript
```

## Figures

![
**A square image at actual size and with a bottom caption.**
Loaded from the latest version of image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/square.png "Square image"){#fig:square-image}

![
**An image too wide to fit within page at full size.**
Loaded from a specific (hashed) version of the image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/wide.png "Wide image"){#fig:wide-image}

![
**A tall image with a specified height.**
Loaded from a specific (hashed) version of the image on GitHub.
](https://github.com/manubot/resources/raw/15493970f8882fce22bef829619d3fb37a613ba5/test/tall.png "Tall image"){#fig:tall-image height=3in}

![
**A vector `.svg` image loaded from GitHub.**
The parameter `sanitize=true` is necessary to properly load SVGs hosted via GitHub URLs.
White background specified to serve as a backdrop for transparent sections of the image.
Note that if you want to export to Word (`.docx`), you need to download the image and reference it locally (e.g. `content/images/vector.svg`) instead of using a URL.
](https://raw.githubusercontent.com/manubot/resources/main/test/vector.svg?sanitize=true "Vector image"){#fig:vector-image height=2.5in .white}

## Tables

| *Bowling Scores* | Jane          | John          | Alice         | Bob           |
|:-----------------|:-------------:|:-------------:|:-------------:|:-------------:|
| Game 1 | 150 | 187 | 210 | 105 |
| Game 2 |  98 | 202 | 197 | 102 |
| Game 3 | 123 | 180 | 238 | 134 |

Table: A table with a top caption and specified relative column widths.
{#tbl:bowling-scores}

|         | Digits 1-33                        | Digits 34-66                      | Digits 67-99                      | Ref.                                                        |
|:--------|:-----------------------------------|:----------------------------------|:----------------------------------|:------------------------------------------------------------|
| pi      | 3.14159265358979323846264338327950 | 288419716939937510582097494459230 | 781640628620899862803482534211706 | [`piday.org`](https://www.piday.org/million/)               |
| e       | 2.71828182845904523536028747135266 | 249775724709369995957496696762772 | 407663035354759457138217852516642 | [`nasa.gov`](https://apod.nasa.gov/htmltest/gifcity/e.2mil) |

Table: A table too wide to fit within page.
{#tbl:constant-digits}

|          | **Colors** <!-- $colspan="2" --> |                      |
|:--------:|:--------------------------------:|:--------------------:|
| **Size** | **Text Color**                   | **Background Color** |
| big      | blue                             | orange               |
| small    | black                            | white                |

Table: A table with merged cells using the `attributes` plugin.
{#tbl: merged-cells}

## Equations

A LaTeX equation:

$$\int_0^\infty e^{-x^2} dx=\frac{\sqrt{\pi}}{2}$$ {#eq:regular-equation}

An equation too long to fit within page:

$$x = a + b + c + d + e + f + g + h + i + j + k + l + m + n + o + p + q + r + s + t + u + v + w + x + y + z + 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9$$ {#eq:long-equation}

## Special

<i class="fas fa-exclamation-triangle"></i> [WARNING]{.semibold} _The following features are only supported and intended for `.html` and `.pdf` exports._
_Journals are not likely to support them, and they may not display correctly when converted to other formats such as `.docx`._

[Link styled as a button](https://manubot.org "Manubot Homepage"){.button}

Adding arbitrary HTML attributes to an element using Pandoc's attribute syntax:

::: {#some_id_1 .some_class style="background: #ad1457; color: white; margin-left: 40px;" title="a paragraph of text" data-color="white" disabled="true"}
Manubot Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot.
Manubot Manubot.
Manubot.
:::

Adding arbitrary HTML attributes to an element with the Manubot `attributes` plugin (more flexible than Pandoc's method in terms of which elements you can add attributes to):

Manubot Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot Manubot.
Manubot Manubot Manubot.
Manubot Manubot.
Manubot.
<!-- $id="element_id" class="some_class" $style="color: #ad1457; margin-left: 40px;" $disabled="true" $title="a paragraph of text" $data-color="red" -->

Available background colors for text, images, code, banners, etc:  

`white`{.white}
`lightgrey`{.lightgrey}
`grey`{.grey}
`darkgrey`{.darkgrey}
`black`{.black}
`lightred`{.lightred}
`lightyellow`{.lightyellow}
`lightgreen`{.lightgreen}
`lightblue`{.lightblue}
`lightpurple`{.lightpurple}
`red`{.red}
`orange`{.orange}
`yellow`{.yellow}
`green`{.green}
`blue`{.blue}
`purple`{.purple}

Using the [Font Awesome](https://fontawesome.com/) icon set:

<!-- include the Font Awesome library, per: https://fontawesome.com/start -->
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.2/css/all.css">

<i class="fas fa-check"></i> <i class="fas fa-question"></i> <i class="fas fa-star"></i> <i class="fas fa-bell"></i> <i class="fas fa-times-circle"></i> <i class="fas fa-ellipsis-h"></i>

[
<i class="fas fa-scroll fa-lg"></i> **Light Grey Banner**<br>
useful for *general information* - [manubot.org](https://manubot.org/)
]{.banner .lightgrey}

[
<i class="fas fa-info-circle fa-lg"></i> **Blue Banner**<br>
useful for *important information* - [manubot.org](https://manubot.org/)
]{.banner .lightblue}

[
<i class="fas fa-ban fa-lg"></i> **Light Red Banner**<br>
useful for *warnings* - [manubot.org](https://manubot.org/)
]{.banner .lightred}

