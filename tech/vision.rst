.. _vision:

Vision 
------
OpenGeo's technical vision is a flexible, powerful set of geospatial libraries and projects that can help any existing or new geospatial information be shared and improved.  
To the end user, any device (mobile, desktop, offline) should be able to access and contribute to any data for any area (subject to appropriate permissions).  
OpenGeo software will run the gamut from powering complete infrastructures to providing key integration points for existing systems to share in an open way.  
It should scale up to massive cloud infrastructures and down to small, offline mobile devices.  
The software should be a joy to code against, with great documentation for intuitive and powerful APIs.  
And it should play a key role in an emergent infrastructure - the geospatial web, which makes possible end user functionality that no one company or government could provide alone.

Some things an end user should be able to do:

* Browse all historical and current aerial imagery for the area they're interested in.  
A base of open information, an option to add in imagery from Google or Microsoft if the device meets their terms, a way to login and get additional data they have access to, the ability to purchase the latest imagery (or even task a satellite, a plane or a drone), and a method for flying a balloon to gather their own aerial photos [#f5]_.

* Join, create or even fork any collaborative data effort.  
If you can't find a good map of surf spots in Argentina you should be able to start it and let others contribute.  
If you notice that a meter on the city's parking map is in the wrong place you should be able to report it to them and have it go through their QA process and get incorporated.  
And we should all be naturally contributing to an open base map instead of navtech, google, teleatlas, governments and open street map all gathering and refining the same data [#f6]_.  
One should also be able to fork an existing data effort, and have one's own distributed version control system that can have one's own QA and syncing process with another data maintenance effort.  
Collaborating geospatially should be even easier than it is to collaborate on open source software, since map making is something that is accessible to everyone.  

* Work in environments with low, occasional, or no internet connectivity.  
Should be able to load up data on a mobile device and go out in the field, edit and resolve conflicts when back online.  
Places without internet can still receive hard drives of disks, and mail back data they gather.  
And when internet cuts out or there is a small pipe we should have methods to make data transfer seamless with smart caching throughout.  

* Make their own mashups.  
A user should be able to put together various datasets, style them the way they want, and optionally add some interesting processes for others to do.  
Should be able to grab any data layers and tweak them to be the way they want, with advanced cartography and editing tools that are intuitive and powerful.  
And then select from many processes to let others use.  
The resulting mashup application, should be easily shared on the web, and it source can optionally be shared with others to tweak it further.

* Apply geospatial processing in intuitive ways, taking existing data sets and then creating new data by applying interesting analysis, easily sharing the results.  
Right now geospatial processing is more the domain of 'experts' who can afford expensive tools and/or gain significant experience in figuring it all out.  
It should be easy for experts to design custom applications that expose advanced geoprocessing to newer users, by translating it to their domain. 
And there should be a nice shallow learning curve for those new users to explore more and more processing power that is relevant to them.  
All this should be available for free and completely on the web.  

* Easily transform data that is not immediately spatial in to a map, where it can be overlaid and processed with other geospatial data sets.  
So taking excel spreadsheets and access databases, geocoding or joining with boundary files, and making that in to spatial data that is shared in many formats.  
And uploading scanned maps and rectifying it online.  And taking unstructured data and deducing what is geospatial about it.

* Search for relevant local datasets and individual vector data points.  
So if a user has a sudden interest in cardinals they can search by their house and get all the latest spottings by birdwatchers and scientists in diverse data sets.  
Or if they learn about a chemical that causes cancer they can find readings done by EPA or citizen scientists.  
From the data points they could pull the full dataset and geoprocess it with other relevant demographic information to do analysis, or spot trends and problems [#f7]_.


.. rubric:: Footnotes

.. [#f5] Like http://grassrootsmapping.org

.. [#f6] Obviously this last thing is starting to happen with OpenStreetMap, especially now that Microsoft and MapQuest are both getting involved.

.. [#f7] It should be noted that this is a huge task, as right now there's not even a good way to find geospatial datasets, which is a much more constrained problem.  Finding individual data points is huge, and even Google's infrastructure has a tough time indexing and figuring out real relevance for big GIS datasets.