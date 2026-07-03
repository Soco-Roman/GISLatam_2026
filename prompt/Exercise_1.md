## Exercise 1. Visualization of traffic incident concentration

Write a script to visualize traffic incident data on a map. Please generate the complete code to perform the following steps:

1. Setup: Import `geopandas`, matplotlib.pyplot`, and `contextily`. Include a `try/except` block
to install `contextily` via `!pip install` if it is not already available.
2. Load Data: Read the GeoJSON file located at `/content/atus_cdmx.geojson` into a GeoDataFrame.
3. Reprojection: Convert the GeoDataFrame’s Coordinate Reference System (CRS) to Web Mercator (EPSG:3857) so it aligns correctly with web basemaps.
4. Plot Setup: Create a plot with a figure size of 12x10.
5. Data Visualization: Plot the incidents as scatter points. Style them with a red color, black edge color (`edgecolor='k'`), and an opacity of 0.4 (`alpha=0.4`).
6. Dynamic Sizing: Scale the size of each point based on the number of injured people, which is found in the `TOTHERIDOS` column. Use the formula:
     markersize = TOTHERIDOS * 20 + 5`
7. Basemap: Add a "CartoDB Positron" basemap to the plot using the `contextily` provider.
8. Map Elements: Add a North arrow (a black arrow pointing up with the letter 'N' above it) annotated in the bottom-left corner of the map.
9. Formatting: Add the title "Traffic Incidents in CDMX" with a font size of 15, maintaining axis coordinates (`ax.set_axis_on()`).
