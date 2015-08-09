# TransitSurveyor Project Description

The [TransitSurvey](https://github.com/TransitSurveyor) *Organization* contains repositories required to build a surveying system that can be used to collect the boarding and alighting locations of passengers using public transit. This project was initially built for use in an Origin-Destination survey conducted by [TriMet](http://trimet.org/) in 2015. The code is split into fours repositories as follows:

+ [MobileSurvey](https://github.com/TransitSurveyor/MobileSurveyor)
  + Android client for field collection
  + written in Java, preloaded with sample data from TriMet
+ [API](https://github.com/TransitSurveyor/API)
  + server API for recieving data from clients
  + written in Python using Flask
  + uses PostgreSQL
  + deployed using NginX and uWSGI
  + repo contains setup script needed to build database with sample data and deploy using an Ubunutu server
+ [Data](https://github.com/TransitSurveyor/Data)
  + contains sample source data required to build data dependencies
  + a simple python script that generates the data inputs required by **API** and **MobileSurveyor** from the source data
+ [Dashboard](https://github.com/TransitSurveyor/Dashboard)
  + web app for viewing data
  + **WARNING** This has has not been updated recently. It might be difficult to get this to build and work with an actual database. Use at your own risk **WARNING**
  
  
## TODO

The system is currently built using [TriMet's GIS data](http://developer.trimet.org/gis/). I would like to try and build the project with data from a different transit agency. This would help show different transit agencies how they could easily use it (assuming they generate GTFS schedule data).

#### Building PostgreSQL database from GTFS

GTFS provides a specification transit agencies use to publish their data. You will need to build a database using [gtfsdb](https://github.com/OpenTransitTools/gtfsdb). Exports could then be generated from this database.

Follow the directions to build gtfsdb. You will then want to load a db using the is_spatial flag.

```shell
# assuming you have created a spatially enabled database
db=postgresql://user:password@localhost:port/database
gtfs=http://developer.trimet.org/schedule/gtfs.zip

git clone https://github.com/OpenTransitTools/gtfsdb.git
cd gtfsdb
virtualenv env
env/bin/pip install psycopg2
env/bin/python setup.py install
env/bin/gtfsdb-load --database_url ${db} --is_geospatial ${gtfs}
```
