## Exercise 2. Estimation of cycling incidents 

Write a single Python script that processes spatial data regarding cycling infrastructure and bicycle accidents, performs a buffer analysis, and exports high-resolution visualizations.

1. **Load Data:** Read the following files using geopandas: `infra_ciclista.geojson`, `vialidades_cdmx.geojson`, and `atus_cdmx.geojson`. 
2. **Reprojection:** Convert the files' Coordinate Reference System (CRS) to Web Mercator ( EPSG:3857 ) so it aligns correctly with web basemaps.
3. **Data Filtering:** Filter the data using the following criteria:
    * Filter the cycling infrastructure data to keep only the rows where the `ESTADO` column is not equal to 'Fuera de servicio'.
    * Filter the `atus_cdmx` dataset to keep only rows where the `BICICLETA` column is not equal to 0. 
    * Store this filtered dataset in a variable named `siniestros_ciclistas`.
4. **Buffer generation:** Generate a 5-meter buffer around the active cycling infrastructure geometries. Store this in a new variable.
5. **Spatial join:** Perform a spatial join between the `siniestros_ciclistas` points and the buffered infrastructure to determine how many bicycle incidents intersect with the buffer.
6. **Statistical Calculation:** Calculate the total count and percentages of bicycle incidents that are inside and outside the buffer from the cycling infrastructure.
7. **Chart visualization and export:** Create a pie chart showing the percentage of incidents near vs. far from the cycling infrastructure. Add a shadow, use distinct colors, and include the percentage labels. Save the figure as `cycle_inicent_stats_pie.png` at 300 dpi with a tight bounding box.
8. **Map construction and layers:** Create a comprehensive map using matplotlib. Plot the `vialidades_cdmx` as a light grey background (thin lines, partial transparency). Plot the active cycling infrastructure as green lines. Plot the bicycle incidents as red points.
9. **Basemap:** Add a "CartoDB Positron" basemap to the plot using the contextily provider.  
10. **Map elements:** Add a North arrow annotated in the bottom-left corner of the map. A black arrow pointing up with the letter 'N' above it.
11. **Formatting:** Add the title "Bicycle Incidents in CDMX" with a font size of 15, maintaining the axis coordinates by explicitly calling `ax.set_axis_on()`.
12. **Map export:** Save the resulting map as `cdmx_bicycle_incidents_map.png` at 300 dpi with a tight bounding box.
