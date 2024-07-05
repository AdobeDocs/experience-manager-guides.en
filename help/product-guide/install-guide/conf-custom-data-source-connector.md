---
title: Configure a custom connector for the data sources
description: Learn how to configure a custom connector for the data sources.
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Configure custom data source connectors

Experience Manager Guides allows you to customize the connectors according to your requirements and then use them with the different data sources. To customize a connector, you need to implement the connector interface and its important functions, and then configure the interface. You can also provide the resources along with the custom connectors.


- [Customize a connector for Experience Manager Guides](#customize-connector)
- [Implement the connector interface](#implement-interface)
- [Important functions](#important-functions)
- [Types of default connector implementations](#default-connectors)
  - [Config interface](#config-interface)
  - [Types of default configs implementations](#default-config-types)
  - [Concrete config implementations](#concrete-config-implementation)
  - [Additional Resources](#resources)



## Customize a connector for Experience Manager Guides {#customize-connector}

You can customize or configure a connector for a data source using the pre-defined interfaces and abstract classes. The entire source code is available at [https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions](https://github.com/adobe/guides-data-source-connectors/tree/main/konnect-definitions). 



## Implement the connector interface {#implement-interface}

Perform the following steps to implement the interface and its functions as per your requirements:

1. Define a standardized way for the connectors to integrate with a system, allowing for the execution of queries, validation of connections, and retrieving metadata.
1. Facilitate the UI integration by providing the default methods for configuring templates, logos, queries, and other settings.
1. Ensure that the connectors are properly validated and can handle errors (`KonnectException`) when interacting with data sources.

The interface acts as a blueprint for implementing various types of data connectors, ensuring that the connectors meet any specific integration and operational requirements within a larger software ecosystem.

## Important functions {#important-functions}

Implement the following important functions: 

|Method |Mandatory |Description|
|---|---|---|
|getLogoUrl|| <ul><li> This method returns the URL used as the connector's logo. <li> By default, it returns an empty string, indicating that no logo URL is provided unless overridden. <br><b> Additional Notes</b>: <br> <ul><li> If you provide both a logo URL and a logo class name, the logo URL is used to display the logo in the user interface. <li> If you specify the logo URL through the configuration settings, it overrides the URL set in the method implementation.|
|validateConnection|Yes| <ul><li> Use this method to validate whether the connector can establish a connection to its data source. <li> It takes a `ConfigDto` object as a parameter, which contains the configuration settings such as connection credentials, and endpoint URLs. <li> The method returns true if the validation (connection test) is successful, indicating that the connector can connect to its data source.|
|execute|yes| <ul><li>Use this method to execute a single query for the connector, interacting with a data source. <li> The connectors supporting this operation handle the query execution, parse the response, and convert it into a JSON string if needed. <li> Encapsulate the query to execute in this method within a `QueryInfoDto` object, which contains details such as the query string, and parameters. <li> The method returns a JSON string that represents the response from executing the query. <br><b> Additional Notes</b>: <li>Implementations of this method vary depending on the specific connector and its interaction with the data source. <li> Use the `KonnectException` to handle any exceptions or errors that occur during the execution or connection to the data source.| 
|executeWithLimit| yes | <ul><li> Use this method for the same purpose as `execute()`, but with the additional functionality of applying a limiting query, typically for showing the previews in UI components. <li> Connectors supporting this operation handle the query execution, parse the response, and convert it into a JSON string if necessary. <li> Encapsulate the query to be executed in this method within a `QueryInfoDto` object, similar to the previous method. <br><b> Additional Notes</b>: <ul><li> `QueryResultDto` is a custom class or data transfer object that encapsulates the result of the query execution, including metadata about the query and its execution status.|
|getSampleQuery | | <ul><li>This method returns a sample query string that can be displayed in the UI, for instance, in the dialog where users can insert or edit queries. <li>By default, it returns an empty string, indicating that no sample query is provided unless overridden. <br><b> Additional Notes</b>: <ul> <li> If you do not define a sample query, and the method returns an empty string, no sample query is shown in the UI insert query dialog.|
|getTemplates | |<ul> <li> This method returns a list of templates associated with the connector. <li> By default, it returns an empty list, indicating that no templates are provided unless overridden. |
|getLogoClassName| | <ul> <li> This method returns the class name as the logo of the connector. By default, it returns an empty string, indicating that no logo class name is provided unless overridden. <br><b> Additional Notes</b>: <ul><li> If you provide both a logo URL and a logo class name, the logo URL is used to display the logo in the user interface. If you specify the logo class name through configuration settings, it overrides the class name set in the method implementation. |
| enabled| yes| <ul><li> This method checks if a `connector` is enabled. <li> By default, the method returns false, meaning that the connector is not enabled unless overridden by a class implementing this method.| 
| getDescription| | <ul><li>Use this method to return a description string that can be displayed in the UI. <li> By default, it returns an empty string, indicating that no description is provided unless overridden. |
| getAuthor | | <ul><li> This method provides a way to retrieve the name of the author who created or is responsible for the connector. <li> It typically helps identify and acknowledge the connector's creator or maintainer within a system or framework.|
|getName|yes | <ul><li>This method provides a way to retrieve the unique name assigned to a connector. <li>The returned name is crucial for identifying the connector within a user interface (UI) context, especially if the connector's configuration settings don't specify a name explicitly. <li>This name is used in various UI components to display or manage connectors in a user-friendly manner.|
|getGroup|yes| <ul> <li>This method provides a way to retrieve the group name associated with a connector. <li>Group names are typically used to organize or categorize connectors into logical groups based on their functionality, purpose, or type. <li> This allows for easier management and presentation of connectors within the configuration UI.|
|getDefaultTemplatePath|| <ul><li> This method returns the default path for the templates associated with this connector. <li> By default, it returns an empty string, indicating that no default path is set unless overridden.|
|getLogoSvg|| <ul><li>Use this method to return the SVG representation of the logo of the connector. <li> By default, it returns an empty string, indicating that no SVG data is provided unless overridden.|
| getMaxNoRowsForPreviewQuery| | <ul><li>This method returns the maximum number of rows queried or displayed in the UI preview. <li> By default, it returns the value of DEFAULT_LIMIT_PREVIEW, a constant representing the default limit for preview rows.|
|getConfigClass|yes| <ul><li>This method provides information about the classes that implement the Config interface and are supported by this connector. <li> It allows the application or framework to dynamically discover and work with configurations that are compatible with the connector.|

## Types of default connector implementations {#default-connectors}

The *konnect-definitions* library ships abstract connector implementations and with predefined functions to run queries. These connector implementations act as templates that can be directly extended and used as is. If a custom implementation is required, its functions can be overridden.

Besides implementing the default connectors, you can also implement one of the following default abstract classes:

- Rest Connector
- File Connector
- GraphQL Connector
- SQL Connector
- NoSQL Connector


If a connector fits into one of these types, extend the connector to the corresponding base class. Otherwise, create it from scratch by implementing the connector interface.

## Config interface {#config-interface}

The `Config` interface is designed to configure a data source with a specific authentication method, giving you precise control over how you create the connection.

The `Config` interface provides flexibility in how authentication details are handled and implemented. Different implementations can offer various ways of authenticating data sources. A connector uses a Config instance to execute and validate queries against a data source, forming a complete workflow.
A connector uses a `Config` instance to execute and validate queries against a data source, forming a complete workflow.

A config implementation defines how authentication is handled to connect to a data source. This config is then used by a connector implementation to interact with the data source, ensuring that queries are executed and validated correctly.

Overall, the `Config` interface is a crucial part of the workflow for connecting to data sources, focusing specifically on authentication configuration.

### Types of default configs implementations {#default-config-types}

The *konnect-definitions* library ships with pre-defined implementations of the Config interface for some widely used authentication configs. You can use these configs directly in the connector or define new using the Config interface.

There are three types of default abstract config implementations for Authentication:

- RestConfig
- SqlConfig
- NoSqlConfig

If a config aligns with one of these types, it can extend the corresponding base class. Otherwise, it can be created from scratch by implementing the Config interface.

### Concrete config implementations {#concrete-config-implementation}

For each abstract config class, you also get the concrete implementations you can use directly for authentication. These implementations include:

- API Key Auth Config
- Basic Auth Token-based Config
- Basic Auth Config
- Bearer token config
- Username Password config for SQL
- Connection string auth config for NoSQL

### Additional Resources{#resources}

Experience Manager Guides also allows you to provide custom resources for logos and templates along with the implementation. You can keep these resources in the `resources` folder.
To make them usable by the connector, it's mandatory to implement these connector functions:


- `getLogoSvg` - Returns the logo SVG as a string.

- `getTemplates` - Returns the list of templates in the given format.