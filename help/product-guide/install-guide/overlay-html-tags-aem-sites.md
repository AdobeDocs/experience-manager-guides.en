---
title: Overlay the HTML tags in non-legacy AEM  Sites output
description: Configure the video and the image settings for aem sites output based on core components mapping
feature: Installation
role: Admin
level: Experienced
---

# Overlay HTML tags in AEM Sites output 

You can add and customize HTML tags in AEM Sites output generated using the AEM Sites preset based on core components mapping from the Web Editor. To customize the HTML tags, you can overlay the `config.xml` file. For example, you can configure the video and image maps in AEM Sites output.

Perform the following steps to overlay and update the `config.xml` file:

1. Log into AEM and open the CRXDE Lite mode.

1. Navigate to the configuration file available at the following location:

    `/libs/fmdita/cq/xssprotection/config.xml`

1. Create an overlay node of the `xssprotection` folder within the apps node.

1. Navigate to the configuration file available in the `apps` node:

    `/apps/fmdita/config/config.xml`

1.  Update the following tags for the videos:
  
	```XML
    <tag name="video" action="validate">
	    <attribute name="src">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="width">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="height">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="data">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="class">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="poster">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="controls">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
    </tag>
    <tag name="source" action="validate">
	<attribute name="src">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
    </tag>

   ```

1. Update the following tags for the image maps: 

   ```XML
    	<tag name="map" action="validate">
	<attribute    name="name">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
	<attribute name="src" onInvalid="removeTag">
		<regexp-list>
			<regexp name="onsiteURL"/>
			<regexp name="offsiteURL"/>
		</regexp-list>
	</attribute>
	<attribute name="name"/>
	<attribute name="alt"/>
	<attribute name="height"/>
	<attribute name="width"/>
	<attribute name="border"/>
	<attribute name="align"/>
	<attribute name="usemap">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="hspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
	<attribute name="vspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
    </tag>
    <tag name="area" action="validate">
	<attribute name="shape">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="coords">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="href">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
   </tag>
   ```

1. Save the file.

Learn more about the best practices of [Security](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/security). 