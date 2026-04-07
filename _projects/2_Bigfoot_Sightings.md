---
name: Bigfoot Sightings Analysis
tools: [Python, HTML, vega-lite, Altair]
image: assets/pngs/bigfoot_map.png
description: Interactive visualizations exploring Bigfoot sightings across the US by season.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Homework 5: Bigfoot Sightings Analysis

This project explores a dataset of Bigfoot sightings, visualizing the frequency of these events across different seasons and their geographic distribution across the United States. 

## Visualization 1: Bigfoot Sightings by Season

This visualization is a bar chart displaying the total number of Bigfoot sightings across different seasons. I chose to use a bar chart (`mark_bar`) because it is highly effective for comparing aggregate counts across distinct categories. For the encodings, the x-axis represents the `season` as a nominal variable (`:N`), sorted in descending order of frequency to make the most common seasons immediately obvious. The y-axis represents the quantitative count of records (`:Q`). 

**Colormap & Transformations:** I applied a custom high-contrast nominal colormap (`#2ca02c`, `#ff7f0e`, `#d62728`, `#1f77b4`) to the `season` variable to visually distinguish each bar, making the chart more engaging and accessible even though the x-axis already provides the labels. On the analysis side, I transformed the `date` column into standard Pandas timestamps using `pd.to_datetime` and ensured Altair could handle the large dataset by using `alt.data_transformers.disable_max_rows()`.

<vegachart schema-url="{{ site.baseurl }}/assets/json/plot1.json" style="width: 100%"></vegachart>

---

## Visualization 2: Geographic Distribution (Interactive)

The second plot is an interactive geographic scatter plot showing the specific coordinates of Bigfoot sightings across the United States. I mapped the `longitude` and `latitude` to the x and y axes using the `albersUsa` projection to accurately represent the US map, and layered this over a base map of state boundaries (`mark_geoshape`) for spatial context. 

**Design Choices & Interactivity:** For the color scheme, I specifically implemented a **semantic color mapping**. I explicitly mapped the seasons to highly intuitive colors: green for Spring, red for Summer, orange for Fall, and blue for Winter. For interactivity, I implemented a dropdown menu parameter that allows users to filter the data points by season. Furthermore, I explicitly sorted the dropdown menu options chronologically ('Spring', 'Summer', 'Fall', 'Winter') rather than relying on the machine's default sorting. When a specific season is selected, the unselected points fade into a light gray (`#dcdcdc`). This interactivity makes the visualization much more engaging, as users can actively explore whether Bigfoot migration patterns change depending on the time of year without visual clutter.

**Transformations & Data Quality:** I noticed an outlier point labeled 'State: Indiana' floating outside the US map due to incorrect GPS coordinates in the raw dataset. However, I explicitly chose not to apply geographic filtering transformations to remove it. My design choice was to preserve the raw integrity of the dataset to highlight the potential human errors (e.g., missing negative signs) in crowdsourced Bigfoot sighting reports.

<vegachart schema-url="{{ site.baseurl }}/assets/json/plot2.json" style="width: 100%"></vegachart>

---

## The Data & The Analysis

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/JoeyWang02/JoeyWang02.github.io/blob/main/python_notebooks/bigfoot_analysis.ipynb" text="The Analysis" %}
</div>
