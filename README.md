# An FBref Memoriam for Player Scouting and Team Analysis

*After Opta sold out to FIFA and billion-dollar betting companies, spurning data democratization and creative outlets for the average football nerd, I wanted to memorialize FBref's advanced data from the 2025/26 domestic season that remain accessible. If this sounds of any intrigue, join me in exploration! For questions or feedback, feel free to email: **idw2005@nyu.edu***

---

## What Is This?

This project features a football analytics notebook that scrapes, cleans, and visualizes player and team data from [FBref](https://fbref.com) via the [`soccerdata`](https://github.com/probberechts/soccerdata) library. It covers all five major European leagues - the Premier League, La Liga, Serie A, Bundesliga, and Ligue 1 - for a significant slice of the 2025/26 season.

Most of the interactive visualizations were built via Dash and Plotly, which won't render when viewed directly on Github. I'd recommend downloading the notebook and opening within your preferred IDE *or* **[visiting this website I made](https://fbref-visualizations.onrender.com/)**, using Dash and [Render.com](https://render.com/)!

---

## What's Inside

The notebook is organized into three chapters:

### Chapter 1 - Data Collection
Pulls and merges eight FBref stat categories (standard stats, shooting, passing, passing types, goal/shot creation, defense, possession, miscellaneous) into a single unified player dataframe of 2,346 player-seasons across 96 teams.

### Chapter 2 - Player Analysis
- **Center of Gravity (COG)** - a custom metric quantifying where on the pitch each player operates, both in terms of touches and defensive actions
- **K-Means Position Clustering** - data-driven reclassification of players into Defender / Wingback / Midfielder / Forward using within-team positional COG
- **Interactive Player Scatter** - explore the full player pool by position, league, or team
- **Player Radar Charts** - per-player stat profiles across key metrics
- **Player Similarity Finder (KNN)** - find the most statistically similar players to any player in the dataset
- **Player Scores & Leaderboard** - a composite scoring system ranking players by position group

### Chapter 3 - Team Analysis
- **Team Centers of Gravity** - aggregated positional profiles per team
- **COG Spine Chart** - compare up to 8 teams' positional COG profiles side by side
- **Side-by-Side Pitch Comparison** - visual pitch maps showing where each team's position groups operate
- **Touch COG vs. Tackle COG Scatter** - attacking intent vs. defensive engagement
- **Effect of Tactics & Rotation on Output** - squad rotation (minutes MAD) and attacking compactness vs. xG and goals
- **Correlation Heatmap** - which features correlate most strongly with xG?
- **Mann-Whitney U Tests** - statistical significance testing across tactical groupings

---

## Getting Started

### Prerequisites

- Python 3.11+
- A virtual environment (highly recommended)

### Installation

```bash
git clone https://github.com/yourusername/fbref-memoriam.git
cd fbref-memoriam
python -m venv .soccerenv
source .soccerenv/bin/activate        # Windows: .soccerenv\Scripts\activate
pip install -r requirements.txt
```

### Running the Notebook

```bash
jupyter notebook fbref_memoriam_2026.ipynb
```

> **Note:** The first run will scrape and cache data from FBref via `soccerdata`. This may take a minute. Subsequent runs will load from cache instantly.

---

## Tech Stack

| Purpose | Library |
|---|---|
| Football data | `soccerdata` |
| Data Munging | `pandas`, `numpy` |
| Statistics | `scipy` |
| Clustering & KNN | `scikit-learn` |
| Visualization | `plotly` |
| Interactive apps | `dash` |

---

## Project Structure

```
fbref-memoriam/
├── fbref_memoriam_2026.ipynb   # Main notebook
├── requirements.txt             # Python dependencies
├── README.md                    # You are here
└── .gitignore                   # Keeps cache and venv out of the repo
```

---

## A Note on Data

All data is scraped from FBref via the `soccerdata` library and cached locally. Please be respectful of FBref's servers - don't scrape excessively, and check `soccerdata`'s documentation for rate limiting guidance.

---

## License

MIT - Use however you please! Just don't pretend that you wrote it :)
