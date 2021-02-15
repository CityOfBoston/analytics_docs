# GIS

## Geospatial Analysis in Postgres

Our data warehouse is capable of running geospatial queries due to a [Postgres extension](employee-handbook/tools/databases.md#extensions) called [PostGIS](employee-handbook/tools/databases.md#postgis). It brings three things to PostgreSQL that are crucial to working with spatial data:

1. Support for spatial data types \(points, lines, polygons, rasters\)
2. Spatial functions that allow you to ask questions like _"what City Council District is this public bathroom in?"_ of your data in a SQL query
3. Spatial indexing so your spatial queries run quickly

{% hint style="info" %}
**Recommended:** [Why should you care about PostGIS? — A gentle introduction to spatial databases](https://medium.com/@tjukanov/why-should-you-care-about-postgis-a-gentle-introduction-to-spatial-databases-9eccd26bc42b)
{% endhint %}

### When to use PostGIS

For the City, the main thing PostGIS gets us is the ability to **automate spatial functions/queries in our data pipelines.** 

If a department asks for some ad hoc GIS analysis, [ArcGIS Desktop](employee-handbook/tools/arcgis.md#arcgis-desktop) \(ArcGIS Pro or ArcMap\) will likely be the best tool for you to use. You'll be able to easily analyze the data and share the results with the department via [ArcGIS Online](employee-handbook/tools/arcgis.md#arcgis-online). In addition, if you're helping a department with spatial data collection \(e.g. the annual homelessness survey\), an ArcGIS product like [Survey123](employee-handbook/tools/arcgis.md#survey123) or [Collector](https://www.esri.com/en-us/arcgis/products/collector-for-arcgis/overview) would probably be best.

On the other hand, if a department needs a report to be updated with some frequency \(daily, weekly, monthly, etc.\) that has a spatial component to it, PostGIS might be the tool to reach for.

### Example PostGIS pipelines

#### Vision Zero

We get new data every month for the [Vision Zero Crash Map](https://apps.boston.gov/vision-zero/). Because CAD data gets geocoded to addresses, mapping the raw data means it looks like crashes are happening on/in buildings. Ideally they would be mapped on the street they occurred on.

We use PostGIS functions to move the crash points to the closest location on the street which they occurred. We then use the [ArcGIS Python API](https://developers.arcgis.com/python/) to overwrite [feature services](http://boston.maps.arcgis.com/home/item.html?id=9b19b989f25a4d718d09be2227626a32) hosted on ArcGIS Online. We display those services on [the web map](https://apps.boston.gov/vision-zero/) using [Mapbox](https://www.mapbox.com/), a web mapping library.  

#### DND 311 Cases 

When a 311 case is opened on a DND owned parcel, the responsibility to address the issue falls to DND, not other departments who usually deal with that kind of case. As a result, DND was interested in seeing all the 311 cases opened within 30ft of any parcel they owned. They wanted a table showing all of these cases and generic information about each \(time opened, description, etc.\). 

Using PostGIS, we buffered the DND owned parcels by 30ft, asked which 311 cases fell inside those areas, and created a script that would re-do that calculation twice a day. We then built a Tableau dashboard displaying a table with these cases listed and shared it with DND. 

_This pipeline is no longer in production, but its still a good example!_

## [Geocoding](https://en.wikipedia.org/wiki/Address_geocoding)

### SAM Geocoder

### ArcGIS Composite Geocoder

#### How to add the ArcGIS Composite Geocoder to ArcMap

1. In the **Catalog** window select **Add ArcGIS Server**
   * Use GIS services
   * Enter in the box the Server URL:  [https://awsgeo.boston.gov/arcgis/rest/services](http://awsgeo.boston.gov/arcgis/rest/services)
2. Right-click on the table you want to geocode and select **Geocode Addresses...**
3. When you have the option to **Choose an Address Locator to use**
   * Select **Add...**
   * Navigate in the folder structure to GIS Servers &gt; arcgis on [awsgeo.boston.gov](http://awsgeo.boston.gov/) &gt; Locators &gt; **Boston\_Composite\_Prod**
4. Select **Boston\_Composite\_Prod** 
   * When selecting **Address Input Fields**, use the **Single Field** option
   * This may require you to concatenate your various fields
   * The Multiple Fields option does not function with this tool

