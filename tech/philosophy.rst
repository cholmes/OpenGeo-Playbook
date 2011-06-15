.. _philosophy:


Philosophy
----------

Central to OpenGeo's technical philosophy is open source, not just the license but in the strength of real communities.  
Diverse contributors working towards their own purpose but taking the time to collaborate build better software than any group focused on a narrow problem.  
We want a diverse ecosystem around the core projects we work on, so that the technology will live on even if OpenGeo as an organization dies for any reason.  

The practical technical implications of that is that we architect small, flexible pieces, and work to push code we write down to the lowest library levels.  
Those libraries are already used by many developers, and our contributions make those libraries even better and more flexible, building a virtuous circle of more contributors using it for more diverse purposes.  
Though initially it is more work to take the time to do things right, we've seen time and again that the extra work pays off [#f1]_.  
So when we start a new project like GeoNode we take the time to improve all the underlying API's to meet our needs, even though it would be far more efficient in the short term to just code what we need.  
We'll also take the time to start new open source projects for functionality that others can use, instead of just making them work with our needs [#f2]_.

So the core of philosophy is to not take shortcuts, and to seize any chance to improve the underlying libraries.  
But we also are not continually redoing things in the abstract, we wait till there is a clear advantage to refactoring things in a new way, where it will help our clients and users.  

We also rely heavily on open standards, but are not slaves to them.  
Open Standards have been a huge advantage to getting acceptance for our open source software, and we use them as the first choice for how our software stack is architected [#f3]_.  
The primary pathway for how each piece interacts with another is through an open standard, so that we can easily swap out one piece for another.  
But we will often extend standards to get 'more' out of them, be that more performance, more options, or more flexibility.  
We also always implement leading ad hoc standards, things that don't go through a real standards process but are widely used.  
If a standard does not exist for something we do want to do we'll also try to find other software that does the same thing and follow and collaborate with them, to hopefully help lead to a good open standard in the future.

The other core philosophy is to leverage the work of others as much as possible.  
We don't want to be writing new libraries for functionality that other open source projects handle, and if it doesn't quite handle all our needs we'll try to contribute to them to make it work for us.  
This has been a huge advantage, as we've been able to add huge amounts of functionality by just making an existing library work for us [#f4]_.  


.. rubric:: Footnotes

.. [#f1] The earliest example of this for us was with GeoTools datastores.  
Early on GeoServer made the choice to not try to build everything, but instead to work with a wider community on the GeoTools project to do all the core geospatial functionality like data access, reprojection, rendering, etc.  
This initially was a whole lot of work, to get many people to agree on the ideal data structure that could handle all the diverse needs.  
We took the time to participate in all the discussions, and then did the first datastore implementation, for PostGIS.  
Within a year other people had contributed datastores for Oracle, ArcSDE and Shapefiles, probably the three most important formats to support.  
Since we took the time to architect things right we didn't have to write any additional code to make those options for GeoServer, instantly increasing the potential user base.  

.. [#f2] GeoExt is a nice example of this.  
At the time we helped start it many organizations had been working with OpenLayers and Ext.js, but all of us were just putting things together for our own use.  
We teamed up with Camptocamp, who had even more experience than us with Ext.js, and took the time to do a new open source project.  
We all realized that together we'd make better software if we collaborated on the pieces that we all had to do.

.. [#f3] The best example of this is probably GeoWebCache.  
Where most every other server project at the time just wrote a cache integrated in their rendering pipeline we started an independent open source project that could cache any WMS.  
We bundled it with GeoServer, so it would work with no installation.  
But the way it works with GeoServer is by making standard WMS requests, which opens it up to be used with any WMS server.  
People now use it in production with a variety of servers, including MapServer and ArcGIS Server.  
As the project grew we also had it implement even more standards, including WMS-C, TMS, WMTS, Google Maps, Bing Maps, and KML Superoverlays.  
It even implements WMS as an output, so that any standard WMS client can use it.  

.. [#f4] In GeoServer we've gotten pdf output by incorporating iText, awesome templating with Freemarker, charts on maps with jfreechart, svg output with batik, rest api with restlet, security with spring security, etc. etc.  
With GeoExt we got a huge win by leveraging Ext.js.  
The great thing is that good choices here lead to improvements in our software with very little additional work.  
Ext.js gets more GUI controls with every release, and we just have to upgrade to take advantage of it.  
We recently upgraded Spring Security and got OpenID and CAS support for our users.  
