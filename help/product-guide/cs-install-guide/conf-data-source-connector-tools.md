---
title: Configure a data source connector using tools
description: Learn how to configure a data source connector using the tools.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Configure a data source connector from the user interface

Experience Manager Guides comes with the **Data Sources** tool that helps you configure out-of-the-box connectors for data sources. You can set up the JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, ElasticSearch, and Generic REST Client connectors.

Besides these out-of-the-box connectors, Experience Manager Guides provides the connectors for Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO) data sources. You can download and install them. The users can then configure these connectors. 

You can also connect to JSON data files using a file connector. Upload the JSON file from your computer or browse it from the Adobe Experience Manager assets. Then, create content snippets or topics using the generators.

To configure a connector, perform the following steps:

1. Select the **Adobe Experience Manager** link at the top and choose Tools. 
1. Select **Guides** from the list of tools.
1. Select the **Data Sources** tile. The **Data Sources** page is displayed. You can view the connected data sources.

    You can toggle between the **List View** or **Tile View** to view the various connected data sources as a list or as tiles. 

    <img src="./assets/data-sources-create-window.png" alt= "data sources listed on the data sources page" width="800">

    *View or Create a data source connector.*
1. Click **Create**.
1. Select the database for which you want to create the connector. For example, the ElasticSearch connector. 
    >[!NOTE] 
    >
    >All the available out-of-the-box databases are listed.

1. Click **Next**. 
1. Enter the configuration and connection details as per the database. 

    >[!TIP]
    >
    >* Hover over <img src="./assets/info-details.svg" alt= "info icon" width="25"> near the field to view more details about it.
    > * Fields with * are mandatory. For example, you can enter the following details for the ElasticSearch connector.

    * **Name**: Enter the name of the data source.
    * **Authentication type**: Select the type of authentication from the drop-down. For example, Basic username-password authentication
    * **Username**: Enter your username.
    * **Password**: Enter your username and password. 
    * **URL**: Add the API URL.

        **Connect to multiple resources**: You can add or use multiple resources based on different URLs for some connectors like Generic REST Client, Salsify, Akeneo, and Microsoft  Azure DevOps Boards  (ADO). Then, connect with them to create content snippets or topics using the generators for them. 
        
        Perform the following steps to create a resource:
        1. Select ![add icon](assets/Add_icon.svg) in the **URL resource section** to add a resource for each URL. 
        1. Configure all the details in the **Add resource** dialog box.
        1. Click **Add**.
        1. You can edit ![edit icon](assets/edit_pencil_icon.svg) or delete ![delete](assets/Delete_icon.svg) the resource from the URL resource list.
        
        1. You can also use the default resources available for data sources like Salsify, Akeneo, and Microsoft ADO. Toggle the options OFF for the resource you don't want to configure for a data source.

        This helps you to quickly fetch data from any of the resources for a particular data source in a single content snippet or topic.

1.  Select the **Exclude factory templates** option to exclude the factory templates from being used for topic and snippet generation. They will not appear under the **Data mapping template** dropdown in the  **Add content snippet generator** or the **Add topic generator** dialog box.


1. Select **Test connection**. You can view the **Test Connection** button enabled only after you add the required details. View a success message if the connection details are correct. Otherwise, you might view an error message. 

    

1. Select **Save** on the top to save the connector.     View the **Save** button enabled after you fill in all the details and the connection is successful.


    If the connector is saved successfully, you can view the connected data source on the page. 

## Features available for a connector

* Toggle between the **List View** or **Tile View**  to view the various connected data sources as a list or as tiles. 
* Select the checkbox for a single connector. Click **Select All** to select all connectors. You can click **Deselect All** when all the connectors are selected. 
 
<img src="./assets/data-sources-features.png" alt= "features of the data sources on the data sources page" width="800">
 
*Edit, reconnect, duplicated, or delete a data source connector.*

You can use the following features for the connector on the **Data Sources** page:

* **Edit**: Edit the configuration details for the selected connector.

* **Reconnect**: Reconnect to a disconnected connector.

* **Duplicate**: Create a new duplicate connector using the current connector as the base. The duplicate connector is created with a suffix (like connectorname_1) by default. For example, sample-elastic-search_1. 
You view an error if the connector with the same name exists.

* **Delete**: Delete the selected connector.


Once you have configured the data source, the connector is listed under the **Data Sources panel** in the Web Editor. You can then connect to the data source and insert a content snippet into your topics. For more details, view [Insert a content snippet from your data source](../user-guide/web-editor-content-snippet.md).
