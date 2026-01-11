# 🏃 From Finish Lines to Feature Engineering

**A data science project analyzing 2+ years of personal running data to predict half marathon performance and train toward a 1:30 finish.**

---

## The Story Behind the Data

I ran casually before moving to Germany in March 2022. But somewhere between navigating a new country, managing anxiety, and processing the decision to leave the Philippines—for political reasons, for personal ones—running became something else. It became how I stayed steady.

My first recorded Strava run is from May 2023. Since then, the data tells a story of consistency turning into capability:

- **Berlin Marathon 2024**: 3:58 — breaking the 4-hour barrier on my first full marathon
- **Hamburg Half Marathon 2025 (x2)**: Current PB of 1:50

Now I'm preparing for the **Copenhagen Half Marathon in September 2026**, and this time I'm not just running with heart—I'm running with data.

**The goal: 1 hour 30 minutes.**

That's 20 minutes faster than my current best. It's ambitious. It's measurable. And it's exactly the kind of challenge that makes data science real.

---

## What This Project Does

This isn't a theoretical ML exercise. It's built on my actual training runs—every slow recovery jog, every tempo session, every race-day effort logged in Strava over 2+ years.

**The project answers two questions:**

1. **Prediction**: Based on my training patterns, what finish time can I realistically expect?
2. **Prescription**: What training load, pace distribution, and weekly structure will get me to 1:30?

---

## Technical Approach

### Data Pipeline

```
Strava API → n8n Extraction → Pandas Cleaning → Feature Engineering → XGBoost Model
```

| Stage | Description |
|-------|-------------|
| **Extraction** | Strava API via n8n workflow automation—no manual CSV exports |
| **Cleaning** | Missing values, GPS outliers, unit standardization |
| **Feature Engineering** | Rolling averages, training load (TRIMP), pace zones, weekly volume trends |
| **Modeling** | XGBoost regression for finish time prediction |
| **Output** | Personalized training plan calibrated to the 1:30 target |

### Key Features Engineered

- **Acute:Chronic Workload Ratio** — injury risk indicator
- **Pace Zone Distribution** — time spent in Z2 (easy) vs Z4 (threshold)
- **Weekly Mileage Trends** — 4-week rolling averages
- **Long Run Percentage** — ratio of weekly long run to total volume
- **Race Specificity Score** — how closely training matches race pace demands

---

## Project Structure

```
├── data/               # Raw Strava exports and processed datasets
├── notebooks/          # Jupyter notebooks (numbered 01_ through 06_)
├── src/                # Reusable Python modules
├── n8n_workflows/      # Automation workflows for data extraction
├── models/             # Trained model artifacts
├── reports/            # Visualizations and analysis outputs
└── config/             # Project configuration
```

---

## Getting Started

```bash
# Clone the repository
git clone https://github.com/yourusername/strava-half-marathon-predictor.git
cd strava-half-marathon-predictor

# Set up virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

### Running the Pipeline

1. Import n8n workflows from `n8n_workflows/` into your n8n instance
2. Configure Strava API credentials in `config/`
3. Run notebooks in sequence: `01_data_extraction.ipynb` → `06_training_plan.ipynb`
4. Generated model saved to `models/`

---

## Current Status

🚧 **Work in Progress**

- [x] Strava API connection via n8n
- [x] Data extraction and initial cleaning
- [ ] Feature engineering pipeline
- [ ] Model training and validation
- [ ] Training plan generation
- [ ] Dashboard for tracking progress

---

## Why This Matters

For career changers learning data science: your life already generates data worth analyzing.

This project is my way of practicing what I'm learning at WBS Coding School—not on Kaggle datasets, but on something I care about. The transferable skills are real: data cleaning is data cleaning whether it's survey responses from advocacy work or GPS coordinates from a morning run.

If you're also training for a race and want to build something similar, the notebooks are documented with that in mind.

---

## Tech Stack

- **Python** (pandas, scikit-learn, XGBoost)
- **n8n** for workflow automation
- **Strava API** for data extraction
- **Jupyter** for exploratory analysis
- **Matplotlib/Seaborn** for visualization

---

## Author

**Vennel Chenfoo**  
Data Science & AI Bootcamp @ WBS Coding School  
Career changer. Runner. Building with data.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/yourprofile)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-black)](https://github.com/yourusername)

---

## License

MIT License — feel free to adapt for your own running data.

---

*"The race isn't just about the finish line. It's about what the data teaches you along the way."*
