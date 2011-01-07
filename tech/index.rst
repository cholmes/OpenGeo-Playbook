.. _tech:

Tech
============

Intro to tech
--------------------


Philosophy
----------

Central to OpenGeo's technical philosophy is open source, not just the license but in the strength of real communities.  Diverse contributors working towards their own purpose but taking the time to collaborate build better software than any group focused on a narrow problem.  We want a diverse ecosystem around the core projects we work on, so that the technology will live on even if OpenGeo as an organization dies for any reason.  

The practical technical implications of that is that we architect small, flexible pieces, and work to push code we write down to the lowest library levels.  Those libraries are already used by many developers, and our contributions make those libraries even better and more flexible, building a virtuous circle of more contributors using it for more diverse purposes.  Though initially it is more work to take the time to do things right, we've seen time and again that the extra work pays off [#f1]_.  So when we start a new project like GeoNode we take the time to improve all the underlying API's to meet our needs, even though it would be far more efficient in the short term to just code what we need.  We'll also take the time to start new open source projects for functionality that others can use, instead of just making them work with our needs [#f2]_.

So the core of philosophy is to not take shortcuts, and to seize any chance to improve the underlying libraries.  But we also are not continually redoing things in the abstract, we wait till there is a clear advantage to refactoring things in a new way, where it will help our clients and users.  

We also rely heavily on open standards, but are not slaves to them.  Open Standards have been a huge advantage to getting acceptance for our open source software, and we use them as the first choice for how our software stack is architected [#f3]_.  The primary pathway for how each piece interacts with another is through an open standard, so that we can easily swap out one piece for another.  But we will often extend standards to get 'more' out of them, be that more performance, more options, or more flexibility.  We also always implement leading ad hoc standards, things that don't go through a real standards process but are widely used.  If a standard does not exist for something we do want to do we'll also try to find other software that does the same thing and follow and collaborate with them, to hopefully help lead to a good open standard in the future.

The other core philosophy is to leverage the work of others as much as possible.  We don't want to be writing new libraries for functionality that other open source projects handle, and if it doesn't quite handle all our needs we'll try to contribute to them to make it work for us.  This has been a huge advantage, as we've been able to add huge amounts of functionality by just making an existing library work for us [#f4]_.  

Vision 
------
OpenGeo's technical vision is a flexible, powerful set of geospatial libraries and projects that can help any existing or new geospatial information be shared and improved.  To the end user, any device (mobile, desktop, offline) should be able to access and contribute to any data for any area (subject to appropriate permissions).  OpenGeo software will run the gamut from powering complete infrastructures to providing key integration points for existing systems to share in an open way.  It should scale up to massive cloud infrastructures and down to small, offline mobile devices.  The software should be a joy to code against, with great documentation for intuitive and powerful APIs.  And it should play a key role in an emergent infrastructure - the geospatial web, which makes possible end user functionality that no one company or government could provide alone.

Some things an end user should be able to do:

* Browse all historical and current aerial imagery for the area they're interested in.  A base of open information, an option to add in imagery from Google or Microsoft if the device meets their terms, a way to login and get additional data they have access to, the ability to purchase the latest imagery (or even task a satellite, a plane or a drone), and a method for flying a balloon to gather their own aerial photos [#f5]_.

* Join, create or even fork any collaborative data effort.  If you can't find a good map of surf spots in Argentina you should be able to start it and let others contribute.  If you notice that a meter on the city's parking map is in the wrong place you should be able to report it to them and have it go through their QA process and get incorporated.  And we should all be naturally contributing to an open base map instead of navtech, google, teleatlas, governments and open street map all gathering and refining the same data [#f6]_.  One should also be able to fork an existing data effort, and have one's own distributed version control system that can have one's own QA and syncing process with another data maintenance effort.  Collaborating geospatially should be even easier than it is to collaborate on open source software, since map making is something that is accessible to everyone.  

* Work in environments with low, occasional, or no internet connectivity.  Should be able to load up data on a mobile device and go out in the field, edit and resolve conflicts when back online.  Places without internet can still receive hard drives of disks, and mail back data they gather.  And when internet cuts out or there is a small pipe we should have methods to make data transfer seamless with smart caching throughout.  

* Make their own mashups.  A user should be able to put together various datasets, style them the way they want, and optionally add some interesting processes for others to do.  Should be able to grab any data layers and tweak them to be the way they want, with advanced cartography and editing tools that are intuitive and powerful.  And then select from many processes to let others use.  The resulting mashup application, should be easily shared on the web, and it source can optionally be shared with others to tweak it further.

* Apply geospatial processing in intuitive ways, taking existing data sets and then creating new data by applying interesting analysis, easily sharing the results.  Right now geospatial processing is more the domain of 'experts' who can afford expensive tools and/or gain significant experience in figuring it all out.  It should be easy for experts to design custom applications that expose advanced geoprocessing to newer users, by translating it to their domain.  And there should be a nice shallow learning curve for those new users to explore more and more processing power that is relevant to them.  All this should be available for free and completely on the web.  

* Easily transform data that is not immediately spatial in to a map, where it can be overlaid and processed with other geospatial data sets.  So taking excel spreadsheets and access databases, geocoding or joining with boundary files, and making that in to spatial data that is shared in many formats.  And uploading scanned maps and rectifying it online.  And taking unstructured data and deducing what is geospatial about it.

* Search for relevant local datasets and individual vector data points.  So if a user has a sudden interest in cardinals they can search by their house and get all the latest spottings by birdwatchers and scientists in diverse data sets.  Or if they learn about a chemical that causes cancer they can find readings done by EPA or citizen scientists.  From the data points they could pull the full dataset and geoprocess it with other relevant demographic information to do analysis, or spot trends and problems [#f7]_.

Technical challenges
--------------------
(This should maybe go in another section)

Overlaying these use cases on to the technical depth needed to truly solve them reveals most of them take quite a bit of work.  And there's no way OpenGeo could possibly build all the needed technology on its own.  But we're committed to getting open versions of all the tech needed for the above.  We won't likely be the ones to build it all, but if there are critical pieces that are not open we will keep trying to find ways to get it built.  

Browse all imagery 
~~~~~~~~~~~~~~~~~~

The center of this problem needs to be Open Aerial Map, which has struggled to get off the ground for a variety of reasons.  In a nutshell it's a solid base infrastructure where anyone can upload the latest imagery under a public license.  It should eventually be its own foundation, that can raise fund and in-kind donations for a massive server infrastructure.  Ideally this is a distributed infrastructure, so that it can scale to the level needed for all historical.  It should also provide a framework for other services to share imagery in a known protocol, optionally with security restrictions.  Technically a really intuitive web-based front end that lets one browse all the imagery that one has access to will likely go a long ways.  It should also be able clip/ship/zip on the pieces one has the right permissions to, so one could do further analysis.  On the server side it should be super easy to upload new imagery (or ship a drive to a known location), and also to point at an existing file system (or network of file systems), and automatically crawl it and extract all the needed metadata.  Covered in this would also be when raw imagery hits the file system, being able to rectify it and process it according to predefined chains, making it automatically available as WMS, WCS and tiles.  All data added should also get search interfaces, crawled by Google, available as CSW, and with both extracted and user contributed metadata.  Should also be able to handle video, from drones and new satellites, making it searchable and providing nice animations.

* GeoExt/OpenLayers Time interface, with lots of good interaction design to handle diverse datasets and their appropriate metadata in an intuitive manner.  Should also be able to log in to remote servers where one has more permissions, and also upload data.

* Network crawler to find imagery and register it.

* GeoServer/GeoNode integration with OSSIM plus likely GeoSolution's GeoBatch (or some equivalent), to pull down and process latest imagery.

* Cloud scaling of imagery processing and storage.

* Handling of video imagery formats.

* Protocols for caching and distributing imagery between different physical servers, for fast access and also offline capabilities.  Perhaps investigate p2p-inspired solutions, though something like DNS, centralized but able to failover easily, is more tractable.

* Helping take grassrootsmapping.org further, hooking it up to a global infrastructure, and making it accessible to anyone.  

* Hardware and hosting infrastructure for the core Open Aerial Map imagery.  Likely could limit it to just the latest imagery, and have others handle the historical stuff with good open protocols.  But there should be some dedicated central infrastructure with real resources behind it to ensure that it'll always be available.

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

Offline, low bandwidth and mobile environments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Though OpenGeo is entirely focused on web-based environments, using the browser as the primary user interface, we intend for all of our sofware to be able to function offline and in situations with limited or occasional bandwidth.  Part of this is possible due to open source software - with no license fees and the increasing power and storage of mobile computers we can often just include our server side software on clients.  One can also imagine situations where a local office isn't online or has really low bandwidth, but can run a small dedicated computer that can sync and serve data locally.  We'd like to make the software very smart with regards to caching and syncing, where it can only send the changes, and also automatically figure out what data to sync first, based on statistics of actual use.  This should be possible with both vector and raster data.

We also plan to make our software available on even more limited devices, like mobile phones.  Our first goal will be to get OpenLayers running on iPhone and Android applications, which is almost complete.  After that will likely be a toolkit like GeoExt that is geared towards making custom mobile applications.  These devices will not be able to run our server software, but we'll leverage html5 local storage and build in syncing smarts so that it can also function if there isn't a cell phone signal.  We'll also integrate with the GPS and enable editing and merging with conflict resolution when back online.  

The advances in offline environments should also dovetail with general speed in connected environments, adding smarts for moving data around, so that it is close to the end user.  Geospatial information can be huge, so we want to have it be in the right places when people need it.  But also to be smart about when to move the process to the data, and just supply the result to another location.

* GeoWebCache truncation based on transactions, georss feeds, active notification / webhooks, style changes, etc.

* GeoWebCache LFU and LRU cache, with statistic-based seeding, both of existing datasets that change and new data that might be added.

* Browser coordination of notifications and tile truncation, to automatically change data as it is edited, possibly with comet or hummingbird, or some other active client push, for real-time editing and collaboration

* Implementation and contribution to geospatial synchronization and notification standards, especially for vector data.  This is in many ways a subset of geospatially collaboration topics, but should aim for wider standard-based collaboration, to be able to sync with any data source, and have efficient transfer of differences.

* Mobile vector and raster caching, likely using HTML5 mobile storage standards.

* iPhone and Android javascript toolkits, improving the openlayers core for touch events, and making reusable GUI components like GeoExt does for standard web apps.

* Automatic federation and synchronization of data, based on usage and location.  Should be useful for even fully connected nodes, as geospatial data can get huge, so it should anticipate where it may need to be for analysis and processing.

* Methods for moving physical media and having it sync seamlessly with updates and merging/conflict resolution.


Mashup Creation
~~~~~~~~~~~~~~~

It should be easy for any user to create a 'mash-up', combining data from different sources, styling it to show what they want, and possibly annotating or editing the source data.  For people coming from a GIS background this is just basic GIS.  But in a web environment we can make the whole process social, persisting all the maps that everyone makes.  We call these mash-ups because they are just like the types of map mashups that take a programmer who knows javascript.  They should become accessible to everyone, to manipulate geospatial information and then by default persist the results for all to see.  With advanced permissioning to make it private if they just want to share with a small group or to keep it private while working on it.  And each mashup should be able to be copied, to see the 'source' of the layers and styles and change them to be another mashup.  Ideally we keep track of the provenance of who made what changes when.

To get there we need better through the web styling.  Styler is a decent start, but there's a whole lot more functionality that could be added to get to the level of a standard GIS.  And we should aim to exceed that level of usability, so that any normal web user would find it intuitive to take someone else's mashup and make it their own.  We also need annotation and editing, for cases when data needs to be tweaked.  And we ideally also need wizards for application creation, so anyone can set not only the layers but also the tools they want to expose to others.  Eventually those tools should incorporate geospatial processing (link to next section).  

Users who want to take mashups further should be able to figure out what's going on from the mashup itself, and build it up in to a more complex application.  So turn it from a simple display of data to an application that others can use.  This might include adding more tools that lets other users add layers, edit, export or analyze data.  This will obviously start to get in to programming, but even there it should be targeted at programers who don't already 'know' geospatial, who instead have a problem that they want to solve and can quickly learn how to tap in to the power of geospatial.

* More options in Styler, including `better symbolizers <http://projects.opengeo.org/styler/wiki/Symbolizers>`_, `thematic mapping <http://projects.opengeo.org/styler/wiki/StyleQuantities>`_, `Unique Values <http://projects.opengeo.org/styler/wiki/StyleCategories>`_, `copy and paste <http://img.skitch.com/20090217-b99x3j9a3ex9g5gayubqja46dt.png>`_, and more labeling options

* An `image manager <http://projects.opengeo.org/styler/wiki/ImageManager>`_ that lets people upload individual images and .ttf font symbol sets.

* Integration of `CSS Styling <http://docs.geoserver.org/latest/en/user/community/css/index.html>`_ in to Styler

* Standardization of CSS styling, ideally with a common implementation between geoserver css, cascadenik and gss.

* Wizards for creation of GXP applications, that can export new ones from an existing GeoExplorer map and also mash-up someone else's app.  

* Editing and annotation tools for mashups.  Ability to create new layers on the fly.

* GeoNode expansion of 'maps' to 'apps', supporting provenance and better export.

* Interaction Design work to make styling and application creation accessible to a much wider audience.   

* CSS styling language, that can be edited directly on the client side and reflected in the GUI, so designers can easily make styles in a way they're comfortable with.

* Great programming toolkits that combine processing and data to abstract the problems of geospatial from web programmers.

Geospatial Processing
~~~~~~~~~~~~~~~~~~~~~

The main technical challenge ahead with geospatial processing is not the actual algorithms, it's making them much more usable.  In the open source world there's long been powerful command line tools like GRASS.  And proprietary desktop GIS's have long focused on GUI's for advanced geospatial processing.  But they've never much focused on making this processing power accessible to everyone, as the price point is high enough to easily justify some training or at least time to become an 'expert'.  OpenGeo seeks to make that processing available to all, by exposing it all as web services, and making it quite easy to combine different processes to create custom web services.  It should be easy to script these together in a variety of programming languages, and eventually even a visual workbench type application to create processing chains from a GUI.

The other piece needed is to be able to pull these web services in to intuitive applications.  There is much interaction design work to be done to make geospatial processing much more 'easy', something that anyone can approach.  Part of this is putting it in the language of the people using it, but part is just making the whole experience of GIS more intuitive.  The web-based applications should be self documenting, and also should allow users to easily 'play' - experiment with various processes to figure out what they mean.  This is obviously a huge topic, as it gets in to the whole education of GIS.  But we believe the tools themselves should help people get better at geospatial processing, presenting easy options at the beginning, and nice tutorials and commands to expose more.  The whole process should also be inherently social, so you can always see what processes someone else did, and how they reached the result they got.  People can learn together, refining one another's processes.  Thus bringing even more of the open source vibe to mapping - it's not just open data collaboration, but open collaboration on analysis and processing.  The data generated from the results should always itself be available as web services and in the maps of other users.

Advanced users should be able to make an online application that others can use and play with to see various results.  So its far beyond a static map, and even beyond most of the online maps we see today, which are just moveable and zoomable flat maps.  It should be a map that one can interact with, each potentially creating thousands of different maps based on the variables input in to it.  There must be a shallow learning curve to create such an interactive map by selecting processes on data sets to expose to others.  And even more advanced users should be able to see how that interactive map was made and reuse the processes for their own map.  And very advanced users could script their own processes from existing ones, or even code a totally new geospatial process or model.  

Every process used in an application should by default be a web services that other applications can access.  These in turn should be able to be moved between services, as the nature of geospatial data is that its much harder to move the actual data than to move the process.  So processes should be open code that can easily be transferred between systems, exposing their source in the web service.  Web services would do the operation themselves if the data was close, and send the operation over the wire if the data was elsewhere.  In the long term the decision to move the process or the data should be something the user does not need to worry about, it just happens in the most efficient way.  Geoprocessing should also take advantage of cloud architectures, to be able to do complex operations very quickly by just adding more power, potentially taking advantage of idle systems or dynamic pricing like Amazon's EC2 Spot Instances.  

* Advance the new Web Processing Service (WPS) in GeoServer, particularly documentation, scalability, and ease to create new processes.

* Improve GeoScript, enhancing the existing language bindings and adding more, and make it easy to hook up to a GeoServer WPS, easily composing new processes from existing ones.

* Framework for easily sharing new geoscripts and coding them in to applications.

* Easy addition of WPS processes to GXP/GeoExplorer, to compose custom applications with a bit of javascript.  Need lots of great examples and documentation to help people make their own.

* Javascript wizard GUI's to create custom applications without having to write any code.

* Javascript visual workbench create new processes without having to write any code.

* Make it easy to clone custom app configurations, make them social by adding 'processes' and/or 'apps' to GeoNode as top level content that can be rated/tagged/commented/cloned.  

* Research and develop ways to pass processes to data instead of moving data around.

* Loads of interaction design and user testing to take geospatial processing out of the domain of 'experts' so that there's a nice shallow learning curve for anyone to naturally learn how to do advanced analysis.  

* Encourage an open ecosystem of geospatially related analysis and models.  There should be tens of thousands of analysis tools one can select from, including models that run for days on super computers on down to simple processes to get an answer.  

Spatializing non-spatial data
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Since there is much data out there that has an implicit though not explicit geospatial location we should make it easy to incorporate that data in to the geo world.  The main source of vector data is spreadsheets and basic access databases that have addresses, zip codes, census blocks, state names, or other boundaries.  All but addresses require an ability to 'join' the column listing the boundary or point location with a set of geometries.  Ideally there'd be a bunch of well known, possibly crowdsourced, boundaries that everyone could use.  And then people would also have the option to easily upload a spatial dataset to be joined against.  And there'd be a nice GUI to select what information to join.

For addresses we need a great geocoder, which is a problem that is far more than just software, but extends in to open data.  OpenAddress.org has made a good first pass at the effort, but we need much more data.  OpenStreetMap has some address information, and perhaps Microsoft and MapQuest can help now that they're going that route.  Ideally most any location search application would use an open address database and also have the built in facilities to correct and improve the addresses.  Past the data there should be great geocoding software that can plug in to the open address database, but also would be easily to write plugins that work with other datasets.  The final piece for a truly great geocoder is to crowdsource the corrections - misspellings and alternate names and the ways people refer to a place in shorthand.  One could imagine collecting a database of all searches, and hopefully also instrument the results of those searches.  And then researches could apply natural language processing and other advanced techniques to build an engine that is quite good at correcting.

For raster data there is scanned images and unrectified aerial images.  One should be able to upload either and then using online tools rectify them based on identifying points in common.  There are already several projects out there like this, but we'd like to bring that in to GeoNode so that more types of data can easily be uploaded.  Similar techniques and user interface likely could also be applied to vector data that's not located geospatially, like CAD drawings.  

* Open Source geocoder - there are already several, but not has great critical mass.  Ideally you want one that is pluggable and has lots of different backend implementations the way GeoTools or GDAL can read lots of different formats.

* Open Address database and tools - good possibilities with OSM and OpenAddress, but they need critical mass, and integrated tools that can be included in other web applications so users can correct data as they are using it.

* Web interface for 'joins' - need to make a great GUI to join data together, and to upload data to be joined.  There is some proprietary stuff that does this, but nothing great in the open source world.  On the backend it'd be a great improvement to have GeoServer able to handle joins on the fly and across data formats (though realistically if you're having people upload then you probably want to keep it in the same data source)

* GeoExt components for rectifying scanned images and photos.  And possibly also CAD files.


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


Other Tech to be built
~~~~~~~~~~~~~~~~~~~~~~

A smattering of other technology that doesn't fit in to any of the above use cases, but that we are interested in seeing open implementations of.

* Better real-time support - be able to handle real time vehicle locations and user check-ins.  Storing them in the backend and having nice tools to display the latest and dig back in to time.  And geoprocessing tools geared towards deep analysis of historical real-time data.

* 3-D - we should be able to take advantage of Oracle's 3D support, and push more 3D functionality in to PostGIS.  Ideally we also understand CAD and can produce the 3D open standards like Collada models.  We also hope to eventually do a 'spinny globe' in html5 with javascript, that can overlay data from our services and also show real 3d data.  This is not an area we know a whole lot about, but it's definitely of interest.

* Schemaless data support - we'd like to be able to leverage new data backends like CouchDB, Cassandra, Mongo, etc.  Some of these need to have spatial operations added to them, but for our stack all we really need is a spatial index, the rest we can handle.

* Continued support for new open standards.  WFS 2.0 and WCS 2.0 are probably the leading ones, but new versions of other specs and other open standards of things we do or want to do, like geosynchronization.

* Cloud scaling, including making on demand rendering and geoprocessing clusters, and being able to auto scale all tiers to deal with any load.

* Performance and scalability - all the software we build should work as well or better than everything else out there, and should be continually tested and refined.  




.. rubric:: Footnotes

.. [#f1] The earliest example of this for us was with GeoTools datastores.  Early on GeoServer made the choice to not try to build everything, but instead to work with a wider community on the GeoTools project to do all the core geospatial functionality like data access, reprojection, rendering, etc.  This initially was a whole lot of work, to get many people to agree on the ideal data structure that could handle all the diverse needs.  We took the time to participate in all the discussions, and then did the first datastore implementation, for PostGIS.  Within a year other people had contributed datastores for Oracle, ArcSDE and Shapefiles, probably the three most important formats to support.  Since we took the time to architect things right we didn't have to write any additional code to make those options for GeoServer, instantly increasing the potential user base.  

.. [#f2] GeoExt is a nice example of this.  At the time we helped start it many organizations had been working with OpenLayers and Ext.js, but all of us were just putting things together for our own use.  We teamed up with Camptocamp, who had even more experience than us with Ext.js, and took the time to do a new open source project.  We all realized that together we'd make better software if we collaborated on the pieces that we all had to do.

.. [#f3] The best example of this is probably GeoWebCache.  Where most every other server project at the time just wrote a cache integrated in their rendering pipeline we started an independent open source project that could cache any WMS.  We bundled it with GeoServer, so it would work with no installation.  But the way it works with GeoServer is by making standard WMS requests, which opens it up to be used with any WMS server.  People now use it in production with a variety of servers, including MapServer and ArcGIS Server.  As the project grew we also had it implement even more standards, including WMS-C, TMS, WMTS, Google Maps, Bing Maps, and KML Superoverlays.  It even implements WMS as an output, so that any standard WMS client can use it.  

.. [#f4] In GeoServer we've gotten pdf output by incorporating iText, awesome templating with Freemarker, charts on maps with jfreechart, svg output with batik, rest api with restlet, security with spring security, etc. etc.  With GeoExt we got a huge win by leveraging Ext.js.  The great thing is that good choices here lead to improvements in our software with very little additional work.  Ext.js gets more GUI controls with every release, and we just have to upgrade to take advantage of it.  We recently upgraded Spring Security and got OpenID and CAS support for our users.  

.. [#f5] Like http://grassrootsmapping.org

.. [#f6] Obviously this last thing is starting to happen with OpenStreetMap, especially now that Microsoft and MapQuest are both getting involved.

.. [#f7] It should be noted that this is a huge task, as right now there's not even a good way to find geospatial datasets, which is a much more constrained problem.  Finding individual data points is huge, and even Google's infrastructure has a tough time indexing and figuring out real relevance for big GIS datasets.

.. [#f8] See http://projects.opengeo.org/geoext/wiki/GeoEditor for our current designs, but these will evolve as people use it more and demand more.
