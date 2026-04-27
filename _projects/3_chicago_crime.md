---
name: Chicago Crime Analysis 2026
tools: [Python, Altair, Vega-Lite]
image: https://raw.githubusercontent.com/joeywang02/IS445_Final/main/Screenshot 2026-04-26 at 20.37.05.png
description: An interactive data journalism article exploring the spatial, temporal, and socioeconomic dimensions of crime in Chicago.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Crime in Chicago: Where, When, and Why?
**Authors: Group 6 - Xinyi Chen, Zhongyin Wang**

Crime is not just a set of numbers, it is a complex issue shaped by geography, time, and social conditions. To better understand public safety in Chicago, our team analyzed tens of thousands of crime records from the 2026 dataset. This article explores where these incidents happen, when they peak, and how they relate to the economic health of different neighborhoods.

---

## 1. Central Exploration - The Crime Landscape

To understand safety in a city as large as Chicago, we need to look at both the big picture and specific neighborhoods. Our central dashboard allows you to explore these geographic patterns interactively.

<vegachart schema-url="https://raw.githubusercontent.com/joeywang02/IS445_Final/main/json/interactive_dashboard_supernew1.json" style="width: 100%"></vegachart>

**How to Use the Dashboard:**
This is a "linked" visualization. 
* Filter by Location: Click on a District on the map to see its local crime ranking and timeline.
* Filter by Category: Click on a Crime Type in the bar chart to see how that specific incident is distributed across the city.
* Combined View: You can select both a District and a Crime Type at the same time. This allows you to dive deep into the specific timeline of a single crime category within a specific neighborhood (for example, seeing exactly when "Thefts" peak in "District 18")
  
**Key Findings from the Dashboard:**
* When viewing the map without filters, District 12 shows the darkest orange color, indicating it has the highest total volume of reported crimes in the city so far in 2026.
* Across the entire city, Theft is the most frequent crime type, significantly outnumbering other categories like Battery or Criminal Damage.
* Interestingly, safety patterns change when you look at specific crimes. By clicking "THEFT" on the bar chart, the map updates to show that District 18 actually reports the highest number of thefts, even surpassing the overall leader, District 12. This suggests that certain areas face very specific types of security challenges.
* A closer look at the timeline for District 18 reveals a rhythmic pattern: theft incidents frequently **peak at the beginning of each month**. This specific insight could help local authorities better schedule their security resources during these high-risk days.

---

## 2. The Weekly Pulse - When is Crime Most Frequent?

While location is important, time also plays a key role. We created a heat map to show the density of crimes across different hours of the day and days of the week.

<vegachart schema-url="https://raw.githubusercontent.com/joeywang02/IS445_Final/main/json/crime_heatmap_interactive.json" style="width: 100%"></vegachart>

**Data Insight:**
By using the dropdown menu above, you can see patterns for different types of crime. Generally, the data reveals a "temporal pulse" in the city. Many reported incidents peak during late Friday and Saturday nights, likely linked to increased social activity. In contrast, weekday mornings are often the quietest periods. Understanding these patterns can help the city allocate resources more effectively and help citizens stay more aware during high-risk hours.

---

## 3. Beyond the Surface - The Impact of Economy on Safety

To look beyond the surface, we must ask: What drives these geographical differences? We correlated the total crime count of each community with its poverty rate.

<vegachart schema-url="https://raw.githubusercontent.com/joeywang02/IS445_Final/main/json/poverty_scatter_regression.json" style="width: 100%"></vegachart>

**What the Data Tells Us:**
The scatter plot above reveals a sobering reality: a strong positive correlation exists between economic hardship and crime volume. Communities like **Austin** and **South Shore**, which face higher poverty rates, also show the highest incident counts. However, there are interesting exceptions. For example, "The Loop" (downtown) shows high crime levels despite having a lower poverty rate. This is because high-density commercial areas attract a large number of visitors and tourists, creating more opportunities for certain crimes. This suggests that while economic support is vital for long-term safety, different areas require different policing and social strategies.

---

## Data & Methods

This analysis was conducted using Python and the Altair visualization library. All data is sourced from the City of Chicago Open Data Portal.

* **Crime Dataset**: [Crimes - 2026 (Preliminary)](https://data.cityofchicago.org/Public-Safety/Crimes-2026/f6bk-yv3r/about_data)
* **Social Indicators**: [Census Data - Socioeconomic Indicators](https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2/about_data)

<div class="left">
{% include elements/button.html link="https://data.cityofchicago.org/Public-Safety/Crimes-2026/f6bk-yv3r/about_data" text="View Raw Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/JoeyWang02/IS445_Final/blob/main/final2&3_Workbook_2.ipynb" text="Analysis Notebook" %}
</div>
