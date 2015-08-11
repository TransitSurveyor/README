# TransitSurveyor Project Description

**author:** Jeffrey Meyers (jeffrey.alan.meyers@gmail.com)

Copyright © 2015 Jeffrey Meyers. This program is released under the "MIT License". Please see the file COPYING in this distribution for license terms.



The [TransitSurvey](https://github.com/TransitSurveyor) *Organization* contains repositories required to build a surveying system that can be used to collect the boarding and alighting locations of passengers using public transit. This project was initially built for use in an Origin-Destination survey conducted by [TriMet](http://trimet.org/) in 2015. The code is split into four repositories as follows:

+ [MobileSurvey](https://github.com/TransitSurveyor/MobileSurveyor)
  + Android client for field collection
  + written in Java, preloaded with sample data from TriMet
+ [API](https://github.com/TransitSurveyor/API)
  + server API for receiving data from clients
  + written in Python using Flask
  + uses PostgreSQL
  + deployed using NginX and uWSGI
  + repo contains setup script needed to build database with sample data and deploy using an Ubuntu server
+ [Data](https://github.com/TransitSurveyor/Data)
  + contains sample source data required to build data dependencies
  + a simple python script that generates the data inputs required by **API** and **MobileSurveyor** from the source data
+ [Dashboard](https://github.com/TransitSurveyor/Dashboard)
  + **WARNING** This repo is not really in a state that is usable  
  + web app for viewing data

### High Level Setup

1. Follow the build instructions in the `README` inside the [MobileSurveyor](https://github.com/TransitSurveyor/MobileSurveyor) repo. This will build an android app that provides the user interface for collecting boarding and alighting locations.
2. To setup the backend database and web services you will want to follow the `README` inside the [API](https://github.com/TransitSurveyor/API) repo. You will need to set up a VPS and run the setup shell script to build the database and deploy that application.
3. Both repositories are loaded with sample data, but to generate your own follow the `README` instructions in the [Data](https://github.com/TransitSurveyor/Data) repo. You will construct your source inputs and run the build script. After that the outputs will need to be copied into the `data_inputs` folder in both the `MobileSurveyor` and `API` repos.





