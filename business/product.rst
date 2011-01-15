.. _product:

Product
-------

This section discusses OpenGeo's product approach and future directions

Product focus
`````````````

The focus of OpenGeo's product is to make it as easy as possibly for people to share and collaborate geospatially.  We see 'product' as a layer of value on top of our individual open source projects.  The product is more than just software, it includes all the pieces around it that turn it from a bunch of 1's and 0's in to something that solves a problem.  OpenGeo currently only has one product - the OpenGeo Suite Enterprise Edition.  

OpenGeo's goal for each open source project is to make it as flexible and powerful as possible.  The point of the Suite is to make that power and flexibility available to a much wider audience.  It adds installers that bundle all the needed dependencies and extra options, pulls the documentation together in one place, and adds a recipe book to help educate.  It also includes several end user applications based on GeoExt, including GeoExplorer, Styler and GeoEditor.  These are examples of what can be done, and also provide immediate out of the box functionality.  The Suite comes already optimized and integrated, but is also distributed as individual components that can be easily adapted for existing environments.  The Enterprise Edition includes unlimited bug fixes and advice, and future versions will come with a few more extras.  All but the Basic level also include training, as well as discounts on consulting work.

The general future product focus is to be the best platform for building geospatial applications.  It should be as easy as possible to get set up, include the best support on the market, and provide the most flexible tools to easily build anything that leverages geospatial information.   It should naturally educate users to be able to go from no knowledge to making powerful applications (we've still got quite a ways to go on this last one).  

It should also be a platform that enables partners and clients to build their own products.  This includes not just the software, but being able to offer unlimited support on products built on the OpenGeo Suite.  This will be accomplished with business relationships that bundle the Enterprise Edition support and extras with products built on top of it.  


Our Open-Core approach
``````````````````````

There is much written about the Open-Core model [#f1]_.  There has been backlash against it, as some companies using the term lack a real commitment to open source.  Since OpenGeo's reason for existence is to further the open source software we naturally put making software ahead of huge revenue to make investors happy.  But we draw inspiration from good Open-Core companies.  The essence is 'give me a cookie' [#f2]_ - include _something_ in the Enterprise package that you can't get in the normal package that you can sell a CTO/CIO on.  

At OpenGeo we discussed internally at length if we felt ok about having code that we didn't release as open source.  Everyone agreed that it's worth it if a very small piece of proprietary code can help make a business model that funds us to spend the vast majority of our time on open source code.  But we want to do that as little as possible, and that we prefer not having to do anything proprietary.  

The first year of the OpenGeo Suite had a Community Edition and Enterprise Edition with the exact same code base.  The Enterprise Edition did get additional testing and QA, but had no extra code.  It included unlimited support, access to more granular upgrade packages, and larger levels bundled in training.  We sold a number of them, but not enough to avoid tweaking the model.  For the 2.4 release we likely will have two 'extras' in the Enterprise Edition.  The first is bundling `GeoCat Bridge <http://www.geocat.net/bridge>`_ software, which is a plugin to ArcGIS Desktop tools to publish to the OpenGeo Suite.  The second is extra monitoring functionality.  The base monitoring API is a community module in GeoServer, but we include additional GUI tools in the admin panel that build on top of it.  Our philosophy on choosing these is that are quite far from the core.  The first is only useful to ArcGIS desktop users (which generally are not the same people standing up the server software and building applications), and the second is mostly useful to systems administrators.  We follow Matt Asay's advice [#f3]_, which is to sell to IT Operations - who will spend money to save time.  

So we are now experimenting with making a few pieces more private.  One thing we may try in the future is keeping things private for an explicit amount of time, and then releasing as open source.  We've considered that for things like WMS 1.3, which everyone wanted but no one would step up and fund (big props to the UK Ordnance Survey for finally doing that).  It's not something we could in good conscious keep out of the open source core, but keeping it private for a time could provide a way to spread the funding for it to paying Enterprise clients.  We also favor extras that aren't code.  One leading idea is a subscription service to OpenStreetMap updates, where we automatically keep a database and custom tiles in sync.  Enterprise clients would get updates, everyone else would just have tools to get it once and do updates on their own.  Other ideas include nicer automatic upgrades and networked monitoring tools.  


Next Product Steps
``````````````````

As we expand our revenue from Enterprise contracts we will be able to have more a more concrete roadmap for each OpenGeo Suite release and our future products.  In the short term, however, the roadmap is a complex interchange of open source contributions, funded client work, dedicated product time, and aligning customer needs with our roadmap.  But we have little doubt that we will make progress on the following major areas in the next year.

Cloud
~~~~~

Cloud aligns with our goal to make it as easy as possible to add geospatial capabilities to web applications.  Though we've made great progress in easing the installation of the OpenGeo Suite it still requires hardware and a systems administrator, as well as know how on optimizing and scaling it.  Our goal with the cloud is to completely abstract the whole problem of running the infrastructure.  

The OpenGeo Suite already has cloud options, with our partners at Skygone, and as AMI's on Amazon.  Though these match the offerings of our competitors on the cloud we plan to go much further.  The main piece we want to tackle is auto-scaling, firing up new instances on demand.  This is the true advantage of the cloud, to be able to handle any load.  We see interesting use cases like massive tile generation, firing up 100+ machines to cut the process from weeks to hours.  

Our goal is to be able to offer instance hour pricing for fully supported software, that includes automatic upgrades, security fixes, monitoring and scaling.  It should also be very easy to deploy applications developed elsewhere on to the cloud, with test and development instances before going to production.  We like the cloud a lot as a product direction, since it provides extra value to clients.  The combination of supported open source software and cloud computing will allow us to offer incredible capabilities in one package at a great price.

Easy Custom Applications
~~~~~~~~~~~~~~~~~~~~~~~~

Though the projects we work on provide an extreme amount of flexibility there is still a hole in easily composing them in to applications.  A decent developer has no problem, but our goal is to make it easier for technically inclined users to make custom applications.  The center of this is our GeoExplorer application and the GXP framework.  Past advanced Editing and Styling this year we will start to incorporate geospatial processing.  The standards-based Web Processing Service (WPS) is now a part of GeoServer.  We hope to advance `GeoScript <http://www.geoscript.org>`_ and build up easy ways to compose custom processes and incorporate them in to GXP-based applications.  Also needed is some more 'wizard' type functionality to easily compose applications through the GUI itself.  

We believe that advances in this will open up the power of geospatial to a much wider audience.  People who are technically inclined and understand maps, but who haven't had GIS training.  Instead of a model of training them in desktop tools when they will likely do the same 5 operations again and again we hope to make it easier to just design and build a geospatial powered application that speaks in the language of their domain.  

Data gathering and collaboration
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Our mission driven goal is to move beyond just sharing data, to helping enable people to build and maintain geospatial information.  We will build upon the existing editing capabilities, pushing further in the direction of versioning and geosynchronization, to enable robust infrastructures for editing.  We also seek to advance 'official' workflows in conjunction with crowdsourcing initiatives, to help risk averse organizations be able to leverage the power of the crowd yet also maintain their required quality.  We see initiatives like OpenStreetMap as a great step in the right direction, but want to enable that type of collaboration for smaller communities on all types of datasets, not just street maps.  The core software should be flexible for lots of different workflows, licensing schemes, and communities.  It should offer a step forward for all geospatial collaboration, and be compatible with existing tools while also pushing the edge on html5 compliant approaches.  

Mobile
~~~~~~

Key to data collaboration and custom apps will be mobile capabilities.  We've prototyped several applications, and plan to push things much further as mobile platforms are clearly the future.  We hope to enable not just the viewing of geospatial information but mobile editing, for applications like asset management, surveys, and reporting.  Our initial approach will be to push our existing javascript tools as far as possible, leveraging mobile web-browsers, but also wrapping them in toolkits to make them more compatible with mobile environments.  This allows us to share and reuse much more code.

.. rubric:: Footnotes

.. [#f1] 
http://alampitt.typepad.com/lampitt_or_leave_it/2008/08/open-core-licen.html
http://blogs.the451group.com/opensource/2008/09/01/andrew-lampitt-defines-open-core-licensing/
http://blogs.gartner.com/brian_prentice/2010/03/31/open-core-the-emperors-new-clothes/

.. [#f2]
http://kirkwylie.blogspot.com/2008/07/open-source-business-strategies.html

.. [#f3]
http://news.cnet.com/8301-13505_3-10350956-16.html