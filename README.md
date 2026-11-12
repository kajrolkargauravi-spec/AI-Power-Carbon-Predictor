# AERIS — AI Energy Requirement Intelligence System

AERIS is a Streamlit application for estimating the electricity requirements and
associated carbon footprint of AI model training workloads. It uses a trained
Random Forest model to estimate power consumption and presents related
energy/carbon insights.

## Features

- Predicts AI-training power consumption using a trained machine-learning model.
- Explores energy requirements across workload and hardware configurations.
- Estimates associated carbon emissions using electricity carbon-intensity data.
- Presents model-related visualisations and prediction information through an
  interactive Streamlit interface.

## Tech Stack

- Python
- Streamlit
- Pandas and NumPy
- Scikit-learn and Joblib
- Plotly

## Project Structure

```text
AI-Power-Carbon-Predictor/
├── app.py
├── ai_power_random_forest_model.pkl
├── electricity_carbon_intensity_2024.csv
├── conformal_prediction_params.csv
├── requirements.txt
└── assets/
    ├── actual_vs_predicted.png
    ├── model_comparison.png
    ├── power_by_hardware.png
    ├── power_by_workload.png
    ├── power_distribution.png
    ├── residual_plot.png
    └── shap_importance.png
```

## Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/ai-power-carbon-predictor.git
cd ai-power-carbon-predictor
```

### 2. Create and activate a virtual environment

**Windows (PowerShell):**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Launch the application

```bash
streamlit run app.py
```

Streamlit will print a local URL (usually http://localhost:8501) that you can
open in your browser.

## Deploy on Streamlit Community Cloud

1. Push this repository to GitHub.
2. Sign in to Streamlit Community Cloud.
3. Create a new app and select this GitHub repository and branch.
4. Set the main file path to `app.py`.
5. Deploy. Keep the model, CSV files, and `assets/` directory in the repository
   so the application can access them at runtime.

## Notes

- The model file is a serialized Python object (`.pkl`). Only load it from a
  source you trust, and keep the Python/scikit-learn environment compatible
  with the environment used to train it.
- The carbon-intensity estimates depend on the values and assumptions in
  `electricity_carbon_intensity_2024.csv` and the calculations implemented in
  the application.
- This repository contains the application and its required deployment
  artefacts. Add a dataset, training notebook, or research paper only if you
  have permission to publish them and they contain no private or restricted
  information.
- Update this README with the public demo URL, final dataset/source citations,
  and any model evaluation details you have verified before publishing.

## Acknowledgement

Developed as an academic/research project. Add contributor, institution,
conference, and data-source acknowledgements here as appropriate.
