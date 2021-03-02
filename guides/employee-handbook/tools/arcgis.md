# ArcGIS

## [ArcGIS Online](https://www.esri.com/en-us/arcgis/products/arcgis-online/overview)

### [Hosted Feature Layer](https://doc.arcgis.com/en/arcgis-online/manage-data/hosted-web-layers.htm)

A hosted feature layer is the basic [building block](https://doc.arcgis.com/en/arcgis-online/manage-data/data-in-online.htm) of the maps we create. In a map, you can use multiple layers of data to overlay information.

#### How to create a new hosted feature layer via ArcGIS Online

1. Create a CSV file from the dataset you wish to use.
2. Log into [Boston Maps](../../gis.md#boston-maps) and navigate to the [Content](https://boston.maps.arcgis.com/home/content.html) section. If you want this layer to be updated via a Civis workflow then please use the **etldevelopers\_boston** service account.
3. In the top left, choose **Add Item** &gt; **From your computer**
   1. Titles must be unique & tags are required. We usually use CSV and anything else appropriate.
   2. Once you've uploaded a CSV file you'll notice a checkbox with **Publish this file as a hosted layer** selected. Keep it selected.
4. Assuming your dataset has geospatial columns and it correctly recognized those columns you can leave the rest as is and choose **Add Item**.

#### How to overwrite a hosted feature layer via ArcGIS Online

1. Find the hosted feature layer you'd like to update by searching the [Content](https://boston.maps.arcgis.com/home/content.html) section.
2. On the right, choose **Update Data** &gt; **Overwrite Entire Layer** then follow the instructions.

#### How to overwrite a hosted feature layer via Civis

{% hint style="info" %}
Please make sure the feature layer was **created from a CSV** file and not a Service Definition otherwise you will see a `list index out of range` error when using the Export: Arcgis Feature Layer component.
{% endhint %}

## [ArcGIS Desktop](https://desktop.arcgis.com/en/)

### How to Install ArcGIS Desktop Applications

1. Go to the Google Drive folder containing the installation files for the program you wish to install.
   1. [ArcGIS Pro installation files](https://drive.google.com/open?id=1x_EyirfwqQvNVyJIVRfLMn47pzDO51-d) \(2.3\)
   2. [ArcMap installation files](https://drive.google.com/open?id=1TPNvd7fNpjxzFl4AdJ62vQW07DkrSArT) \(10.6.1\)
   3. [Root folder with all files](https://drive.google.com/drive/folders/0B5xorwVOSRdXTm1tZFhYVnJDWVk?usp=sharing) \(ArcGIS Pro, ArcMap, SAM Building Tool, Insights\). The above two are subfolders in this root folder.
2. Download the .exe file on your computer then double-click it to run and follow the on-screen instructions. 
3. You need a license to run any ArcGIS software. Once you have installed the program and go to open it for the first time, you will get the error below. This is because you need to tell ArcGIS where to look for the license.
   1. Locate ArcGIS Administrator \(should have been one of the installed programs in the general installation bundle\). Search for it on your computer.
   2. Go to the Desktop folder and add ZPGISLIC to the License Manager field.
4. All set. You should now be able to use the ArcGIS desktop software that you installed.

![](../../../.gitbook/assets/image%20%281%29.png)

![](../../../.gitbook/assets/image%20%282%29.png)

### [ArcGIS Pro](https://www.esri.com/en-us/arcgis/products/arcgis-pro/resources)

### Updating a hosted feature layer via ArcGIS Pro

### [ArcMap](https://desktop.arcgis.com/en/arcmap/)

## [StoryMaps](https://storymaps.arcgis.com/stories)

### Optimal Image Sizes for Story Maps

{% hint style="info" %}
All images should be in JPG format.
{% endhint %}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Sizing (px)</th>
      <th style="text-align:left">Ratio</th>
      <th style="text-align:left">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Featured Content</td>
      <td style="text-align:left">600 x 400</td>
      <td style="text-align:left">3:2</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Map Tour (New)</td>
      <td style="text-align:left">2000 x 750</td>
      <td style="text-align:left">4:3</td>
      <td style="text-align:left">Landscape</td>
    </tr>
    <tr>
      <td style="text-align:left">Map Tour (Original)</td>
      <td style="text-align:left">1000 x 750</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Cascade</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>2000 px - Covers, immersive sections, large images in narrative sections.</p>
        <p>1000 px - Small/medium images in narrative sections</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Map Journal</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left">
        <p>2000 px - Main Stage</p>
        <p>1000 px - Side panels</p>
        <p>2000 px - Expandable side panels</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Shortlist (New)</td>
      <td style="text-align:left">1000 x 750</td>
      <td style="text-align:left">4:3</td>
      <td style="text-align:left">If you use 3:2 instead of 4:3, just make it uniform for all items.</td>
    </tr>
    <tr>
      <td style="text-align:left">Custom Points</td>
      <td style="text-align:left">120 x 120</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">An example is the flowers on the Garden Contest map.</td>
    </tr>
    <tr>
      <td style="text-align:left">Twitter</td>
      <td style="text-align:left">600 x 400</td>
      <td style="text-align:left"></td>
      <td style="text-align:left">4 x 6 print size</td>
    </tr>
    <tr>
      <td style="text-align:left">Header Logo</td>
      <td style="text-align:left">250 x 50 max</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

## [Survey123](https://www.esri.com/en-us/arcgis/products/arcgis-survey123/overview)

