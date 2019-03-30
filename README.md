# osm_to_postgres
-Bash workflow for downloading, simple preprocessing, and loading Open Street Map data into a PostgreSQL/PostGIS database.
-These scripts probably aren't directly useful to you, but you can follow the workflow quickly and modify for your own purposes.
-The [OSM wiki and documentation](https://wiki.openstreetmap.org/wiki/Databases_and_data_access_APIs#osm2pgsql) has become much more complete than when I wrote these scripts.

### Setup

-Dependencies are all on [Homebrew](https://brew.sh/)

```
brew install wget
brew install osmium-tool
brew install osm2pgsql
brew install postgresql
brew install postgis
```
### Usage

`OSM-build` will run the scripts in correct order.

Otherwise:

```
OSM-download
OSM-extract
OSM-load2postgres
```

`OSM-dropdb` will drop the databases you just created.

### Notes

-Downloads go to `~/OSM-data/`

-The .geojson or other vector file for clipping large .osm.pbf files should also be located in `~/OSM-data/`. You provide these files yourself.

-The database creation script assumes you have setup a PostGIS extended template database called 'template_postgis'. [Here](https://postgis.net/install/) is the official documentation for PostGIS.


