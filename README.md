# 🚆 Train Delay & Cancellation Risk (Tasks 1–3)

This project contains three Jupyter notebooks that build a complete pipeline for analyzing and predicting **train delays and cancellations** using weather, calendar, and geospatial data.

---

## 📁 Project Structure

- **task 1 clean.ipynb**  
  Exploratory data analysis (EDA), hypothesis testing, and spatial analysis of stations.

- **task 2.ipynb**  
  Delay prediction (regression) using Linear Regression, Random Forest, and XGBoost.  
  Also generates delay-risk buckets and saves processed features.

- **Task 3.ipynb**  
  Cancellation risk prediction (classification) using the engineered features from Task 2.

---

## 🗂 Generated / Required Data Files

- `data/stations/osm_germany_stations.geojson`  
  *(additional geodata – sent separately via email)*

- `data/processed/train_sub_task2.parquet`  
  *(created in Task 2 and reused in Task 3)*

- `data/processed/features_task2.json`  
  *(created in Task 2 and reused in Task 3)*

---

## ⚙️ Setup

### 1. Create a virtual environment
```bash
python -m venv .venv

2. Activate the environment

macOS / Linux

source .venv/bin/activate


Windows PowerShell

.\.venv\Scripts\Activate.ps1


Windows CMD

.\.venv\Scripts\activate.bat

3. Install dependencies
pip install -r requirements.txt

🌦 Data Sources
Weather

Weather data is fetched automatically using the meteostat library.
No manual download is required (internet connection needed).

Geodata

Station geodata is provided separately via email and must be placed here:

data/stations/osm_germany_stations.geojson

🔁 Reproducibility

All machine learning models use:

random_state = 42


Changing the seed will change the results.
Runtime Notice

The Random Forest hyperparameter optimizations in Task 2 and 3 are computationally expensive.
Expected runtime: ~30 minutes (depending on your machine)

▶️ Execution Order

task 1 clean.ipynb
In the end datasets are saved that are reused for task w

task 2.ipynb
After the train and test set are defined they are saved for reuse in task 3 that they can be preposessed further for the logistic regression and random forest

Task 3.ipynb

Start Jupyter:

jupyter lab or jupyter notebook

❗ Common Issues

Missing GeoJSON → place file in
data/stations/osm_germany_stations.geojson

pyarrow missing → required for Parquet files

No internet → Meteostat cannot download weather data
