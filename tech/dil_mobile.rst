.. _dil_mobile:

Disconnected/Intermittent/Low-bandwidth (DIL) and mobile environments
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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

