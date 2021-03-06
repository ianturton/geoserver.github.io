---
author: geoserver
comments: true
date: 2012-04-06 16:47:08+00:00
layout: post
link: http://blog.geoserver.org/2012/04/06/geoserver-2-2-beta/
slug: geoserver-2-2-beta
title: GeoServer 2.2-beta Released
wordpress_id: 1029
categories:
- Announcements
---

We're happy to announce to the beta release of GeoServer 2.2-beta and encourage you to [download](http://geoserver.org/display/GEOS/GeoServer+2.2-beta1) it, try out the great new features, and let us know if there are any bugs. Since this is the first beta release, we recommend against deploying it in a production environment without first undertaking extensive testing. That said, we’re hoping to move to release candidates soon, so any and all testing will help this process move along faster.

The release of a new major version update is a big deal (the [last one](http://blog.geoserver.org/2011/05/12/geoserver-2-1/) was 11 months ago) and, while you may have heard about some of the new features on the developer list, here they are all in one place:

**Referencing**



	
  * **NTv2 and NADCon Support** allows for datum transformations with cm level precision (instead of the usual 4m, when all goes well). Both will activate only if the grid files are present in the data dir, so by default the mere presence of the method is harmless, but generally speaking this is very good news for whoever needs to increase reprojection accuracy. Thanks to Andrea Aime and Oscar Fonts.**
**

	
  * A new **[reprojection console](http://osgeo-org.1560.n6.nabble.com/Little-reprojection-console-tt4631340.html) **allows users to make sure the transformations are actually using the grids by picking two coordinate systems and transforming a single point back and forth. Thanks Andrea.

	
  * Better support for un-referenced data with the new **[EPSG:40400](http://docs.geotools.org/latest/userguide/library/referencing/crs.html)** code that identifies a coordinate system made up of a generic 2D Cartesian plane.


**Data access**



	
  * **[Database-level security](http://geo-solutions.blogspot.com/2012/01/developers-corner-introducing-database.html) **implements the ability to use DBMS session startup and teardown scripts to alter user access the database during a specific request while falling back on connection pooling when the request is complete. Thanks to [Astrium GEO-Information Services](http://www.astrium-geo.com/) for sponsoring GeoSolutions to make this improvement.

	
  * **[Sorting and paging](http://geo-solutions.blogspot.com/2011/12/wfs-for-masses-adding-support-for.html)** is now available in all WFS versions (in 1.0 and 1.1 as a vendor param) via the sortBy and startIndex/maxFeature parameters. Thanks to Justin Deoliveira and Andrea.

	
  * A new experimental **OGR data store** provides access to  a rich set of readable formats without needing special bridge libraries.

	
  * The **[image collection](http://docs.geotools.org/latest/userguide/library/coverage/image-collection.html)** coverage store allows users to serve un-referenced data through WMS using image/pixel space as the coordinate system. Thanks to [SFMTA](http://www.sfmta.com) for sponsoring OpenGeo to complete this work.


**Security**



	
  * A major retrofit of the GeoServer **[security subsystem](http://docs.geoserver.org/latest/en/user/security/index.html)** adding support for a number of new authentication mechanisms including **[LDAP](http://docs.geoserver.org/latest/en/user/security/tutorials/ldap/index.html)**, **[digest](http://docs.geoserver.org/latest/en/user/security/tutorials/digest/index.html)** and **[X.509](http://docs.geoserver.org/latest/en/user/security/tutorials/cert/index.html)** certificate authentication, and more. These improvements also includes the addition of **[user groups](http://docs.geoserver.org/latest/en/user/security/usergrouprole/usergroups.html)**. This is a continuation of work started by Christian Mueller as a Google Summer of Code project;  thanks to [NOAA](http://www.noaa.gov/) for sponsoring OpenGeo to help Christian and Justin bring it to completion.


**Web Feature Source (WFS)**



	
  * Support for **[WFS 2.0](http://geoserver.org/display/GEOS/GSIP+61+-+WFS+2.0)** adds some interesting new capabilities to the WFS protocol such as paging, stored queries, and extended operators. Thanks to [IGN France](http://www.ign.fr/) for sponsoring OpenGeo to make this improvement.


**Web Map Service (WMS)**



	
  * Support for additional dimensions brings [**time and elevation**](http://geo-solutions.blogspot.com/2011/06/time-and-elevation-support-in-geoserver.html) support to both vector and raster data. And, with support for time, comes support for **[animation in WMS](http://docs.geoserver.org/stable/en/user/tutorials/animreflector.html)**. Thanks to Andrea on both counts.

	
  * **[Rendering transformations](http://docs.codehaus.org/display/GEOTOOLS/Rendering+transformations) **provide a bridge between WPS and WMS and allow for very powerful visualization capabilities for processing through normal WMS. Thanks again, Andrea.


**Web Processing Service (WPS)**



	
  * New WPS features include support for asynchronous process execution and a variety of new processes.


**Virtual Services**



	
  * [Virtual services](http://docs.geoserver.org/latest/en/user/services/virtual-services.html) allow GeoServer to support the notion of multitenancy, enabling a single GeoServer instance to publish multiple service endpoints. Thanks to NOAA for sponsoring OpenGeo to complete this improvement and a special thanks to Micah Wengren of NOAA for his leadership on the project.

	
  * **[Workspace local settings](http://geoserver.org/display/GEOS/GSIP+67+-+Workspace+Local+Settings)** allow for specifying service settings such as contact information,  proxy settings, and output format settings on a per workspace basis.

	
  * **[Styles and layer groups](http://geoserver.org/display/GEOS/GSIP+73+-+Workspace+Local+Styles+and+Layer+Groups)** can also now be defined on a per workspace basis.


**GeoWebCache**



	
  * A **GeoWebCache configuration GUI** is now available directly from within the GeoServer web admin interface, including: the ability to define new grid sets, specify which layers to cache, seed or truncate the cache, and more. Big thanks to Gabriel and the GeoWebCache team for furthering improving integration between GeoWebCache in GeoServer.


**Wow! **And that isn't even everything, many [other](http://jira.codehaus.org/secure/ReleaseNote.jspa?projectId=10311&version=18401) bug fixes and improvements have made it into the 2.2 series as well.

Everyone who uses GeoServer should have at least one or two items in the above list to be excited about. [Download GeoServer 2.2-beta](http://geoserver.org/display/GEOS/GeoServer+2.2-beta1), try it out, and please provide feedback and report any issues on the [GeoServer mailing list](http://geoserver.org/display/GEOS/Mailing+Lists).  As with any beta version, _be sure to backup your data directory before upgrading_.

**FOSS4G North America**

Be sure to catch Andrea and Justin's [State of GeoServer](http://foss4g-na.org/schedule/the-state-of-geoserver/) and [What's new in GeoServer 2.2](http://foss4g-na.org/schedule/whats-new-in-geoserver-2-0/) presentations at [FOSS4G North America](http://foss4g-na.org/) to learn more about the exciting new features in GeoServer 2.1 and GeoServer 2.2. The conference takes place in Washington DC from April 10 through April 12 and on-site registration is available on a first come first serve basis for $350.

**Thanks again for using GeoServer!**

**[Download GeoServer 2.2-beta](http://geoserver.org/display/GEOS/GeoServer+2.2-beta1)**
