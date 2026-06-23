# Analysis of Selected Player Statistics from the Top 5 European Football Leagues (2023/24 Season)

A comprehensive data acquisition, analysis, and visualization project examining player performances across Europe's top 5 football leagues (Premier League, La Liga, Serie A, Bundesliga, and Ligue 1) during the 2023/24 season. 

This repository contains the source code (`Project.qmd`) for an interactive Quarto report that integrates data engineering, statistical profiling, spatial mapping, and advanced data visualization techniques using **R**.



## Project Overview & Objectives
In modern football, minor statistics are increasingly scrutinized, sometimes leading to the overestimation or misinterpretation of a player's true baseline abilities based purely on their nationality or league context. This project sets out to objectively cross-examine these metrics with the following core focuses:
- **League Demographics & Overperformance:** Comparing the English Premier League against continental competitors.
- **Goal & Assist Efficiency:** Normalizing offensive metrics and exploring standard vs. advanced metrics (like Expected Goals - xG).
- **Age Curve Dynamics:** Mapping total goal contributions against player age to identify peak performance windows.
- **Geographic Representation:** Tracking the distribution of talent using coordinates and interactive mapping.
- **Match Endurance & Discipline:** Assessing minutes played by outfield players and analyzing referee strictness across leagues.


## Key Analytical Features & Visualizations
The interactive report leverages an array of specialized R packages to structure its findings:
1. **Offensive Output Profiling (`ggplot2` / `patchwork`):** Dual horizontal bar charts mapping top goalscorers in the Premier League vs. other European leagues.
2. **Positional Goal Distribution (`ggplot2` boxplots):** A look at strike-rate variations across leagues for forwards with a minimum of 10 complete 90-minute appearances.
3. **Age vs. Contribution Mapping (`ggpattern`):** An elegant area-gradient chart showcasing how Goal+Assist (G/A) volume clusters around the global league average age of 25.
4. **Geographic Plotting (`leaflet`):** An interactive Esri World Imagery base-map highlighting global talent hubs with custom data-driven circle markers.
5. **Migration and Demographic Flow (`networkD3`):** A Sankey diagram mapping player nationalities to their current competing leagues to showcase regional integration trends (e.g., South American pipelines).
6. **Volumetric Assist Modeling (`wordcloud2`):** A custom-shaped keyword cloud visualizing the top 100 assist providers color-coded dynamically by domestic league.
7. **Interactive Structure Browsing (`collapsibleTree`):** A responsive hierarchical node graph mapping out the entire dataset down from League to Team to Player level.


## Repository & File Directory Structure
```text
├── Project.qmd          # Core Quarto document containing the data pipeline and R code
├── .gitignore           # Git ignore rule file (filters out heavy builds and cache)
├── top5players.csv      # Main raw dataset consisting of comprehensive player statistics
├── glowny.png           # Header/banner visual asset for the report UI
├── 2324.jpg / 2425.png  # Asset imagery for Team of the Season comparisons
├── circle.html          # Intermediary compiled circle-packing widget (xG representation)
└── lastplot.html        # Compiled interactive collapsible tree widget
```


## Getting Started

### Prerequisites
To replicate or run the Quarto compilation pipeline locally, you will need **R (>= 4.0)**, **RStudio**, and **Quarto CLI** installed.

### Required Packages
Open your R console and install the necessary dependencies utilized across the project:
```R
install.packages(c(
  "ggplot2", "tidyverse", "readxl", "readr", "dplyr", "patchwork", 
  "ggpattern", "magick", "cartography", "plotly", "leaflet", "sf", 
  "htmltools", "htmlwidgets", "networkD3", "data.tree", "treemap", 
  "collapsibleTree", "jpeg", "grid", "wordcloud2", "RColorBrewer", "devtools"
))

# Additional htmlwidgets installed via GitHub if required:
# devtools::install_github("jeromefroe/circlepackeR")
```

### Execution & Rendering
Render the document directly from your terminal or RStudio command line to obtain the finalized client-side HTML:
```bash
quarto render Project.qmd --to html
```


## Data Sources
- **Player Performance Records:** Derived from curated Kaggle datasets outlining seasonal top-5 European league parameters.
- **Advanced Match Analytics:** Cross-referenced against structural outputs found on [WhoScored Statistics](https://www.whoscored.com/Statistics).
- **Visualization Frameworks:** Built in accordance with best practice structures hosted by the [R Graph Gallery](https://r-graph-gallery.com).

---
**Author:** Jakub Szamik  
**Project Date:** January 1, 2025  
