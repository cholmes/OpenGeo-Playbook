.. _mashup:

Mashup Creation
~~~~~~~~~~~~~~~

It should be easy for any user to create a 'mash-up', combining data from different sources, styling it to show what they want, and possibly annotating or editing the source data.  
For people coming from a GIS background this is just basic GIS.  
But in a web environment we can make the whole process social, persisting all the maps that everyone makes.  
We call these mash-ups because they are just like the types of map mashups that take a programmer who knows javascript.  
They should become accessible to everyone, to manipulate geospatial information and then by default persist the results for all to see.  
With advanced permissioning to make it private if they just want to share with a small group or to keep it private while working on it.  
And each mashup should be able to be copied, to see the 'source' of the layers and styles and change them to be another mashup.  
Ideally we keep track of the provenance of who made what changes when.

To get there we need better through the web styling.  
Styler is a decent start, but there's a whole lot more functionality that could be added to get to the level of a standard GIS.  
And we should aim to exceed that level of usability, so that any normal web user would find it intuitive to take someone else's mashup and make it their own.  
We also need annotation and editing, for cases when data needs to be tweaked.  
And we ideally also need wizards for application creation, so anyone can set not only the layers but also the tools they want to expose to others.  
Eventually those tools should incorporate geospatial processing (link to next section).  

Users who want to take mashups further should be able to figure out what's going on from the mashup itself, and build it up in to a more complex application.  
So turn it from a simple display of data to an application that others can use.  
This might include adding more tools that lets other users add layers, edit, export or analyze data.  
This will obviously start to get in to programming, but even there it should be targeted at programers who don't already 'know' geospatial, who instead have a problem that they want to solve and can quickly learn how to tap in to the power of geospatial.

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
