---
description: The City of Boston's Open Data program is currently in its third iteration.
---

# Open Data

## Overview

{% page-ref page="../programs/analyze-boston.md" %}

## Tech Stack

* **Analyze Boston \(CKAN\):** This is the public-facing platform through which we deliver open data. 

  This platform has an unconnected dev site. See engineering team for access to both dev and prod.

  * [Analyze Boston login](https://data.boston.gov/user/login?__no_cache__=True)
  * [Analyze Boston dev login](https://boston.ogopendata.com/user/login?__no_cache__=True)
  * [Analyze Boston schema on OpenGov Github](https://github.com/OpenGov-OpenData/ckanext-bostonschema/tree/master/ckanext/bostonschema/schemas)
  * [CKAN](https://ckan.org/)
    * A general overview of what CKAN can do can be found [here](https://drive.google.com/file/d/0B7i450bBGU-mc1NOTFhpdTVidXc/view)
    * CKAN [User Guide](https://docs.ckan.org/en/2.8/)
    * CKAN [Github](https://github.com/ckan/ckan)
  * Analyze Boston is serviced by a third-party contract. **See 'AppGeo/OpenGov'** section for contract details.

* \*\*\*\*[**Boston Maps**](gis.md#boston-maps)**:** Boston Maps is the geospatial version of Analyze Boston, which sits on the ArcGIS Online platform run by ESRI. Geospatial datasets are published on Boston Maps, and these are pushed to Analyze Boston via a harvester designed by OpenGov/AppGeo
  * [BostonMaps](http://bostonopendata-boston.opendata.arcgis.com/)
  * [BostonMaps ArcGIS Harvester Schedule](https://data.boston.gov/user/login?came_from=http%3A%2F%2Fdata.boston.gov%2Fharvest%2Fboston-maps-arcgis-online%2Fjob)
* **Google Analytics:** Analytics for the Analyze Boston platform
  * [Google Analytics](https://cityofboston.access.preservica.com/uncategorized/IO_14038e5c-8286-4846-9e34-d87b5b80f376/)
* \*\*\*\*[**S3**](employee-handbook/tools/amazon-web-services.md#s3)**:** This is used for raw data storage for manually updated datasets. See engineering team for access.
  * [Open Data AWS repository](https://us-east-1.signin.aws.amazon.com/oauth?response_type=code&client_id=arn%3Aaws%3Aiam%3A%3A015428540659%3Auser%2Fs3&redirect_uri=https%3A%2F%2Fs3.console.aws.amazon.com%2Fs3%2Fbuckets%2Fcity-of-boston%2F%3Fregion%3Dus-east-1%26state%3DhashArgs%2523%26tab%3Doverview%26isauthcode%3Dtrue&forceMobileLayout=0&forceMobileApp=0)
* \*\*\*\*[**Knack**](employee-handbook/tools/knack.md)**:** This is used as the primary process for submitting a new dataset or for adding fields to an existing dataset. See Stefanie Costa Leabo for access.
  * [Knack login](https://builder.knack.com/)
* **Upaknee:** This is used to distribute a quarterly email to internal and external stakeholders. See Sarah Figalora for access.
  * [Upaknee login](https://boston.upaknee.com/signin)
* **Medium:** Analyze Boston has a Medium page to share data stories and other news. This has not been updated since the 2016 launch.
  * [Analyze Boston Medium](https://medium.com/news-stories-from-boston-open-data)

## **Helpful Links**

### **Analyze Boston Content**

* [COB Writing Guide](https://www.boston.gov/departments/digital-team/city-boston-writing-guide)
* [COB Pattern Library](https://patterns.boston.gov/components/preview/experiential.html)
* [COB Experiential Icons](https://drive.google.com/drive/folders/0B0RwQU94BhGeclNFNVBhaGhYbXM)
* [Civic Data Ambassador Videos](https://vimeo.com/showcase/5208525)
* [Analyze Boston User Personas](https://drive.google.com/file/d/0B7i450bBGU-mMlVvTUZzdXRMMU0/view)

### **Open Data Guides & Resources**

* [State of Open Data](https://stateofopendata.od4d.net/)
* [Open Data 500](http://www.opendata500.com/)
* [US City Open Data Census](http://us-cities.survey.okfn.org/)
* [Open Data Handbook](http://opendatahandbook.org/) by the Open Knowledge Foundation
* [Project Open Data](https://project-open-data.cio.gov/)
* [Open Data Guide](http://opendata.guide/) by City of Philadelphia
* [Open Data Resource Library](https://datasf.org/resources/) by DataSF
* [Open Data Standards Directory](https://datastandards.directory/)
* [Civic Data Standards](https://labs.centerforgov.org/open-data/civic-data-standards/)
* [Data Catalogue Vocabulary \(DCAT\)](https://www.w3.org/TR/vocab-dcat/)
* [Project Open Data Metadata Schema](https://project-open-data.cio.gov/v1.1/schema/)
* [MetaData Catalog](http://metadata.phila.gov/index.html) by City of Philadelphia
* [Training Videos](https://www.youtube.com/playlist?list=PLHPo5n89M3wcOXS8utcZPSKwbobCvEhif) by BARI
* [GovEx Courses](https://courses.govex.academy/catalog)
* [Data Academy](https://datasf.org/academy/) by DataSF
* [Tactical Data Engagement](https://sunlight-foundation.gitbooks.io/tactical-data-engagement/content/) by Sunlight Foundation
* [Tactical Data Engagement 2.0](https://communities.sunlightfoundation.com/methodology/) by Sunlight Foundation
* [Tools for Community-Centered Open Data](https://communities.sunlightfoundation.com/) by Sunlight Foundation
* [Library of User Personas for Open Data](https://communities.sunlightfoundation.com/discovery/personas-library/) by Sunlight Foundation
* [Creating Open Data User Personas](https://docs.google.com/presentation/d/1fih_iHd3yWDiFCpIeBxG8XBy4Rcp4Z-Mp-1LykKRCbA/edit#slide=id.g313d7edfef_0_0) by Sunlight Foundation
* [Open Data Portal UX Strategy Proposal](https://docs.google.com/document/d/1_v9E4VbFxslog7YZfnIBNRiuHjVYoUjOM7iij0VRmoM/edit#heading=h.vwdrr8bimo8n) by City of Philadelphia
* [Understanding the Users of Open Data](https://docs.google.com/document/d/1_v9E4VbFxslog7YZfnIBNRiuHjVYoUjOM7iij0VRmoM/edit#heading=h.vwdrr8bimo8n) by NYC

### **Open Data Guiding Policies**

* [MA Public Records Law](https://www.sec.state.ma.us/pre/prenotice.htm)
* [2016 MA Ch. 121 An Act to Improve Public Records](https://malegislature.gov/Laws/SessionLaws/Acts/2016/Chapter121)
* [Guide to MA Public Records Law](https://www.sec.state.ma.us/pre/prepdf/guide.pdf)
* [MA Information Requests and Public Records](https://www.mass.gov/info-details/massachusetts-law-about-freedom-of-information-and-public-records)
* [Exemptions to Public Records Requests](https://www.mass.gov/service-details/exemptions)
* [PDDL License](https://www.opendatacommons.org/licenses/pddl/1-0/index.html)
* [2014 COB Open Data Executive Order ](https://data.boston.gov/dataset/cob-executive-order-open-data-4-7-2014)
* [2015 COB Open and Protected Data Policy](https://data.boston.gov/dataset/open-and-protected-data-policy/resource/55dff33c-4b53-462f-b4c9-af51a81c7273)

### **Other Open Data Portals**

* [COB Archives Public Catalog](https://archives.cityofboston.gov/)
* [COB Archives Digital Repository](https://cityofboston.access.preservica.com/)
* [BARI Open Data](https://www.northeastern.edu/csshresearch/bostonarearesearchinitiative/boston-data-portal/)
* [MassData](https://opendata.digital.mass.gov/#/)
* [US Open Data](https://www.data.gov/)

### **Interesting Articles**

* Sunlight Foundation 2018: [https://sunlightfoundation.com/2018/10/22/open-cities-enter-a-new-era-key-takeaways-from-the-open-cities-summit/](https://sunlightfoundation.com/2018/10/22/open-cities-enter-a-new-era-key-takeaways-from-the-open-cities-summit/)
* apolitical 2018: [https://apolitical.co/solution\_article/open-data-cities-citizens-needs/](https://apolitical.co/solution_article/open-data-cities-citizens-needs/)
* Sunlight Foundation 2019: [https://sunlightfoundation.com/2019/01/11/what-makes-a-good-open-data-use-case/](https://sunlightfoundation.com/2019/01/11/what-makes-a-good-open-data-use-case/)

## Contacts

{% hint style="info" %}
Need help with Analyze Boston? Try these folks here.
{% endhint %}

| Name | Title | Email |
| :--- | :--- | :--- |
| David Elges | Chief Information Officer | [david.elges@boston.gov](mailto:david.elges@boston.gov)  |
| Stefanie Costa Leabo | Chief Data Officer | [stefanie.costaleabo@boston.gov](mailto:stefanie.costaleabo@boston.gov)  |
| Greg McCarthy | Chief Information and Security Officer | [greg.mccarthy@boston.gov](mailto:greg.mccarthy@boston.gov) |
|  | General IT Security Team | [ITSecurityTeam@boston.gov](mailto:ITSecurityTeam@boston.gov) |
| Jason Lederman | DoIT Legal Counsel | [jason.lederman@boston.gov](mailto:jason.lederman@boston.gov)  |
| Michelle Pacitta | Boston Legal Counsel point of contact who distributes submitted datasets for legal review | [michelle.pacitta@boston.gov](mailto:michelle.pacitta@boston.gov) |
|  | OpenGov Support Tickets | [support@opengov.com](mailto:support@opengov.com) |
| Kate Hickey | Vice President, AppGeo | [khickey@appgeo.com](mailto:khickey@appgeo.com) |
| Linda Matthews | Director, Customer Success, OpenGov | [lmatthews@opengov.com](mailto:lmatthews@opengov.com)  |
| David Spolidoro | Account Exec, OpenGov | dspolidoro@opengov.com |
| Ashley Tardif | Geospatial Analyst + Analyze Boston Support, AppGeo | atardif@appgeo.com  |

