.. _imagery:

Browse all imagery 
~~~~~~~~~~~~~~~~~~

The center of this problem needs to be Open Aerial Map, which has struggled to get off the ground for a variety of reasons.  
In a nutshell it's a solid base infrastructure where anyone can upload the latest imagery under a public license.  
It should eventually be its own foundation, that can raise fund and in-kind donations for a massive server infrastructure.  
Ideally this is a distributed infrastructure, so that it can scale to the level needed for all historical.  
It should also provide a framework for other services to share imagery in a known protocol, optionally with security restrictions.  
Technically a really intuitive web-based front end that lets one browse all the imagery that one has access to will likely go a long ways.  
It should also be able clip/ship/zip on the pieces one has the right permissions to, so one could do further analysis.  
On the server side it should be super easy to upload new imagery (or ship a drive to a known location), and also to point at an existing file system (or network of file systems), and automatically crawl it and extract all the needed metadata.  
Covered in this would also be when raw imagery hits the file system, being able to rectify it and process it according to predefined chains, making it automatically available as WMS, WCS and tiles.  
All data added should also get search interfaces, crawled by Google, available as CSW, and with both extracted and user contributed metadata.  
Should also be able to handle video, from drones and new satellites, making it searchable and providing nice animations.

* GeoExt/OpenLayers Time interface, with lots of good interaction design to handle diverse datasets and their appropriate metadata in an intuitive manner.  Should also be able to log in to remote servers where one has more permissions, and also upload data.

* Network crawler to find imagery and register it.

* GeoServer/GeoNode integration with OSSIM / OMAR plus likely GeoSolution's GeoBatch (or some equivalent), to pull down and process latest imagery.

* GeoExt interfaces to do OSSIM image processing on the web (likely leveraging OMAR)

* Cloud scaling of imagery processing and storage.

* Handling of video imagery formats.

* Protocols for caching and distributing imagery between different physical servers, for fast access and also offline capabilities.  Perhaps investigate p2p-inspired solutions, though something like DNS, centralized but able to failover easily, is more tractable.

* Helping take grassrootsmapping.org further, hooking it up to a global infrastructure, and making it accessible to anyone.  

* Hardware and hosting infrastructure for the core Open Aerial Map imagery.  Likely could limit it to just the latest imagery, and have others handle the historical stuff with good open protocols.  But there should be some dedicated central infrastructure with real resources behind it to ensure that it'll always be available.