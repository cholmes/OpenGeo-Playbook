.. _other_tech:

Other Tech to be built
~~~~~~~~~~~~~~~~~~~~~~

A smattering of other technology that doesn't fit in to any of the above use cases, but that we are interested in seeing open implementations of.

* Better real-time support - be able to handle real time vehicle locations and user check-ins.  Storing them in the backend and having nice tools to display the latest and dig back in to time.  And geoprocessing tools geared towards deep analysis of historical real-time data.

* 3-D - we should be able to take advantage of Oracle's 3D support, and push more 3D functionality in to PostGIS.  Ideally we also understand CAD and can produce the 3D open standards like Collada models.  We also hope to eventually do a 'spinny globe' in html5 with javascript, that can overlay data from our services and also show real 3d data.  This is not an area we know a whole lot about, but it's definitely of interest.

* Schemaless data support - we'd like to be able to leverage new data backends like CouchDB, Cassandra, Mongo, etc.  Some of these need to have spatial operations added to them, but for our stack all we really need is a spatial index, the rest we can handle.

* Continued support for new open standards.  WFS 2.0 and WCS 2.0 are probably the leading ones, but new versions of other specs and other open standards of things we do or want to do, like geosynchronization.

* Cloud scaling, including making on demand rendering and geoprocessing clusters, and being able to auto scale all tiers to deal with any load.

* Performance and scalability - all the software we build should work as well or better than everything else out there, and should be continually tested and refined.