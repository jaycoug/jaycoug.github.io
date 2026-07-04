---
title: Projects
layout: default
---

Five projects across public health analytics, sports analytics, supply-chain forecasting, cybersecurity analysis, and signal processing. Each deliverable links out to its hosted version.

---

<div class="project-card" markdown="1">

## DSP Explorer Applet
<span class="category-tag">Statistical Modeling</span>

**Question:** How can discrete wavelet transforms and Fourier methods compress and characterize nucleotide sequences — and what do those signal-processing techniques reveal about genetic structure?

**Data:** Named single-gene FASTA sequences from NCBI — insulin, HMGCS2, actin, p53, SYT7, and Mycobacterium tuberculosis; 4 KB–256 KB each; bundled as example data in the repo.

**Data preparation:** Each nucleotide sequence (A/T/C/G) is encoded as a numeric signal using a single-value mapping or the Voss 4-indicator representation before transforms are applied.

**Methods:** Python (numpy, pywt/PyWavelets, scipy.fft, plotly); Haar and Daubechies-4 discrete wavelet transform; DFT and short-time Fourier transform; from-scratch D4 implementation alongside library calls to show the underlying math; Streamlit app with an interactive tool layer and a "Learn" content layer explaining the theory.

**Findings:** Pending — project in progress.

**Limitation:** Current scope is genomic sequences; broader DSP applications (e.g. feature extraction for other project types) are planned as later modules.

**Links:** [GitHub](PLACEHOLDER_DSP_GITHUB) &mdash; [Streamlit App](PLACEHOLDER_DSP_APP)

</div>

---

<div class="project-card" markdown="1">

## HHS Cybersecurity Breaches
<span class="category-tag">Public Health</span>

**Question:** Which types of healthcare data breaches dominated the 2009–2015 reporting window, and which failure modes look most preventable?

**Data:** HHS Office for Civil Rights breach portal — 1,151 incidents reported under HIPAA's Breach Notification Rule (Oct 2009–Feb 2015); sourced via the `crimedatasets` R package; ~300 KB, committed directly to the repo.

**Data preparation:** Dates parsed and standardized; `Individuals.Affected` log-transformed for severity distribution analysis; `Web.Description` free-text field cleaned for keyword extraction.

**Methods:** R + tidyverse (dplyr, ggplot2, stringr, lubridate); breach-type and entity-type distribution analysis; log-scaled severity histogram separating mega-breach outliers from the reporting-floor tail; regex and tidytext keyword extraction on breach narratives to surface causes not captured by structured fields; SAS analogues annotated throughout for public-sector audiences; Quarto HTML report.

**Findings:** Pending — project in progress.

**Limitation:** Data ends Feb 2015; trend findings reflect the 2009–2015 window only and should not be read as current. Breach descriptions are self-reported.

**Links:** [GitHub](PLACEHOLDER_HHS_GITHUB) &mdash; [Report](PLACEHOLDER_HHS_REPORT)

</div>

---

<div class="project-card" markdown="1">

## KYBRFSS Dashboard App
<span class="category-tag">Public Health</span>

**Question:** How do health risk factor prevalence rates vary across Kentucky communities, and which populations carry the highest chronic disease burden?

**Data:** Kentucky BRFSS — statewide population survey covering chronic disease indicators, health behaviors, preventive care access, and demographic variables; state-level supplement to the CDC's national BRFSS program. Produced in collaboration with KDPH.

**Data preparation:** Survey-weighted prevalence estimates computed by indicator, geography, and demographic subgroup; individual-level records are not exposed.

**Methods:** R Shiny; interactive filters for year, county or region, demographic group, and health topic; aggregated outputs only.

**Findings:** Live — see dashboard.

**Limitation:** Population-level survey data; estimates carry sampling error, particularly for small geographic or demographic subgroups. No individual-level data is accessible or displayed.

**Links:** [Dashboard](http://kybrfss.temp.com) *(link pending commissioner approval)*

</div>

---

<div class="project-card" markdown="1">

## USL Championship Analytics
<span class="category-tag">Statistical Modeling</span>

**Question:** Can rolling team performance metrics — xG, goals added, and rest days — reliably forecast USL Championship match outcomes before kickoff?

**Data:** American Soccer Analysis API via the `itscalledsoccer` R package — match results, team and player expected goals, expected passing, and goals added for USL Championship.

**Data preparation:** Raw API responses cleaned into normalized dimension and fact tables (teams, players, matches, team-match stats) stored as Parquet; rolling feature tables built with a lag to prevent future data leakage into pre-match features.

**Methods:** R (itscalledsoccer, tidymodels, targets, arrow, renv); simple Elo-style baseline → multinomial logistic regression → gradient boosting; temporal backtest (train on earlier matchdays, test on later ones); R Shiny app covering league overview, team profiles, player profiles, and match predictions with a methodology page; Tableau Public viz showing one non-duplicative season-level view.

**Findings:** Pending — project in progress.

**Limitation:** ASA provides advanced metrics for a third-tier league; raw counting stats (tackles, discrete fouls, attendance) are not available through this source. Model trained on one season of data; out-of-sample performance should be interpreted cautiously.

**Links:** [GitHub](PLACEHOLDER_USLC_GITHUB) &mdash; [Shiny App](PLACEHOLDER_USLC_SHINY) &mdash; [Tableau Viz](PLACEHOLDER_USLC_TABLEAU)

</div>

---

<div class="project-card" markdown="1">

## Walmart M5 Forecasting
<span class="category-tag">Operations &amp; Forecasting</span>

**Question:** How accurately can a global LightGBM model forecast 28-day unit demand across Walmart's 30,490 item-store time series, and what does forecast error cost in overstock and stockout terms?

**Data:** M5 competition dataset (Kaggle) — 42,840 hierarchical time series of daily Walmart unit sales across California, Texas, and Wisconsin; five CSV files totaling ~440 MB; downloaded separately via Kaggle, not committed to the repo.

**Data preparation:** Wide sales table (30,490 rows × ~1,940 day columns) melted to item-store-day long format; calendar metadata and weekly sell prices joined; converted to Parquet for fast repeated reads.

**Methods:** Python (pandas, pyarrow, lightgbm, scikit-learn, statsforecast, shap, mlflow); naive and seasonal-naive baselines → Ridge regression → LightGBM global model; temporal backtesting against the real 28-day horizon; WRMSSE evaluation; SHAP interpretability; newsvendor inventory simulation comparing baseline vs. ML-assisted vs. quantile-optimal ordering policies; Power BI dashboard presenting results for supply-chain stakeholders.

**Findings:** Pending — project in progress.

**Limitation:** M5 data is a public competition dataset, not live Walmart operational data. Inventory cost figures in the simulation use assumed cost ratios, not real Walmart margins.

**Links:** [GitHub](PLACEHOLDER_WMM5_GITHUB) &mdash; [Power BI Dashboard](PLACEHOLDER_WMM5_POWERBI)

</div>
