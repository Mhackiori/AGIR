<div id="top"></div>
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/Mhackiori/AGIR">
    <img src="Figures/Logo.png" alt="Logo" width="150" height="150">
  </a>

  <h1 align="center">AGIR</h1>

  <p align="center">
    Automating Cyber Threat Intelligence Reporting with Natural Language Generation
    <br />
    <a href=""><strong>Paper in progress »</strong></a>
    <br />
    <br />
    <a href="https://github.com/FilippoPerrina">Filippo Perrina</a>
    ·
    <a href="https://www.math.unipd.it/~fmarchio/">Francesco Marchiori</a>
    ·
    <a href="https://www.math.unipd.it/~conti/">Mauro Conti</a>
    ·
    <a href="https://www.linkedin.com/in/ninoverde/">Nino Vincenzo Verde</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary><strong>Table of Contents</strong></summary>
  <ol>
    <li>
      <a href="#abstract">Abstract</a>
    </li>
    <li>
      <a href="#citation">Citation</a>
    </li>
    <li>
      <a href="#evaluation">Evaluation</a>
      <ul>
        <li><a href="#survey">Survey</a></li>
        <li><a href="#results">Report Type Results</a></li>
      </ul>
    </li>
  </ol>
</details>


<div id="abstract"></div>

## 🧩 Abstract

>Cyber Threat Intelligence (CTI) reporting is pivotal in contemporary risk management strategies. As the volume of CTI reports continues to surge, the demand for automated tools to streamline report generation becomes increasingly apparent. While Natural Language Processing techniques have shown potential in handling text data, they often struggle to address the complexity of diverse data sources and their intricate interrelationships. Moreover, established paradigms like STIX have emerged as de facto standards within the CTI community, emphasizing the formal categorization of entities and relations to facilitate consistent data sharing. In this paper, we introduce **AGIR** (Automatic Generation of Intelligence Reports), a transformative Natural Language Generation tool specifically designed to address the pressing challenges in the realm of CTI reporting. AGIR's primary objective is to empower security analysts by automating the labor-intensive task of generating comprehensive intelligence reports from formal representations of entity graphs. AGIR utilizes a two-stage pipeline by combining the advantages of template-based approaches and the capabilities of Large Language Models such as ChatGPT. We evaluate AGIR's report generation capabilities both quantitatively and qualitatively. The generated reports accurately convey information expressed through formal language, achieving a high recall value (0.99) without introducing hallucination. Furthermore, we compared the fluency and utility of the reports with state-of-the-art approaches, showing how AGIR achieves higher scores in terms of Syntactic Log-Odds Ratio (SLOR) and through questionnaires. By using our tool, we estimate that the report writing time is reduced by more than 40%, therefore streamlining the CTI production of any organization and contributing to the automation of several CTI tasks.

<p align="right"><a href="#top">(back to top)</a></p>
<div id="citation"></div>

## 🗣️ Citation

Please, cite this work when referring to AGIR.

```
@article{citation_in_progress,
  title={,
  author={,
  journal={,
  year={

```

<p align="right"><a href="#top">(back to top)</a></p>
<div id="evaluation"></div>

## 📊 Evaluation

We provide several samples of the generated reports that have been used for the evaluation and the survey. They can be found in the [`Reports`](https://github.com/Mhackiori/AGIR/tree/main/Reports) folder.

<div id="survey"></div>

### ❓ Survey

The questionnaires given to the analysts are structured as follows. First, to establish a baseline to evaluate AGIR's utility, we ask each expert how much time, on average, it takes for them to write a full report. Afterward, for each of the four supported report types, we do the following.

1. We describe the aim of the report type and the focus of their entities and relationships. We also provide several use cases to further contextualize the usage of those particular reports.
2. We provide a graphical overview of the JSON input from which the reports have been generated. Some examples of those STIX graphs are shown in the Figures below.
3. We provide three examples of generated reports. Those three samples are the report generated by Narrator, the report generated by first step AGIR, and the report generated by final step AGIR. To avoid biases, the samples are unmarked and randomized so that the analysts do not know which report has been generated by our system.
4. We ask for an evaluation of each report's accuracy, described as the presence of true intelligence derivable from the input.
5. We ask for an evaluation of each report's fluency, described as the quality of the text, its clarity, ease of reading, and how close it is to a human-generated report.
6. We ask for an evaluation of each report's utility, described as how long the analyst would take to write a full report starting from the presented one.

![Overview Subject Input Example](/Reports/Input_Example/Overview_Subject_Input_Example.png "Overview Subject Input Example")
*Fig. 1. JSON input example for Overview and Subject reports. When dealing with the Subject report, we focus on the “Winnti Group” entity.*
![Timeline Input Example](/Reports/Input_Example/Timeline_Input_Example.png "Timeline Input Example")
*Fig. 2. JSON input example for Timeline reports.*
![Vulnerability Input Example](/Reports/Input_Example/Vulnerability_Input_Example.png "Vulnerability Input Example")
*Fig. 3. JSON input example for Vulnerability reports.*

<div id="results"></div>

### 📝 Report Type Results

The results of the survey divided into overview report, subject report, timeline report, and vulnerability report are shownn, respectively, in Table 1, Table 2, Table 3, and Table 4.

| **Model** | **Fluency** | **Correctness** | **Utility** |
|---|---|---|---|
| Narrator | 2.92 | 2.77 | 109.2 min |
| First Step AGIR | 3.85 | 3.46 | 86.9 min |
| Final AGIR | 4.08 | 4.23 | 78.9 min |

*Table 1. Questionnaire results for the overview reports.*


| **Model** | **Fluency** | **Correctness** | **Utility** |
|---|---|---|---|
| Narrator | 2.85 | 2.92 | 91.2 min |
| First Step AGIR | 3.92 | 3.54 | 68.1 min |
| Final AGIR | 4.00 | 4.15 | 72.3 min |

*Table 2. Questionnaire results for the subject reports.*


| **Model** | **Fluency** | **Correctness** | **Utility** |
|---|---|---|---|
| Narrator | 3.38 | 3.15 | 111.5 min |
| First Step AGIR | 3.46 | 3.38 | 114.6 min |
| Final AGIR | 3.61 | 3.92 | 104.6 min |

*Table 3. Questionnaire results for the timeline reports.*


| **Model** | **Fluency** | **Correctness** | **Utility** |
|---|---|---|---|
| Narrator | 2.84 | 3.07 | 78.1 min |
| First Step AGIR | 3.84 | 3.53 | 48.8 min |
| Final AGIR | 3.92 | 4.23 | 41.5 min |

*Table 4. Questionnaire results for the vulnerability reports.*

<p align="right"><a href="#top">(back to top)</a></p>