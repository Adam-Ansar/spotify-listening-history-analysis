# Spotify Listening History Analysis

## Table of Contents

- [Project Overview](#-project-overview)
- [Features](#features)
- [Data Source](#data-source)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Features / Key Deliverables](#-features--key-deliverables)
- [Technologies Used](#-technologies-used)
- [Project Structure](#-project-structure)
- [Results & Insights](#-results--insights)
    - [Hypothesis 1: Weekend vs. Weekday Listening](#-hypothesis-1-weekend-vs-weekday-listening)
    - [Hypothesis 2: Shuffle Mode & Track Skipping](#-hypothesis-2-shuffle-mode--track-skipping)
    - [Hypothesis 3: Mobile vs. Desktop Listening Duration](#-hypothesis-3-mobile-vs-desktop-listening-duration)
- [Challenges and Limitations](#challenges-and-limitations)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## 🎯 Project Overview

This project dives deep into a personal Spotify listening history dataset to uncover intriguing patterns and user behaviors. By meticulously cleaning and manipulating the raw data, we explore various hypotheses related to listening activity, shuffle mode usage, and platform preferences. The goal is to transform raw listening logs into actionable insights about how a user interacts with Spotify

## Features

- Data cleaning and preprocessing
- Time-based analysis (hourly, daily, monthly trends)
- Top artists, tracks, and genres identification
- Session detection and analysis
- Hypothesis testing
- Visualization of listening habits
- Insights into user preferences

## Data Source

This analysis is derived from a dataset from kaggle. The link to the dataset is as follows: https://www.kaggle.com/datasets/anandshaw2001/top-spotify-songs-in-countries

## Setup Instructions

1. **Clone the repository:**
    ```bash
    git clone https://github.com/yourusername/spotify-listening-history-analysis.git
    cd spotify-listening-history-analysis
    ```

2. **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3. **Place your Spotify history data:**
    - Copy your exported Spotify history file (e.g., `StreamingHistory.json`) into the project directory.

4. **Open the notebook:**
    - Launch Jupyter Notebook and open `spotify_analysis.ipynb`.

## Usage

- Run each cell in `spotify_analysis.ipynb` sequentially.
- Modify file paths or parameters as needed to match your data.
- Review the outputs and visualizations for insights.

## ✨ Features / Key Deliverables

- **Robust Data Cleaning & Preprocessing:** Handles missing values, removes duplicates, and standardizes categorical data for high data quality.
- **Timestamp Conversion:** Converts raw timestamp strings into proper datetime format for accurate time-based analysis.
- **Hypothesis Testing:**
    - **Weekend vs. Weekday Listening:** Compares total and per-track listening durations to identify activity peaks.
    - **Shuffle Mode & Skipping:** Examines if shuffle mode affects the likelihood of tracks being skipped.
    - **Mobile vs. Desktop Listening Duration:** Analyzes session lengths across mobile and desktop platforms.
- **Data Visualization:** Uses matplotlib and seaborn to create plots illustrating key findings from hypothesis tests.
- **Cleaned Data Export:** Outputs a ready-to-use CSV file (`spotify_history_cleaned.csv`) for further analysis or dashboard creation.

🧰 Technologies Used
- **Python 🐍**
- **pandas:** Powerful data manipulation and analysis
- **numpy:** Numerical operations
- **matplotlib:** Static data visualizations
- **seaborn:** Enhanced statistical data visualizations
- **scipy.stats:** Statistical tests (e.g., Chi-square, t-tests)
- **Jupyter Notebook:** Interactive and reproducible analysis

## 📁 Project Structure
```
spotify-listening-history-analysis/
├── data/
│   └── StreamingHistory.json         # Raw Spotify history data
├── notebooks/
│   └── spotify_analysis.ipynb        # Main analysis notebook
├── src/
│   ├── data_cleaning.py              # Data cleaning/preprocessing scripts
│   ├── analysis.py                   # Hypothesis testing and analysis scripts
│   └── visualization.py              # Plotting and visualization scripts
├── requirements.txt                  # Python dependencies
├── spotify_history_cleaned.csv       # Cleaned/exported dataset
├── Spotify_analysis_dashboard.pbix   # Power BI dashboard file
└── README.md                        # Project documentation
```

- `data/`: Contains raw Spotify history files.
- `notebooks/`: Jupyter notebooks for analysis.
- `src/`: Python scripts for cleaning, analysis, and visualization.
- `requirements.txt`: Python dependencies.
- `spotify_history_cleaned.csv`: Output of cleaned data.
- `README.md`: Project documentation.

## 📈 Results & Insights

The analysis uncovered several notable patterns in Spotify listening habits:

### 🎵 Hypothesis 1: Weekend vs. Weekday Listening

- **Finding:**  
    Weekdays saw much higher total listening time (**~14.3 billion ms**) than weekends (**~4.7 billion ms**).  
    _Interpretation:_ Spotify is used more during the workweek, possibly for background music or commuting.

---

### 🔀 Hypothesis 2: Shuffle Mode & Track Skipping

- **Finding:**  
    There is a statistically significant link between shuffle mode and skipping tracks  
    - **Chi-square:** 95.32  
    - **p-value:** 1.62e-22  
    - **Skip rate:**  
        - Shuffle mode: **5.5%**  
        - Sequential play: **4.2%**  
    _Interpretation:_ Users are more likely to skip tracks when shuffling, indicating greater selectivity.

---

### 💻 Hypothesis 3: Mobile vs. Desktop Listening Duration

- **Finding:**  
    Mean listening durations differ significantly by platform  
    - **T-statistic:** -3.6180  
    - **p-value:** 3.0450e-04  
    - **Average durations:**  
        - iOS: **166,547 ms**  
        - Android: **125,217 ms**  
        - Mac: **214,208 ms**  
    _Interpretation:_ Desktop platforms, especially macOS, support longer listening sessions compared to mobile.

---


### View the Interactive Dashboard

You can download the Power BI Desktop file (`.pbix`) from this repository to interact with the dashboard:

[Download Spotify Analysis Dashboard (.pbix)](https://github.com/Adam-Ansar/spotify-listening-history-analysis/blob/main/Spotify_analysis_dashboard.pbix)

**Note:** You will need Power BI Desktop installed to open this file.

🚧 Challenges and Limitations
- **Data Source Specificity:** Analysis is based on a single user's Spotify history; results may not generalize to all users.
- **"ms_played" Interpretation:** The `ms_played` column measures listening time, but very low values (e.g., 0ms) may reflect previews or glitches, affecting per-track averages.
- **Platform Categorization:** "Desktop" vs. "mobile" grouping is based on observed data; other devices (e.g., smart speakers) may have unique usage patterns not fully explored.


## 🤝 Acknowledgements

Help was received throughout this project from various sources. Notably, ChatGPT 4.1 was used to assist with troubleshooting errors, refining code, and providing different insights during the analysis and development process.

## License

This project is licensed under the MIT License.

---

**Contact:**  
For questions or feedback, please open an issue on GitHub.
