---
layout: default
title: Homework 5
---

# Homework 5: Bigfoot Sightings Visualization

---

## Plot 1: Heatmap of Sightings by Season and State

This heatmap visualizes the distribution of Bigfoot sightings across U.S. states and the four seasons (Spring, Summer, Fall, Winter). I created a new `season` column based on the month extracted from the `date` field in the dataset. The data was grouped using `pandas` to count sightings by `(state, season)` combinations.

I chose a **rectangular heatmap** with nominal x and y encodings for `season` and `state`, and a sequential color scale (`oranges`) to represent sighting counts. This format makes it easy to compare patterns across multiple states and times of year. States with high sighting activity in certain seasons become immediately apparent.

<div id="vis1"></div>

---

## Plot 2: Interactive Map Filtered by Classification

This interactive map displays geolocated sightings and includes a **dropdown filter** for the `classification` field (`Class A`, `B`, or `C`). Only rows with valid latitude and longitude data were used, and Altair’s geographic projection `albersUsa` makes the plot more intuitive.

The interactive dropdown helps users explore how credible sightings (e.g., `Class A`) differ in geographic distribution from less verifiable ones (`Class C`). Each point includes tooltip information showing the `state`, `date`, and classification.

<div id="vis2"></div>

---

## Links

- [The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)
- [The Analysis Notebook](https://github.com/Gaoyi-H/Gaoyi-H.github.io/blob/main/projects/hw5/hw5_notebook.ipynb)

---

<script type="text/javascript">
  vegaEmbed('#vis1', 'visualization.json');  // Heatmap
  vegaEmbed('#vis2', 'interactive.json');    // Interactive map
</script>