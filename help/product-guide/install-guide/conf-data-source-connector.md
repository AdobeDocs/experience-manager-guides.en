---
title: Configure a data source connector
description: Learn how to configure a data source connector
exl-id: bd1188e1-0e1d-4e70-928a-10251c3d529d
feature: Web Editor Configuration
role: Admin
level: Experienced
hidefromtoc: 'yes'
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure a data source connector 

AEM Guides provides out-of-the-box connectors for JIRA and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases. You can also add other connectors by extending the default interfaces. The following configuration helps you to easily add the various data sources. Once added, you can view the data sources in the Editor. 

Perform the following steps to configure a data source connector and then use it from the Editor:

## Configure a connector

You can configure an out-of-the-box connector by uploading a JSON file. You can use the following sample setup files to set up connectors for Jira and SQL (MySQL, PostgreSQL, SQL Server, SQLite) databases.
  
A sample setup file for Jira's basic authentication with username and password:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "username": "jirausername",
            "password": "jirapassword",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

For example, save as `jira.json`.

A sample setup file for Jira's basic authentication with token:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

For example, save as `jira.json`.

A sample setup file for Jira's basic authentication with the token having "Basic" keyword present in it: 

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
    "configName": "Jira",
    "templateFolders": ["/content/dam/dita-templates/konnect/jira"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
        "configData": {
            "token": "Basic jiraauthtoken",
            "url": "https://jira.corp.adobe.com/rest/api/latest/search"
        }
    }
}
```

For example, save as `jira.json`.

A sample setup file for MySql's basic authentication:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
    "configName": "MySQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.mysql.jdbc.Driver",
            "connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
        }
    }
}
```

For example, save as `mysql.json`.

A sample setup file for PostgreSQL's basic authentication:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
    "configName": "PostgreSQL",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.postgresql.Driver",
            "connectionString": "jdbc:postgresql://host:port/database"
        }
    }
}
```

For example, save as `postgres.json`.

A sample setup file for MS SQL Server's basic authentication:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
    "configName": "MSSQLServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
            "connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
        }
    }
}
```

For example, save as `mssqlserver.json`.

A sample setup file for SQLite's basic authentication:

```
{
    "connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
    "configName": "SQLiteServer",
    "templateFolders": ["/content/dam/dita-templates/konnect/sql"],
    "connectionConfig": {
        "configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
        "configData": {
            "username": "admin",
            "password": "admin",
            "driver": "org.sqlite.JDBC",
            "connectionString": "jdbc:sqlite:sample.db"
        }
    }
}
```

For example, save as `sqqlite.json`.

### Customize a connector configuration

AEM Guides allows you to customize some values in the configuration file to meet the user's needs.

|Property Name| Description|
|---|---|
|configName| The user can specify a configuration name to help identify the connector|
|templateFolders| List of Folders from where templates will be fetched|

Other fields are customized based on the config class selected to run the Connector.

## Upload the file to a location in AEM

Upload the file to some location in AEM Assets.

For example,  `/content/dam/jira.json`

## Create Configuration using REST API

You can register the configuration using REST API. For more details, view the *REST API to register a data source connector* section in the API Reference for Adobe Experience Manager Guides.

Once you have configured the data source, the connector is listed under the Data Sources panel in the Web Editor. You can then connect to the data source and insert a content snippet into your topics. For more details, view [Insert a content snippet from your data source](../user-guide/web-editor-content-snippet.md).
