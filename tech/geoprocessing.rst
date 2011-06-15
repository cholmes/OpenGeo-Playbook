.. _geoprocessing:


Geospatial Processing
~~~~~~~~~~~~~~~~~~~~~

The main technical challenge ahead with geospatial processing is not the actual algorithms, it's making them much more usable.  
In the open source world there's long been powerful command line tools like GRASS.  
And proprietary desktop GIS's have long focused on GUI's for advanced geospatial processing.  
But they've never much focused on making this processing power accessible to everyone, as the price point is high enough to easily justify some training or at least time to become an 'expert'.  
OpenGeo seeks to make that processing available to all, by exposing it all as web services, and making it quite easy to combine different processes to create custom web services.  
It should be easy to script these together in a variety of programming languages, and eventually even a visual workbench type application to create processing chains from a GUI.

The other piece needed is to be able to pull these web services in to intuitive applications.  
There is much interaction design work to be done to make geospatial processing much more 'easy', something that anyone can approach.  
Part of this is putting it in the language of the people using it, but part is just making the whole experience of GIS more intuitive.  
The web-based applications should be self documenting, and also should allow users to easily 'play' - experiment with various processes to figure out what they mean.  
This is obviously a huge topic, as it gets in to the whole education of GIS.  
But we believe the tools themselves should help people get better at geospatial processing, presenting easy options at the beginning, and nice tutorials and commands to expose more.  
The whole process should also be inherently social, so you can always see what processes someone else did, and how they reached the result they got.  
People can learn together, refining one another's processes.  
Thus bringing even more of the open source vibe to mapping - it's not just open data collaboration, but open collaboration on analysis and processing.  
The data generated from the results should always itself be available as web services and in the maps of other users.

Advanced users should be able to make an online application that others can use and play with to see various results.  
So its far beyond a static map, and even beyond most of the online maps we see today, which are just moveable and zoomable flat maps.  
It should be a map that one can interact with, each potentially creating thousands of different maps based on the variables input in to it.  
There must be a shallow learning curve to create such an interactive map by selecting processes on data sets to expose to others.  
And even more advanced users should be able to see how that interactive map was made and reuse the processes for their own map.  
And very advanced users could script their own processes from existing ones, or even code a totally new geospatial process or model.  

Every process used in an application should by default be a web services that other applications can access.  
These in turn should be able to be moved between services, as the nature of geospatial data is that its much harder to move the actual data than to move the process.  
So processes should be open code that can easily be transferred between systems, exposing their source in the web service.  
Web services would do the operation themselves if the data was close, and send the operation over the wire if the data was elsewhere.  
In the long term the decision to move the process or the data should be something the user does not need to worry about, it just happens in the most efficient way.  
Geoprocessing should also take advantage of cloud architectures, to be able to do complex operations very quickly by just adding more power, potentially taking advantage of idle systems or dynamic pricing like Amazon's EC2 Spot Instances.  

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
