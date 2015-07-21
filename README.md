# TransitSurveyor Project Description

The [TransitSurvey](https://github.com/TransitSurveyor) *Organization* contains repositories required to build a surveying system that can be used to collect the boarding and alighting locations of passengers using public transit. This project was initially built for use in an Origin-Destination survey conducted by [TriMet](http://trimet.org/) in 2015. The code is split into three repositories as follows:

+ [MobileSurvey](https://github.com/TransitSurveyor/MobileSurveyor)
  + Android client for field collection
  + written in Java, preloaded with sample data from TriMet
+ [API](https://github.com/TransitSurveyor/API)
  + server API for recieving data from clients
  + written in Python using Flask
  + uses PostgreSQL
  + deployed using NginX and uWSGI
  + repo contains setup script needed to build database with sample data and deploy using an Ubunutu server
+ [Dashboard](https://github.com/TransitSurveyor/Dashboard)
  + web app for viewing data
  + **WARNING** This has has not been updated recently. It might be difficult to get this to build and work with an actual database. Use at your own risk **WARNING**
  
  
## TODO

The system was built using [TriMet's GIS data](http://developer.trimet.org/gis/). I would like to try and build the project with data from a different transit agency. This would help document how a different transit agency could use this.
