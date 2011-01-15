.. _collaborative_data:

Collaborative Data
~~~~~~~~~~~~~~~~~~

Though OpenStreetMap has clearly led the way on collaborative data OpenGeo believes that there should be technical alternatives, that interact with OSM with their standards.  The core collaborative data infrastructure that we see is inspired more by open source software than wikipedia - a number of diverse projects with different focuses, different communities and norms, and different tools.  One of OpenGeo's targets is existing government workflows, helping them be more collaborative and open internally, and working with their current tools.  So the core engine will be GeoServer and its transaction hooks.  The current protocols are WFS-T and WFS-V, but it should also implement OGC GeoSynchronization spec, OpenStreetMap's API and ESRI's Open GeoServices transactions.  The other standards piece that we want to see in the world is the geospatial equivalent of a 'patch' that can be shared between systems.  

The engine should make it possible to stay in sync with OSM or another versioning data store, with a review engine for organizations to apply their own workflow to crowdsourced data.  That workflow may include automated checks (running a suite of geoprocessing analysis, for example to make sure that topology is maintained) and user quality assurance, as well as post processes like tile creation and cache truncation, as well as notification to interested users and machines.  

There needs to be intuitive web-based tools [#f8]_, as well as great mobile tools that work offline.  This will take significant interaction design work, to make the editing, versioning, merging and conflict resolution accessible to anyone, even if they have no training.  This user interface work is one of the biggest challenges, and will take constant iteration over many projects.  Existing desktop GIS's should also all have plugins that work with the versioning backend.  And the versioning engine should be able to back on to ArcSDE Versioning, Oracle Workspace Manager, PostGIS and others.  

Another key is the social infrastructure around collaborative geospatial data, it needs to rival things like sourceforge and github in the open source software world.  There should be easy ways to join up with others, find a project to collaborate on, or to set up something for internal collaboration.  It needs to have all the tools to help collaboration, like issue trackers, notifications, wikis, and analysis tools.  And should also track reputation and be able to reward good contributions.

The ultimate piece for this will be distributed version control.  It's still an open research question if we should start with a DVCS like git and add spatial to it, or start with a spatial engine and add versioning.  Or some hybrid, like couchdb, which has a syncing model that can be used for versioning, and some decent spatial support.  But one shouldn't need a central server.  This should ideally enable someone to 'clone' someone else's geospatial repository and apply their own QA, so you can have government workflows that easily collaborate with private individuals and companies, with geospatial edits easily flowing between all systems, keeping great track of provenance and reputation so as to build dynamic trust metrics to judge the reliability of a dataset.

* WFS-Versioning or some open protocol, perhaps REST based.  OGC's GeoSynchronization is good to implement, but not sufficient for versioning, just review.

* Implement ESRI's GeoServices REST API for editing (for compatibility with ArcGIS Desktop and Arc web front-ends), that backs on to the versioning engine.

* Push the current WFS-V logic back to PostGIS, so it does versioning automatically, not just through GeoServer.

* Implement Oracle Workspace Manager and ArcSDE Versioning as backends, likely improve the open protocol to be compatible with how they work.

* Active notification of changes, ideally a nice webhook implementation.

* Investigate spatializing distributed versioning options like git and couchdb.

* Put editing in GeoNode, add more social tools and tracking.  So all edits are tied to a user account, with ratings and commenting.  Put in features like cloning an existing dataset and setting up one's own permissions, cascading changes, and starting a new dataset from scratch.

* Versioned editing in GeoNode, with deep tracking of changes across different branches of the same dataset.  And also plugins for issue tracking, wikis, notifications, etc.

* Versioning GUI components in GeoExplorer/GXP, so they can easily be combined and incorporated in other applications.  

* Client and server side topology and network validation and advanced javascript editing - as good as or better than desktop tools in terms of editing interaction, including shared polygon boundaries, COGO, and build polygon tools.

* User interaction research and design for visual display and resolution of geometry and attribute difference between versions, with implementation in GeoExt/OpenLayers

* 'Ethermap' - real-time collaboration on editing and viewing/styling maps, through javascript interfaces.

* Great tools, mobile and full web, to gather data, including government workflows, asset management, surveys, scientific data gathering, etc.  We should have a toolbox of custom workflows that can have anyone out in the field gathering data to feed in to collaborative workflows.

* Incorporation of versioning GUI in to a workflow pulling in changes from another location and performing appropriate QA to put it in to an 'endorsed' dataset.

* Verification and digital signatures for 'endorsed' datasets, edits and web services.

(break up in to data editing/gathering and versioning?)

.. rubric:: Footnotes

.. [#f8] See http://projects.opengeo.org/geoext/wiki/GeoEditor for our current designs, but these will evolve as people use it more and demand more.
