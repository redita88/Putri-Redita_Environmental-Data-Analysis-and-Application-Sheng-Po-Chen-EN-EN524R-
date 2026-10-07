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
