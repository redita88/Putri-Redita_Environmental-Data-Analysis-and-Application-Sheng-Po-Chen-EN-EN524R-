**Assignment 6 — Environmental Statistics & Scientific Interpretation**

**Notebook:** `notebooks/05_statistics.ipynb`

### Research Question
How is relative humidity (RH) related to air temperature (AMB_TEMP) in the Taiwan environmental dataset?

### Selected Variables
- `RH`: Relative Humidity (%)
- `AMB_TEMP`: Air Temperature (°C)

### Statistical Analysis
1. Descriptive statistics: mean, median, SD, Q1, Q3, and IQR.
2. Distribution of relative humidity.
3. IID bootstrap 95% confidence interval for mean RH.
4. Lag-1 temporal autocorrelation assessment.
5. Pearson and Spearman correlation between `AMB_TEMP` and `RH`.
6. Sensitivity analysis using IQR-based potential RH outliers.

### Main Findings
- Mean RH: **64.84%**
- Median RH: **65.00%**
- SD: **9.15%**
- IQR: **12.00%**
- IID bootstrap 95% CI for mean RH: **64.01%–65.66%**
- Pearson correlation: **r = -0.500**
- Spearman correlation: **ρ = -0.402**
- Eight potential RH outliers were identified using the IQR rule.
- After temporarily excluding these potential outliers, Pearson correlation changed to **r = -0.445** and Spearman correlation to **ρ = -0.383**.

### Interpretation
Air temperature and relative humidity showed a moderate negative association in the analyzed dataset. The relationship remained negative after the potential outliers were temporarily excluded, although its magnitude became weaker.

### Limitations
The dataset contains only one calendar day of observations, which limits temporal representativeness. Temporal dependence may cause the IID bootstrap confidence interval to underestimate uncertainty, and a day-block bootstrap could not be applied because only one calendar day was available. The observed statistical association does not demonstrate causation.

### Reproducibility
Run `notebooks/05_statistics.ipynb` to reproduce the statistical summaries, figures, bootstrap analysis, correlations, and sensitivity analysis.
## Assignment 5 – Data QA/QC

This assignment evaluates the quality of the processed environmental
dataset from Assignment 4.

- Selected variables: AMB_TEMP and RH
- Starting observations: 476
- Missing AMB_TEMP/RH: 0
- Invalid RH outside 0–100%: 0
- Potential IQR outliers: 11
- Primary QA/QC dataset: 476 observations
- Sensitivity analysis: correlation changed from r = -0.500 to r = -0.409

Potential statistical outliers were flagged and retained rather than
automatically removed.
# Assignment 4 – Data Processing

## Research Question
How does relative humidity (RH) vary with air temperature (AMB_TEMP) in Taiwan?

## Data Source
- Provider: Taiwan Ministry of Environment (MOENV)
- Dataset: AQX_P_35
- Access method: MOENV Open Data API

## Processing Workflow
The Assignment 4 processing workflow is documented in `notebooks/03_processing.ipynb`.

The main processing steps are:
1. Retrieve AQX_P_35 data from the MOENV Open Data API.
2. Select AMB_TEMP and RH observations.
3. Convert concentration values to numeric format.
4. Remove invalid or missing concentration values.
5. Reshape the data from long to wide format by monitoring site and time.
6. Remove observations without complete AMB_TEMP–RH pairs.
7. Create the final analysis-ready table.

## Processed Output
`analysis_ready_temperature_humidity.csv`

The final analysis-ready dataset contains 476 complete temperature–humidity observations.



## W3 Data Source

### MOENV Air Quality Data

- Provider: Ministry of Environment (MOENV)
- Dataset: AQX_P_432 — Air Quality Index
- Access method: MOENV Open Data API
- Access date: 2026-10-01
- Temporal resolution: Hourly
- Raw snapshot: `data/raw/moenv_AQX_P_432_2026-10-01_sample.json`

**Known limitation:**  
The snapshot represents data available at the retrieval time and is not a complete historical dataset.

------------------------------------------------------------------------------------------------------------
# EN524R / CE801V — Week 2 GitHub Demo

## Research Question
How does PM2.5 vary over time at Zhongli station, and how is it related to basic meteorological conditions?

## Data
Teaching dataset: `data/sample/zhongli_aq_2025.csv`

Columns in the supplied sample:
- datetime
- station
- PM2.5
- O3
- NO2
- TEMP
- RH
- WS

## Workflow
1. Open `notebooks/01_air_quality_demo.ipynb`.
2. Run all cells from top to bottom.
3. Inspect the data and document one QA/QC decision.
4. Create an exploratory PM2.5 time-series figure.
5. Verify the notebook runs in both JupyterLab and Google Colab.

## Environment
Python 3 with:
- pandas
- matplotlib

Install dependencies with:

```bash
pip install -r requirements.txt
```

## Reproducibility Note
Large/raw datasets should not be committed to the repository. Use `data/sample/` for a small reproducible teaching sample and document the original data source in this README.

## AI Assistance
If AI tools are used, document what they assisted with and how the output was verified.
