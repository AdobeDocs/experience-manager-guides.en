---
title: Architecture of External Data Sources Integration in AEM Guides
description: Learn about the architecture of External Data Sources Integration in AEM Guides.
---
# External data sources integration

Data from external systems can be easily integrated into your Experience Manager Guides instance. Connecting to external data sources can significantly enhance the functionality and usability of your content management system. 


You can efficiently connect and fetch data from external sources using data integration. With this feature, you don't have to depend on the IT team to obtain the data and then manually copy and paste it or constantly update the changes in the external system.

This feature ensures synchronization with the original source and allows harmonious updates to the documentation without relying on manual copy-paste operations. It also helps maintain the data consistency between Experience Manager Guides and the external data source.

Furthermore, after fetching the content from external data sources, you can author it in DITA format and also reuse the integrated content.


## Data source integration framework

The integration framework of a data source primarily encompasses two main components: the external data sources and their integration into Experience Manager Guides instance.

### External Data Sources

Some of the data sources that you can connect from Experience Manager Guides  are as follows:

- Relational Databases (RDBMS)
    - PostgreSQL, MySQL, Microsoft SQL Server, MariaDB, and SQLite
- Non-relational Databases
    - MongoDB, Apache Cassandra, Apache CouchDB, and Redis
- Product Information Management (PIM) / Product Lifecycle Management (PLM)
    - Pimcore, Salsify, Akeneo, and Informatica
- Product Management Systems
    - JIRA and Microsoft Azure DevOps Boards (ADO) 
- Online Analytical Processing (OLAP) and Analytics Systems

### Integration in Experience Manager Guides 



Through the use of an authenticated connector, data is transferred from an external system and generates data within Experience Manager Guides.
![Architecture](assets/Konnect-Architecture.gif)


### Integration in Experience Manager Guides

Perform the following steps to integrate the content into Experience Manager Guides:

1. **Set up the data source connector**
    - o	The data source connector serves as the interface to establish connectivity with the external data sources. You must configure the connector to establish the connection and include the authentication methods, such as `Basic Auth` or `API key Auth`. All configuration details, including encrypted information, are securely stored in Adobe Experience Manager.
    - The connector layer is designed to be extensible, allowing you to create your implementations for connecting to various systems that are not provided out-of-the-box by Experience Manager Guides.
      ![Connector Layer](assets/data-source-connector-layer.jpg)
   >[!NOTE]
   >
   > Access the Konnect definition module and implement the Connector interface to create a custom connector.
   
1. **Customize the Velocity templates** 

   - Experience Manager Guides supports Velocity (https://velocity.apache.org/), a highly robust templating engine to transform the data from JSON files into DITA content. Velocity offers the flexibility to navigate through JSON structures with any level of nesting.
   - The following example showcases how you can integrate velocity templates and data sourced from Jira to effortlessly generate tables or ordered lists.
      - Jira Response
     
        ```
        {
            "expand": "schema,names",
            "total": 5,
            "hostname": "https://jira.corp.adobe.com",
            "maxResults": "200",
            "issues": [
                {
                    "key": "DXML-12756",
                    "fields": {
                        "description": "Implement the snippet generator in External Data Source integration",
                        "summary": "Implement the snippet generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12755",
                    "fields": {
                        "description": "Implement the topic generator in External Data Source integration",
                        "summary": "Implement the topic generator in External Data Source integration"
                    }
                },
                {
                    "key": "DXML-12745",
                    "fields": {
                        "description": "Implement the ability to register a new connector",
                        "summary": "Implement the ability to register a new connector"
                    }
                }
            ],
            "startAt": 0
        }
        ```
        
      - Templates
        ![Templating Engine](assets/data-source-TemplatingEngine.png){width="800" align="left"}
      - Data generated from same data source but different templates
        ![Data Generated](assets/data-source-templates-topics.png){width="800" align="left"}        

3. **Generate content using the templates** 
   - You can generate the content from the templates that you have created. 
   - You can generate various types of content:
        - Snippet: This is one-time usable content. You can generate the data from the connector in the defined template and then embed it in the desirable tag.
        - DITA Topic: Generate various topics to use as is in content or can be reused as a *Reusable Component*.
        - DITA Topic + Map: You can also generate a complete map can also with the topic and then use the data for publishing directly or use it as a *Reusable Component* in other data.


4. **Publish the integrated content** 
   - Publishing is the OOTB feature of Experience Manager  Guides and you can directly publish all the data generated from the external system as PDF or AEM Site output. 

### Learn how to configure data sources

The following documents provide more details on configuring the connectors and using them in your instance.

1. [Configure a data source connector](conf-data-source-connector-tools.md)
2. [Generate content using snippets or topics](../user-guide/web-editor-content-snippet.md)