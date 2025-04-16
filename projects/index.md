# HW5 – Bigfoot Sightings

[**The Data**](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv)  
[**The Analysis**](https://github.com/Gaoyi-H/Gaoyi-H.github.io/blob/main/projects/hw5/hw5_notebook.ipynb)

---

## Heatmap: Sightings by State and Season

This heatmap visualizes Bigfoot sightings aggregated by U.S. state and season. Each rectangle represents a count of sightings in a particular state-season combination. The x-axis encodes the season (Winter, Spring, Summer, Fall), and the y-axis encodes the state abbreviation. The color of each tile uses the `'oranges'` color scale to reflect the number of sightings — the darker the tile, the more reports were filed in that combination. The tooltip provides more specific counts for each cell.

To generate this chart, I grouped the dataset using `groupby(['state', 'season'])` in pandas to calculate the total number of sightings for each combination. This transformation simplified the data and allowed us to focus on aggregated patterns rather than individual sightings.

<div id="heatmap" style="margin-top: 30px;"></div>

---

## Interactive Map: Sightings by Classification

This interactive map displays individual Bigfoot sightings based on their geographic coordinates. It includes only sightings with valid latitude and longitude values and filters the classification to `Class A`, `Class B`, or `Class C`. Each sighting is represented as a colored circle, plotted on a U.S. map using the Albers USA projection. The color encoding uses Altair’s `'set1'` categorical scheme to distinguish between classification types. Hovering over a point shows the sighting’s state, date, and classification.

To enable interactivity, I used `alt.param()` and `binding_select()` to create a dropdown menu, allowing users to filter sightings by classification. This adds a layer of user engagement and makes it easier to analyze spatial differences between report types. Data was filtered using pandas to remove missing coordinates and keep only the relevant classification categories.

<div id="mapchart" style="margin-top: 30px;"></div>

---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>
<script>
  vegaEmbed('#heatmap', 'heatmap.json');
  vegaEmbed('#mapchart', 'interactive_map.json');
</script>
