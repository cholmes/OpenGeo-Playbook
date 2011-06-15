.. _industry

Industry 
========

The Geospatial Software Industry 
--------------------------------

The geospatial software industry is (some stats and stuff).  It has seen a significant shakeup in the past few years, with the rise of Google Maps and Google Earth, setting off geospatial as a vitally important piece in the battle for internet dominance between the major technology companies of our day.  
Google and Microsoft lead, with Apple likely making a play soon, plus Nokia, AOL and Yahoo all participating in some way.  
The industry has traditionally been dominated by software companies building specialized desktop products aimed at experts.  
But the rise of internet has them all making server products to defend their previous dominance.  

The major technology companies are all primarily focused on geospatial as a platform for the next generation of computing, as most all mobile devices are location aware.  
The revenue stream that powers them is primarily location-based advertising, and all see potential for even more in the future.  
For software developers they wrap up the data and software in to one package, behind a nice API.  
But their primary user is consumers, and what they care about is their platform being widely used.  
So they tend to make their API's freely available to anyone who will use it on a public site.  
The thing that is most important to them is that their logo gets out there and they are used as the default mapping platform by consumers, so their software tools are primarily aimed at developers who want to make consumer focused online applications.  
Both Microsoft and Google have complete enough platforms though that they can be used a replacement for some traditional GIS functionality, and both have started to sell their platforms directly to organizations who can't make their applications public.  

The only traditional GIS player who is still seriously in the geospatial software game is ESRI, as MapInfo and Intergraph have moved their focus to 'solutions' focused on particular industries, while also doing more consulting.  
ESRI has been starting to follow them building up a bigger consulting arm.  
ESRI has been forced to focus on its strengths like geospatial processing and 'real' GIS analysis.  
Google and Microsoft basically cut out the bottom end of the market for them, as many people would by ESRI products when all they really needed to do was some basic visualization of their geospatial data.  
Google and Microsoft allowed developers to do this for 'less than free'[#f1]_, supplying not only the software but super valuable data that they previously would have had to pay substantially for.  
The only caveat was that they had to make the resulting map publicly accessible, though soon one could alternatively just pay a fee.

The other major trend in the geospatial software industry has been the rise of open source.  
Though there is as of yet no companies making major revenues like a redhat, mysql or jboss the rising popularity of the software has made for tougher competition.  
Since many geospatial deployments take considerable customization a number of consultants who have traditionally built their solutions on proprietary software have made the switch to open source.  
If they are trusted by the client and the open source software is close enough then it allows them to increase their bottom line.  
The open source geospatial world got a boost in credibility in 2006 with Autodesk making a foray in to the space by releasing their rewrite of MapGuide as open source and leading the formation of the Open Source Geospatial Foundation.  

Geospatial open source software has primarily made an impact on server and web-based software, where it is completely competitive if not better than most proprietary software.  
The traditional GIS players however have maintained their dominance on the desktop, where there is still a lot of catching up to do.  
Recently, however, Quantum GIS has captured considerable momentum, so may take some of the lower end of the market.  
Many smaller companies have made good business building open source software (DMSolutions, Refractions, Camptocamp, Orkney, WhereGroup, Prodevelop, etc), but all have relied primarily on consulting revenue, using that to build up the projects.  
None have crossed the chasm to become a mainstream geospatial software company.  


OpenGeo's position in the geospatial industry
----------------------------------------------

OpenGeo is positioned in the gap between traditional GIS software and new internet mapping platforms.  
The technical approach has been to embrace both sides, focusing on open standards and also working well with both so as to slot in and bridge the gap.  
This can be done in a piecemeal fashion, using one or two of OpenGeo's core technology alongside an existing solution.  
Clients can move on to more OpenGeo software, but are also encouraged to stay with what is working if no new capabilities are needed.  
OpenGeo made two early bets - web-based and open source - which have both paid off.  
Both are at the center of major technological trends, and are only advancing more.

For users of mapping API's OpenGeo is a choice for users wanting more, or more control.  
The 'more' is the ability to connect to existing enterprise geodatabases, efficient handling of large amounts of data, geospatial operations, separation of styling from data, and GUI tools to build applications.  
These can all be used on top of an existing Google Maps or Bing Maps solutions, so users can keep their base layers while adding additional functionality more easily than coding it all themselves.  
The 'more control' comes in two forms.  
The first is that users can completely run their own infrastructure just like Google or Microsoft does, but using their own data, styling the maps as they want, and with total control over user interactions [#f2].  
The second is that by just using their tiles instead of their full API (using OpenLayers or GeoExt instead), users aren't locked in to the platform - they can switch between them or make their own tiles if the terms of service change.  

For users of GIS server software OpenGeo offers a more reliable and flexible product.  
Most of the core projects that power the OpenGeo Suite are over 5 years old, and have benefitted from the superior development process of open source.  
They have had many people using it in a huge variety of deployments, reporting bugs and improving it for many purposes.  
This has lead to a core that just works better in more situations, instead of focusing on 'new' features to convince people to pay for an upgrade.  
OpenGeo has been riding and contributing to this technology wave, refining the 'product' as a full solution bringing the diverse components together in to a full Suite.  
Adding support and training to the package positions it as a great alternative even for risk averse organizations who are initially intimidated by open source.  
The area of focus has been web-based geospatial applications, that can leverage the data of internet mapping API's, adding more powerful GIS functionality on top of it.  
OpenGeo has been pushing the edge of what is possible in the browser, doing editing (with snapping and splitting), map styling and soon geoprocessing  - all traditional desktop GIS strengths.  




The competition
---------------


.. rubric:: Footnotes

.. [#f1] http://abovethecrowd.com/2009/10/29/google-redefines-disruption-the-%E2%80%9Cless-than-free%E2%80%9D-business-model/ defines the great term.  The inspiration for the post was actually Google's turn by turn navigation and how it changes things for tomtom, nokia and garmin.  But the effect on geospatial software was similar, though not as major, with the Google Maps API bundling data for developers for free.  

.. [#f2] http://ride.trimet.org is a good example of this, the normal google map tiles are dominated by roads, but as a transit agency they wanted the focus to be more on transit, so they made the roads thinner with more subdued colors.  They further can use this map as a platform for a number of other internal applications, without having to pay any additional license fees.
