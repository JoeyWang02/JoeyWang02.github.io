---
name: Chicago Crime Analysis 2026
tools: [Python, Altair, Vega-Lite]
image: https://raw.githubusercontent.com/joeywang02/IS445_Final/main/final_visualization.png
description: An interactive data journalism article exploring the spatial, temporal, and socioeconomic dimensions of crime in Chicago.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Rhythms of the City: A 2026 Chicago Crime Perspective
**Authors: Group 6 (Xinyi Chen, Zhongyin Wang)**

Crime is rarely a random occurrence; it is a complex tapestry woven from geography, time, and social conditions. This report dives into tens of thousands of crime records from the 2026 Chicago dataset to uncover where, when, and why these incidents happen.

---

## 1. Central Exploration: The Crime Landscape (Interactive Dashboard)

To understand Chicago's safety, one must look at the city as a whole while being able to zoom into its parts. Our primary dashboard provides this flexibility.

<vegachart schema-url="https://raw.githubusercontent.com/joeywang02/IS445_Final/main/json/interactive_dashboard_new.json" style="width: 100%"></vegachart>

**How to Interact:**
You can directly click on any **Police District** on the map to filter the entire view. Once a district is selected, the bar chart on the right automatically updates to show the specific "Primary Types" of crime in that area, and the timeline below reflects the incident fluctuations for that specific region over the first half of 2026. This linked interactivity allows you to compare the safety profiles of downtown business hubs versus residential neighborhoods.

---

## 2. Temporal Patterns: The City's Heartbeat (Contextual Analysis)

While the dashboard shows *where* crime happens, it is equally important to know *when* it peaks. We analyzed crime density across every hour of every day of the week.

<vegachart schema-url="https://raw.githubusercontent.com/joeywang02/IS445_Final/main/json/crime_heatmap_interactive.json" style="width: 100%"></vegachart>

**Data Insight:**
This heatmap reveals a distinct "temporal pulse." Regardless of the district, there is a significant surge in reported incidents during late Friday and Saturday nights (10 PM – 2 AM), likely correlated with nighttime social activities. Conversely, weekday mornings show the lowest activity. By understanding these "risk windows," city resources can be deployed more effectively when they are needed most.

---

## 3. Socioeconomic Roots: Poverty and Safety (Contextual Analysis)

To look beyond the surface, we must ask: What drives these geographical differences? We correlated the total crime count of each community with its poverty rate.

<vegachart schema-url="https://raw.githubusercontent.com/joeywang02/IS445_Final/main/json/poverty_scatter_regression.json" style="width: 100%"></vegachart>

**Deep Dive:**
The scatter plot above reveals a sobering reality: a strong positive correlation exists between economic hardship and crime volume. Communities like **Austin** and **South Shore**, which face higher poverty rates, also show the highest incident counts. However, "The Loop" remains an outlier—showing high crime despite low poverty—due to its massive influx of commuters and tourists. This suggests that while poverty is a structural driver of crime, high-density commercial areas create different "targets of opportunity."

---

## Data & Methods

This analysis was conducted using Python and the Altair visualization library. All data is sourced from the City of Chicago Open Data Portal.

* **Crime Dataset**: [Crimes - 2026 (Preliminary)](https://data.cityofchicago.org/)
* **Social Indicators**: [Census Data - Socioeconomic Indicators](https://data.cityofchicago.org/)

<div class="left">
{% include elements/button.html link="https://data.cityofchicago.org/Public-Safety/Crimes-2026/f6bk-yv3r/about_data" text="View Raw Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/JoeyWang02/IS445_Final/blob/main/final2%263_Workbook.ipynb" text="Analysis Notebook" %}
</div>
