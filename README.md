# TA Chimaliro School Site Suitability

A geospatial analysis of potential primary-school locations in Traditional Authority (TA) Chimaliro, Thyolo District, Malawi.

The project brings together the TA boundary, main roads, mapped schools, and protected areas. The analysis workflow reprojects the layers to WGS 84 / UTM Zone 36S (`EPSG:32736`), clips them to the TA boundary, and maps the resulting suitable areas.

## Project files

```text
chimaliiro-school-site-accessibility/
├── data/
│   ├── ta_chimaliro.geojson
│   ├── roads.geojson
│   ├── existing_schools.geojson
│   └── protected_areas.geojson
├── notebooks/
│   └── school_site_analysis.ipynb
└── outputs/
    ├── suitable_areas_map.png
    └── interactive_map.html
```

## Input data

- **TA boundary:** TA Chimaliro from Malawi's level-3 administrative boundaries.
- **Main roads:** Malawi OpenStreetMap extract, filtered to `primary`, `secondary`, and `trunk` roads.
- **Existing schools:** OpenStreetMap education-facilities data filtered to `amenity=school`. OSM does not consistently identify school level, so this layer can include non-primary schools.
- **Protected areas:** Malawi records from the October 2026 World Database on Protected Areas (WDPA) release. The GeoJSON contains polygon areas and point-only records.

## Outputs

- `outputs/suitable_areas_map.png` — static map of suitable areas and the analysis layers shown by the notebook.
- `outputs/interactive_map.html` — interactive Folium map with an OpenStreetMap basemap and the suitable-area overlay. Open it in a web browser; an internet connection is needed for the basemap tiles.

## Running the Code

Launch Jupyter Notebook from the project folder and run all cells inside `notebooks/school_site_analysis.ipynb`.

The notebook is included at `notebooks/school_site_analysis.ipynb`. It uses GeoPandas, Matplotlib, and Folium, and loads the four GeoJSON files from `data/`. The path setup works when Jupyter starts in either the project folder or its `notebooks/` folder. It writes both maps to `outputs/` (creating that folder if needed).


