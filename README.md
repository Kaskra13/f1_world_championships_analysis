# Formula 1 World Championships Analysis (1950-2024)

A comprehensive data analysis project exploring 75 years of Formula 1 racing history, examining driver performance, constructor dominance, race dynamics, and the evolution of the sport across decades.

## Project overview

This project performs in-depth statistical analysis and visualization of Formula 1 World Championship data from 1950 to 2024. Using SQL queries, statistical modeling, and data visualization techniques, it uncovers patterns in driver performance, qualifying efficiency, pit stop strategies, and the changing dynamics of competitive racing over time.

## Key analyses

### Driver Performance
- **Career Statistics**: Analysis of top drivers by wins, podiums, and career longevity
- **Cumulative Performance Tracking**: Season-by-season win accumulation for legendary drivers (Hamilton, Schumacher, Verstappen, Vettel, Prost, Senna)
- **Position Gain Analysis**: Identification of drivers who consistently gain positions from qualifying to race finish
- **Lap Time Efficiency**: Average lap time comparisons across drivers with 500+ recorded laps

### Race Dynamics
- **Grid Position Correlation**: Statistical analysis (Pearson r=0.446, Spearman ρ=0.457) showing moderate positive correlation between starting grid position and final race position
- **Qualifying-to-Race Performance**: Drivers who excel at overtaking vs. those who maintain position
- **Pole Position Conversion**: Decade-by-decade analysis of pole-to-win conversion rates (ranging from 28% in 1980s to 52% in 2020s)

### Pit Stop Strategy
- **Duration Analysis**: Average pit stop times by driver (min: 22.5s for Michael Schumacher)
- **Team Efficiency**: Identification of fastest pit crews and their impact on race outcomes

### Constructor Analysis
- **Championship Dominance**: Season-by-season constructor performance and points accumulation
- **Era-Defining Teams**: Analysis of dominant constructors across different F1 eras

### Geographic Distribution
- **Circuit Analysis**: Interactive world map showing F1 race distribution by country
- **Venue Frequency**: Italy (107 races), UK (79 races), and Germany (79 races) lead historical hosting

### Temporal Trends
- **Decade-Level Evolution**: How F1 has changed across decades in terms of scoring systems, competitiveness, and race outcomes
- **Points Inflation**: Polynomial regression (R²=0.95) and LOWESS smoothing showing dramatic increase in average points scored per driver entry
- **Competitive Balance**: Analysis of whether the sport has become more or less competitive over time

## Technologies Used

- **Python 3.x**
- **Data Processing**: pandas, numpy
- **Database**: SQLite3
- **Visualization**: matplotlib, seaborn
- **Geospatial**: geopandas
- **Statistical Analysis**: scipy, statsmodels, scikit-learn
- **Data Source**: Kaggle API (kagglehub)

## Dataset

**Source**: [Formula 1 World Championship (1950-2020)](https://www.kaggle.com/datasets/rohanrao/formula-1-world-championship-1950-2020) via Kaggle

**Tables** (14 total):
- `races`: Race calendar and metadata (1,125 races)
- `results`: Race outcomes and performance (26,759 entries)
- `drivers`: Driver information (861 drivers)
- `constructors`: Team/constructor data (212 teams)
- `qualifying`: Qualifying session results (10,494 records)
- `lap_times`: Detailed lap-by-lap timing (589,081 laps)
- `pit_stops`: Pit stop duration and timing (11,371 stops)
- `circuits`: Track information and locations (77 circuits)
- `driver_standings`: Championship standings throughout seasons
- `constructor_standings`: Constructor championship data
- `seasons`, `status`, `sprint_results`, `constructor_results`: Supporting tables

## Installation & Setup

### Prerequisites
```bash
# Python 3.8 or higher
# Google Colab account (recommended) OR local Jupyter environment
```

### Local setup
```bash
# Clone the repository
git clone https://github.com/Kaskra13/f1_world_championships_analysis/ f1-championships-analysis
cd f1-championships-analysis

# Install required packages
pip install pandas numpy matplotlib seaborn scipy kagglehub geopandas statsmodels scikit-learn

# Set up Kaggle API credentials (place kaggle.json in ~/.kaggle/)
# Download from: https://www.kaggle.com/docs/api
```

### Running in Google Colab
1. Upload the notebook to Google Colab

2. The notebook will automatically download the dataset using kagglehub

3. Run all cells sequentially


## Usage
```python
# The project follows this workflow:

# 1. Data import
DATASET_PATH = kagglehub.dataset_download("rohanrao/formula-1-world-championship-1950-2020")

# 2. Database creation
# All CSV files are loaded into SQLite database for efficient querying
conn = sqlite3.connect('f1_data.db')

# 3. Analysis execution
# Run SQL queries and generate visualizations for each analysis section

# 4. Statistical modeling
# Polynomial regression and LOWESS smoothing on temporal trends
```

## Key findings

Top Performers
- Most Career Wins: Lewis Hamilton (105), Michael Schumacher (91), Max Verstappen (63)

- Most Podiums: Lewis Hamilton (202), Michael Schumacher (155), Sebastian Vettel (122)

- Best Average Pit Stop: Michael Schumacher (22.5s average)

Race Dynamics Insights
- Starting grid position has moderate predictive power for final position (r=0.446)

- Approximately 45% of race finishing positions can be explained by starting grid position

- Pole position conversion to wins has improved from 28% (1980s) to 52% (2020s), suggesting increased dominance of qualifying performance

Evolution of F1
- Average points per entry has increased significantly, especially post-2000 due to scoring system changes

- The sport has seen distinct eras of constructor dominance (Ferrari in 1950s/2000s, Mercedes in 2010s, Red Bull in 2020s)

- Geographic expansion: from European-centric to truly global championship


## Visualizations
The project includes the following key visualizations:

- Horizontal bar charts for top driver comparisons

- Scatter plots with hexbin density for grid-to-finish correlations

- Box plots for position distribution analysis

- Line plots for cumulative performance tracking

- Geographic choropleth maps for race distribution

- Time series plots with polynomial regression and LOWESS smoothing

- Bar charts for decade-level trend analysis
  
