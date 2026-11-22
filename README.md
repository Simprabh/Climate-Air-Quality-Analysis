## Delhi Climate & Air Quality Analysis 2025
Analysis of hourly air-quality and weather data for six Delhi locations in 2025. Our team acts as advisors to a public-health organisation and answers the question: which environmental indicators deserve priority investment?
📋 Investigation Blueprint	docs/Investigation_Blueprint.md
📄 Technical Report	report/Technical_Report.md
🗂️ Project board (Kanban)	See the repository's Projects tab · screenshot
📊 Charts	visualizations/
Key findings
Particulate matter dominates. PM10 (Pearson r = 0.93) and PM2.5 (Spearman ρ = 0.83) are the indicators most strongly associated with AQI. CO and NO2 are weakly or negatively associated.
Strong seasonality. AQI and PM10 are elevated from March to June (peak March–May); PM2.5 peaks in December–January. Only July–September keep particulate levels near national standards.
Humidity is the weather variable most clearly (negatively) associated with AQI.
Data-quality limits. The six locations contain only two distinct pollution series, and 13.2 % of daily AQI values exceed the official 0–500 scale. Results support indicator-level priorities, not location rankings.
Recommendations: (1) Monitor particulates (PM10 and PM2.5). (2) Strengthen health alerts for March–June, tracking humidity and wind speed. (3) Check the three hotspots (Dwarka, IGI Airport, Okhla Phase III) against official station data before targeted interventions. Details are in the Technical Report.
Monthly AQI profiles
Team
Member	Role
Simprabh Dhillon (@Simprabh)	Project coordinator & repository maintainer
Aparna Devi Nangunoori	Business analyst & EDA lead
Sandesh Malla	Data engineer
Apoorva Kulkarni (@apygit)	Domain researcher & reporting
Repository structure
├── data/
│   ├── raw/
│   │   └── delhi-weather-aqi-2025.csv           # Original hourly data (52,560 rows)
│   └── processed/
│       └── Delhi_Air_Quality_Daily_2025.csv     # Cleaned daily data (2,190 rows)
│
├── notebooks/
│   ├── data_cleaning_preprocessing.ipynb        # 1. Quality checks, cleaning, daily aggregation
│   └── EDA_AQI_.ipynb                           # 2. EDA, correlations, charts
│
├── visualizations/                              # 7 charts, saved automatically by the EDA notebook
├── docs/
│   ├── Investigation_Blueprint.md
│   ├── kanban_board.png
│   └── Delhi Map (6  Locations).png
├── report/
│   └── Technical_Report.md
├── README.md
└── requirements.txt
How to run
bash
git clone https://github.com/Simprabh/Climate-Air-Quality-Analysis.git
cd Climate-Air-Quality-Analysis

python -m venv .venv
source .venv/bin/activate          # Windows: .venv\Scripts\activate
pip install -r requirements.txt

jupyter nbconvert --to notebook --execute --inplace notebooks/data_cleaning_preprocessing.ipynb
jupyter nbconvert --to notebook --execute --inplace notebooks/EDA_AQI_.ipynb
Alternatively, open the notebooks in Jupyter or VS Code and run them in order (cleaning first, then EDA). The cleaning notebook writes data/processed/Delhi_Air_Quality_Daily_2025.csv, and the EDA notebook reads it and saves all charts to visualizations/.
Dataset
Delhi weather and air-quality data 2025 — public dataset from Kaggle. Locations: Anand Vihar, Connaught Place, Dwarka, IGI Airport, Okhla Phase III, Rohini. Variables: AQI, PM2.5, PM10, CO, NO2, temperature, humidity, pressure, wind speed.
Master's in Data Science — Schiller International University, Heidelberg

