## Exercise 3. Quantifying Cyclist Safety: Exposure and Risk Index Modeling
Write a complete, optimized script using geopandas, matplotlib, osmnx, sklearn, mapclassify, and contextily to perform the following spatial analysis and visualization tasks for Mexico City. Follow the next steps:

1. **Load Data:** Load the local files: `infra_ciclista.geojson`, `vialidades_cdmx.geojson`, and `atus_cdmx.geojson`.
2. **Reprojection:** Convert the Coordinate Reference System (CRS) of all three GeoDataFrames to Web Mercator (EPSG:3857) to ensure alignment with web basemaps.
3. **Data Filtering:** Filter the cycling infrastructure data (`infra_ciclista`) to retain only active routes by excluding rows where the `ESTADO` column equals 'Fuera de servicio'.
4. **External data acquisition:** Use `osmnx` to download Points of Interest (POIs) for Ciudad de México, Mexico, targeting the tags: `{"amenity": ["supermarket", "market", "hospital", "school", "university", "kindergarten"], "leisure": "park", "recreation_ground"}`
5. **External data reprojection:** Project the POIs to CRS EPSG:3857.
6. **Buffer generation:** Generate a 20-meter buffer around the road network (`vialidades_cdmx`) and save it as `buffer_vial`.
7. **Incidents spatial join:** Perform a spatial join to count the number of traffic incidents (`atus_cdmx`) that intersect each road buffer. Add this count as a new integer column called `num_siniestros` (fill NaNs with 0).
8. **POIs spatial join:** Perform a second spatial join to count the number of POIs that intersect each road buffer. Add this count as a new column called `num_pois` while safely handling cases where no POIs intersect to ensure the column defaults to 0.
9. **Cycle infrastructure intersection:** Check for intersections between the road buffers and the active cycling infrastructure. Add a new binary column called `inf_ci` to the roads dataframe (1 if there is an intersection, 0 otherwise).
10. **Normalization:** Use `MinMaxScaler` from scikit-learn to normalize the `num_siniestros` and `num_pois` columns to a range of 0 to 1, naming these new columns `sin_norm` and `pois_norm`.
11. **Risk index calculation:** Calculate the risk index for cyclists by strictly applying the following formula to create a `risk_index` column:
     `risk_index = (sin_norm / (pois_norm + 0.01)) * (1 - inf_ci)`
12. **High-risk index filtering:** Filter the roads dataframe to keep only the segments where `risk_index` is greater than 1 and export this final filtered dataset as a GeoJSON file named `viaidades_risk.geojson`.
13. **Map construction:** Generate a high-quality static map using `matplotlib` and `contextily` showing only the filtered high-risk roads.
14. **Thematic styling:** Color the road lines according to their `risk_index` value: Use the `YlOrRd` colormap and `NaturalBreaks` classification scheme with k=5. Maximize line visibility by setting `linewidth=4` and explicitly removing the border (`edgecolor='none'`). Include a legend titled "Risk Index".
15. **Basemap:** Add a base map using `contextily` with the `CartOOB.Positron` style.
16. **Map elements:** Add a North arrow annotated in the bottom-left corner of the map. A black arrow pointing up with the letter 'N' above it.
17. **Formatting:** Add the title "Cyclist risk index" with a font size of 15, and maintain the axis coordinates by explicitly calling `ax.set_axis_on()`.
18. **Map export:** Save the final resulting map as a PNG file named `map_final_rendered.png` at 300 dpi and include the code to display the plot at the end.
