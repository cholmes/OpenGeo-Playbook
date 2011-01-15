.. _search:

Search
~~~~~~

Searching and finding geospatial information is perhaps the least solved problem OpenGeo is hoping to help tackle.  The first level is just searching for data sets, ignoring data points.  The traditional approach has been to make a 'catalog', but there is as of yet nothing to aggregate everything in catalogs, and they haven't really taken off.  Google has been attempting to crawl geospatial information, but with their consumer focus they haven't spent much good time on finding actual sets of data, and they only really try on KML and GeoRSS, neither of which is great for representing an entire set of data.  ESRI has made some decent strides with their ArcGIS Servers, which all have web accessible root pages, so they can get crawled and searched by Google.

GeoNode is our framework for helping to solve the problem.  Initially we've just focused on properly exposing the data - putting data and metadata together in one easily accessible web page.  And each GeoNode has a catalog that can be searched.  The next steps are to make the data web pages more accessible to google, so they are easily crawled and searched by any web engine.  And also to start to tackle federated search, being able to do a search across GeoNodes.  The other piece is to bring social metadata - comments, rating, tags, views - in to the same page, so that other systems can more easily rank and retrieve better search results.  In the short term we're not looking for federated search to really solve the problem, but just to easily search across a few known locations.  And then having all the information be as accessible as possible in as many open standards as possible.

The next problem is even harder, which is to search individual points.  Both those within given datasets and just other information out there.  Google is now good at the later with their mapping search, but they aren't any good at points within datasets.  It is a very hard problem, as individual points don't have much metadata - just finding a point one has no idea what any of its attributes even mean.  One approach towards this, which we do support, is the route that INSPIRE has gone, of standardizing data attributes.  This way one can find known definitions of a 'road' or a 'waterway' and understand it even if it comes from different sources.  The other approach, which we also support, is to just get as much information - data, metadata, social metadata, applications, maps, uses - out there as possible, so that smarter people can try to tackle the problem.  Once there is enough valuable geospatial information out there then it will make economic sense for more people to invest in the problem.  So as OpenGeo we focus more on the 'open', and will help support any emerging standards to make data easier to search.  But we may at some point try to help encourage a central DNS type registry with automatic publishing of metadata from all GeoNodes to it, so data that is shared is searchable by default.

The other thing that OpenGeo can do to help this is make it possible to do a search on any given GeoNode against all the data there.  So incorporating all the extra information it has available to give back results based on a location.  This should be particularly helpful for searches on a very small geographic area, as you can ask several GeoNodes that you know have the type of information you're interested if they have _anything_, and then from there go from the data to the dataset information to figure out what it is and if it's relevant.

* Better crawlability (REST services) of datasets and individual data points.

* Federated search across GeoNodes - one interface to search, across several nodes, with properly weighted results.

* Search across datasets for individual points.

* Better Catalog / CSW.  GeoNetwork needs some major contributions (possibly build it up around solr, since it's already lucene based), or else we need something that can really scale and handle not only metadata but also help with the data.  

* App Schema advances to better support known schemas, including on the fly schema transformation for users to put the data in to a form they know.  

* Visual workbench tools for application schemas to do the data transforms without requiring complex configuration or code.

* GeoNode support for all types of data, metadata, social metadata and use, and incorporating that in to search results for datasets and eventually individual data as well.

* DNS type central registry of all geospatial information, with automatic notification to that registry built in by default to OpenGeo software (though could easily be disabled)
