---
name: Chicago Crime & Socioeconomic Analysis
tools: [Python, HTML, vega-lite, Altair, Pandas]
image: <vegachart schema-url="{{ site.baseurl }}/IS445_Final/final_visualization.png" style="width: 100%"></vegachart>
description: An interactive data journalism piece exploring Chicago crime patterns through temporal rhythms, transit hubs, and socioeconomic contexts.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Final Project: Deconstructing Chicago's Safety Landscape

This project analyzes reported crime incidents in Chicago from early 2026. Instead of simply mapping where crimes occur, this analysis delves deeper into the "when" and "why." By integrating contextual datasets such as socioeconomic hardship indexes, population demographics, and CTA transit station locations, this project aims to provide a more nuanced, normalized view of urban safety.

## Visualization 1: The 24-Hour Pulse of the City (Interactive Dashboard)

This interactive dashboard serves as the core exploratory tool, allowing users to investigate how different types of crimes ebb and flow throughout the week. 

**Design Choices & Interactivity:** The dashboard utilizes linked views to connect spatial data (the map) with temporal trends (the line charts). I deliberately segmented the 24-hour day into four distinct, semantic periods: *Morning (6am-12pm)*, *Afternoon (12pm-6pm)*, *Evening (6pm-12am)*, and *Late Night (12am-6am)*. I applied a custom intuitive color palette (e.g., bright orange for afternoon, dark navy for late night) to make these periods instantly recognizable. 

To provide an analytical baseline, I implemented a "Whole-to-Part" layering technique. A highly visible red/gray line represents the total daily incidents, while the segmented colored lines are overlaid on top. This allows readers to instantly identify which specific time period is driving a sudden spike in the city's overall crime rate. The dashboard supports cross-filtering: brushing over the map or selecting a specific crime type from the dropdown dynamically updates the temporal trend lines.

<vegachart schema-url="{{ site.baseurl }}/assets/json/interactive_dashboard.json" style="width: 100%"></vegachart>

---

## Visualization 2: Socioeconomic Context & Per Capita Analysis

Raw crime counts can be misleading, as they often merely mirror a neighborhood's population density. To correct this, I incorporated a secondary dataset containing Chicago Census demographic and hardship data. 

**Transformations & Analytical Approach:** In this visualization, I performed data aggregation to calculate the **crime rate per 1,000 residents** for each Community Area. By plotting population size against total crime incidents and adding a regression trend line, the scatter plot clearly highlights the outliers—neighborhoods that suffer from disproportionately high crime rates relative to their population size. 

The color encoding (`scale=alt.Scale(scheme='purples')`) maps to this newly calculated per-capita rate. This shift from absolute numbers to normalized rates provides a critical sociological lens, revealing how systemic socioeconomic factors, rather than just population density, correlate with neighborhood safety.

<vegachart schema-url="{{ site.baseurl }}/assets/json/poverty_scatter_regression.json" style="width: 100%"></vegachart>

---

*(Optional: To explore the exact spatial correlation between poverty density and crime incidents, use the overlay map below.)*

<vegachart schema-url="{{ site.baseurl }}/assets/json/poverty_crime_overlay.json" style="width: 100%"></vegachart>

---

## The Data & The Analysis

<div class="left">
{% include elements/button.html link="https://data.cityofchicago.org/Public-Safety/Crimes-2001-to-Present/ijzp-q8t2" text="The Raw Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/JoeyWang02/is445_final/blob/main/final2%263_Workbook.ipynb" text="The Analysis Notebook" %}
</div>
