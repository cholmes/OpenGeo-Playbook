.. _spatialize:


Spatializing non-spatial data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Since there is much data out there that has an implicit though not explicit geospatial location we should make it easy to incorporate that data in to the geo world.  The main source of vector data is spreadsheets and basic access databases that have addresses, zip codes, census blocks, state names, or other boundaries.  All but addresses require an ability to 'join' the column listing the boundary or point location with a set of geometries.  Ideally there'd be a bunch of well known, possibly crowdsourced, boundaries that everyone could use.  And then people would also have the option to easily upload a spatial dataset to be joined against.  And there'd be a nice GUI to select what information to join.

For addresses we need a great geocoder, which is a problem that is far more than just software, but extends in to open data.  OpenAddress.org has made a good first pass at the effort, but we need much more data.  OpenStreetMap has some address information, and perhaps Microsoft and MapQuest can help now that they're going that route.  Ideally most any location search application would use an open address database and also have the built in facilities to correct and improve the addresses.  Past the data there should be great geocoding software that can plug in to the open address database, but also would be easily to write plugins that work with other datasets.  The final piece for a truly great geocoder is to crowdsource the corrections - misspellings and alternate names and the ways people refer to a place in shorthand.  One could imagine collecting a database of all searches, and hopefully also instrument the results of those searches.  And then researches could apply natural language processing and other advanced techniques to build an engine that is quite good at correcting.

For raster data there is scanned images and unrectified aerial images.  One should be able to upload either and then using online tools rectify them based on identifying points in common.  There are already several projects out there like this, but we'd like to bring that in to GeoNode so that more types of data can easily be uploaded.  Similar techniques and user interface likely could also be applied to vector data that's not located geospatially, like CAD drawings.  

* Open Source geocoder - there are already several, but not has great critical mass.  Ideally you want one that is pluggable and has lots of different backend implementations the way GeoTools or GDAL can read lots of different formats.

* Open Address database and tools - good possibilities with OSM and OpenAddress, but they need critical mass, and integrated tools that can be included in other web applications so users can correct data as they are using it.

* Web interface for 'joins' - need to make a great GUI to join data together, and to upload data to be joined.  There is some proprietary stuff that does this, but nothing great in the open source world.  On the backend it'd be a great improvement to have GeoServer able to handle joins on the fly and across data formats (though realistically if you're having people upload then you probably want to keep it in the same data source)

* GeoExt components for rectifying scanned images and photos.  And possibly also CAD files.

