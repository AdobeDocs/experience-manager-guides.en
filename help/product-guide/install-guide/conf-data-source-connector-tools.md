---
title: Configure a data source connector using tools
description: Learn how to configure a data source connector using the tools.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/VnRmYie1-SA-DFrz46j3xS6GEO6rJG4QAc4M-mNMYYc
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure a data source connector from the user interface

Experience Manager Guides comes with the **Data Sources** tool that helps you configure out-of-the-box connectors for data sources. You can set up connectors for JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), AdobeCommerce, and ElasticSearch databases.

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
    >* Hover over <img src="./assets/info-details.svg" alt= "info icon" width="25"> near the field to view more details about it.
    > * Fields with * are mandatory. For example, you can enter the following details for the ElasticSearch connector.

    * **Name**: Enter the name of the data source.
    * Authentication type: Select the type of authentication from the drop-down. For example, Basic username-password authentication
    * **Username**: Enter your username.
    * **Password**: Enter your username and password. 
    * **URL**: Add the API URL.

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


Once you have configured the data source, the connector is listed under the **Data Sources panel** in the Web Editor. You can then connect to the data source and insert a content snippet into your topics. For more details, view [Use data from your data source](../user-guide/web-editor-content-snippet.md).

>[!NOTE]
>
>You can also create custom connectors and use them with the different data sources. Learn how to [configure custom connectors](../knowledge-base/kb-articles/data-source/conf-custom-data-source-connector.md).