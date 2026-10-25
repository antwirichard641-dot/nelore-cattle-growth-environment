# Associations Between Cattle Growth, Supplement-Feeder Behaviour, and Environmental Conditions

**An exploratory animal science and agricultural data analysis project using Nelore cattle data from Brazil.**

[![Research](https://img.shields.io/badge/Focus-Animal%20Science%20%7C%20Agricultural%20Data-365f4b)](https://github.com/antwirichard641-dot/nelore-cattle-growth-environment)
[![Analysis](https://img.shields.io/badge/Methods-Statistical%20Analysis-456c9b)](notebooks/)
[![Reproducibility](https://img.shields.io/badge/Workflow-Reproducible%20Research-76568c)](notebooks/)

## Project Overview

Cattle growth reflects the interaction of animal-level characteristics, feeding behaviour, and environmental conditions. Understanding these relationships can help identify questions relevant to livestock productivity, animal management, and data-informed agricultural research.

This project examines associations between recorded average daily gain (ADG), supplement-feeder behaviour, and environmental indicators using a dataset of Nelore cattle from a farm in Brazil.

The workflow combines data auditing, descriptive statistics, fixed-effects modelling, correlation analysis, time-adjusted associations, and research visualisation. The objective is to evaluate the observed relationships while distinguishing statistical evidence from conclusions that the data cannot support.

## Research Questions

1. How does recorded average daily gain vary across the study periods?
2. Are supplement-feeder behaviour measurements associated with recorded cattle growth after accounting for animal and period differences?
3. Which environmental indicators are associated with period-level mean growth, and do these associations persist after accounting for a linear time trend?

## Dataset and Study Design

The analysis uses a cattle dataset obtained from [Mendeley Data](https://doi.org/10.17632/3wdjvxmvsp.7).

| Study characteristic | Description |
|---|---|
| Animal type | Nelore cattle |
| Number of animals | 26 |
| Number of study periods | 15 |
| Prepared observations | 390 |
| Study period | December 2022–October 2023 |
| Primary growth outcome | Recorded average daily gain (ADG) |
| Main explanatory variables | Supplement-feeder behaviour and environmental indicators |

The prepared dataset contains 390 observations and 76 columns. The animal-level analysis uses recorded ADG and feeder-behaviour variables. Environmental associations are assessed at the period level.

**Important design consideration:** Environmental indicators shared by animals within a period do not provide 390 independent environmental observations. The environmental analysis therefore has only 15 independent periods, which limits statistical power and the strength of conclusions.

## Analytical Workflow

The project is organised into three notebooks, progressing from data quality assessment to statistical analysis and final reporting.

1. **Data audit and preparation** — inspect dataset structure, observations, variables, missingness, and analysis readiness.
2. **Growth and association analysis** — summarise growth patterns, estimate feeder-behaviour associations using fixed-effects models, and examine environmental correlations.
3. **Final results and visualisation** — consolidate key results, export tables, and produce figures for research communication.

### Methods

- Descriptive statistics for recorded ADG and period-level growth patterns.
- Fixed-effects models accounting for animal and period differences when examining feeder-behaviour associations.
- Pearson correlations between environmental indicators and period-level mean ADG.
- Time-adjusted correlations calculated after removing linear period trends from both variables.
- Statistical visualisation and export of analysis tables for transparent reporting.

## Key Findings

### 1. Growth patterns

Mean recorded ADG was approximately **0.592 kg/day**. Period-level mean growth varied substantially, ranging from approximately **−0.13 to 1.20 kg/day**.

This variation highlights the importance of examining growth over time rather than relying only on an overall mean.

### 2. Supplement-feeder behaviour

The fixed-effects models did not detect statistically significant associations between the examined feeder-behaviour variables and recorded ADG.

| Feeder-behaviour measure | p-value |
|---|---:|
| Total feeder time | 0.486 |
| Total attendance | 0.738 |
| Total days | 0.760 |

These results indicate that the models did not identify statistically significant associations in this dataset. They do not establish that feeder behaviour is biologically unimportant or unrelated to growth.

### 3. Environmental associations

After removing linear period trends, relative humidity retained a positive association with period-level mean ADG. The corresponding associations for rainfall and NDWI were not statistically significant.

| Environmental indicator | Time-adjusted correlation (r) | p-value |
|---|---:|---:|
| Relative humidity | 0.614 | 0.015 |
| Rainfall | 0.310 | 0.260 |
| NDWI | 0.164 | 0.559 |

The relative-humidity result is exploratory. With only 15 independent periods, it should not be interpreted as evidence that humidity causes higher cattle growth.

## Research Figures

### Figure 1. Cattle growth across study periods

![Cattle growth across study periods](image/figure1_cattle_growth.png)

*Recorded average daily gain across the study periods, illustrating temporal variation in cattle growth.*

### Figure 2. Supplement-feeder behaviour and growth

![Supplement-feeder behaviour analysis](image/figure2_feeder_behaviour.png)

*Visual summary of the examined feeder-behaviour measures and their associations with recorded average daily gain.*

### Figure 3. Environmental indicators and growth

![Environmental associations with cattle growth](image/figure3_environmental_associations.png)

*Summary of environmental associations with period-level mean growth, highlighting the distinction between initial and time-adjusted correlations.*

## Research Outputs

The repository includes the prepared dataset, three analysis notebooks, exported result tables, and figures.

- **[Notebook 1 — Data Audit](notebooks/01_Nelore_Cattle_Data_Audit.ipynb):** dataset structure, quality checks, and preparation.
- **[Notebook 2 — Growth and Associations](notebooks/02_Nelore_Cattle_Growth_and_Associations.ipynb):** descriptive analysis, feeder-behaviour models, and environmental associations.
- **[Notebook 3 — Final Results and Dashboard](notebooks/03_Nelore_Cattle_Final_Results_and_Dashboard.ipynb):** consolidated findings, tables, and figures.

### Exported tables

- [`final_growth_summary.csv`](data/final_growth_summary.csv)
- [`final_feeder_results.csv`](data/final_feeder_results.csv)
- [`final_environment_results.csv`](data/final_environment_results.csv)

## Repository Structure

```text
nelore-cattle-growth-environment/
├── data/
│   ├── nelore_cattle_prepared.csv
│   ├── final_growth_summary.csv
│   ├── final_feeder_results.csv
│   └── final_environment_results.csv
├── notebooks/
│   ├── 01_Nelore_Cattle_Data_Audit.ipynb
│   ├── 02_Nelore_Cattle_Growth_and_Associations.ipynb
│   └── 03_Nelore_Cattle_Final_Results_and_Dashboard.ipynb
├── image/
│   ├── figure1_cattle_growth.png
│   ├── figure2_feeder_behaviour.png
│   └── figure3_environmental_associations.png
└── README.md
```

## Limitations and Interpretation

- **Limited environmental sample size:** environmental associations are based on 15 study periods, not 390 independent environmental observations.
- **Observational design:** the analyses identify associations and do not establish causality.
- **Temporal patterns:** time trends may influence observed relationships between growth and environmental indicators.
- **Generalisation:** findings from this dataset and study setting should not automatically be extended to other cattle populations or production systems.
- **Statistical uncertainty:** a non-significant result does not prove the absence of an association.

These limitations are central to interpreting the results responsibly and identifying priorities for future research.

## Reproducibility and Technical Skills

This project demonstrates an end-to-end quantitative research workflow involving:

- Data loading, auditing, and preparation.
- Descriptive and inferential statistical analysis.
- Fixed-effects modelling and correlation analysis.
- Time-trend adjustment.
- Research visualisation and CSV export.
- Structured Jupyter notebooks and documented analytical steps.

**Tools:** Python, pandas, NumPy, SciPy, statsmodels, Matplotlib, Jupyter Notebook, and GitHub.

## Relevance to Future Research

This project connects animal science with quantitative agricultural research. The workflow provides a foundation for further investigation of livestock productivity, animal behaviour, environmental variation, and data-driven farm management.

Potential extensions include evaluating additional predictors, testing model sensitivity, and analysing larger datasets with more independent environmental observations.

## Conclusion

The analysis documents variation in cattle growth, examines feeder-behaviour associations while accounting for animal and period differences, and evaluates environmental relationships using time-adjusted correlations.

Relative humidity showed a positive time-adjusted association with period-level mean ADG, whereas the examined feeder-behaviour measures did not show statistically significant associations in the fitted models. Given the observational design and small number of independent periods, these findings should be treated as exploratory.

The project demonstrates a transparent, reproducible approach to analysing agricultural data and communicating results with appropriate statistical caution.
