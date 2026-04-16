# A Geospatial Dataset of Landing Sites in Mexico

[![DOI](https://zenodo.org/badge/1113160684.svg)](https://doi.org/10.5281/zenodo.19608740)

## About
The raw data come from Rodríguez et al. (2004). These data report fish landing sites in Baja California, Baja California Sur, and Sonora for sites identified by name, CONAPESCA site code, and geographic coordinate. The data were manually 
extracted by region from pdf to Excel, and a comprehensive geopackage is created in this repository in connecting the CONAPESCA site code to the geographic coordinate by a document specific landing site key.

Full citation: Ramírez Rodríguez, M., López Ferreira, C., & Hernández Herrera, A. (2004).  Atlas de localidades pesqueras de Baja California, Baja California Sur y Sonora. México Instituto Politécnico Nacional, Centro Interdisciplinario de Ciencias Marinas, Comisión Nacional de Acuacultura y Pesca

## Data set construction

- Step 1: Manually extract sitekey tables from [PDF](data/raw/Atlas_2004.pdf) into [Excel](data/raw/atlas_locations_raw.xlsx), with one sheet per "region"
- Step 2: Combining regional sheets into one comprehensive data frame
- Step 3: Build a geopackage of locations  by [Combining ](code/sitekey_cleaning.html) geographic coordinate and CONAPESCA site code by the Atlas specific site code (Clave)
- Step 4: Cleaning of sites in which a single key is mapped to different locations 
- Step 5: Final cleaning 
- Step 6: Visualization of data
- Step 7: Exporting of final [Geopackage](data/processed/sites_key.gpkg)

## Output data description

### [sites_key.gpkg](dat/processed/sites_key.gpkg)

A geopackage (vector) data set with X rows and Y columns:

- `Localidad_key`: Character. Landing site names from Atlas site descriptions 
- `Clave`: Character. Five digit, Atlas specific reference code
- `Captura`: Character. CONAPESCA site code
- `Desembarque`: Character. Identification code - often identical to CONAPESCA code with a leading zero
- `geom`: geometry. Latitude/longitude coordinates

## How to access these data

The raw data, both in [PDF](data/raw/Atlas_2004.pdf) and [Excel](data/raw/atlas_locations_raw.xlsx) form are available publicly in the repository. The finalized [sites_key.gpkg](dat/processed/sites_key.gpkg) is also provided.
