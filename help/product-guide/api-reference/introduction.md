---
title: Introduction
description: Introduction to the API Reference Guide for AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
---
# Introduction {#id1761C0007W7}

Adobe Experience Manager Guides \(later referred as *AEM Guides*\) is an end-to-end, enterprise solution that enables Adobe Experience Manager \(AEM\) to have component content management solution \(CCMS\) capabilities for DITA-based content creation and delivery. Customers can access AEM Guides workflows programmatically using the AEM Guides APIs to integrate it with other enterprise applications. These APIs can also be used by Adobe partners to enhance the value proposition of AEM Guides by extending its functionality or by integrating it with other applications or services.

## AEM Guides APIs 

The AEM Guides APIs are available in two formats: 

- [Java-based APIs](#java-based-apis)
- [REST-based APIs](#rest-based-apis)

These APIs expose key functions of AEM Guides to application developers. Using these functions, developers can create their own plug-ins to extend the out-of-the-box workflows. The APIs are available around managing outputs for DITA content, working with DITA maps, adding conditional attributes to folder-level profiles, and converting HTML and Words documents to DITA format.


### Java-based APIs

You can use Java-based APIs available in Experience Manager Guides to create custom plugins and extend out-of-the-box workflows. 

**Configure SDK from Maven central repository for AEM Guides as a Cloud Service**

>[!INFO]
>
>View [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-dox-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) for the latest and detailed documentation on using the Java-based API for Experience Manager Guides as a Cloud Service.

To configure and use the service API JARs from Maven repository in your projects, add the API SDK as a project dependency in your project's `pom.xml` file as shown below.

    ```XML
    <dependency>
    <groupId>com.adobe.aem</groupId>
    <artifactId>aem-dox-sdk-api</artifactId>
    <version>${RELEASE}</version>
    </dependency>

    ```

>[!NOTE]
>
> Ensure that you use the same version of the API JAR as the AEM Guides package installed on your server.

**Configure and use the API JAR from Maven central repository (On-premise)**

>[!INFO]
>
>View [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) for the latest and detailed documentation on using the Java-based API for Experience Manager Guides On-premise setup.

To configure and use the service API JARs for on-premise deployments, add the service API JAR as a project dependency in your project's `pom.xml` file as shown below:

    ```XML
    <dependency>
    <groupId>com.adobe.aem</groupId>
    <artifactId>aem-guides-sdk-api</artifactId>
    <version>${RELEASE}</version>
    </dependency>

    ```

>[!NOTE]
>
> Ensure that you use the same version of the API JAR as the AEM Guides package installed on your server.   


**Configure and use the API JAR from AEM Guides public Maven repository (On-premise)**

>[!NOTE]
>
> The public AEM Guides Maven repository will be deprecated after the 5.3.0 release of Experience Manager Guides. The API JAR will only be available in Maven central repository thereafter.   

Perform the following steps to use the service API JARs from the public Maven repository:

1. Configure the AEM Guides public Maven repository in your `pom.xml` or `settings.xml` file as shown below:

    ```XML
    
    <repository>
        <id>fmdita-public</id>
        <name>fmdita-public</name>
        <url>https://repo.aem-guides.com/repository/fmdita-public</url>
     </repository>

    ```

1. Once the repository is setup, add the service API JAR as a project dependency in the project's `pom.xml` file.

    ```XML
    

    <dependency>
        <groupId>com.adobe.fmdita</groupId>
        <artifactId>api</artifactId>
        <version>${RELEASE}</version>
    </dependency>

    ```

    >[!NOTE]
    >
    > Use the same version of the API JAR as the AEM Guides package which you have installed on the server.

Once service API JAR is added as a project dependency in the project's `pom.xml` file, you can build and use AEM Guides Java APIs in your project.


### REST-based APIs 

Experience Manager Guides provides a comprehensive set of REST-based APIs that allow developers to access and interact with core functionalities over HTTP.

These APIs are ideal for:

- Integrating Experience Manager Guides with other enterprise systems
- Automating publishing and review workflows
- Building custom applications and extensions

For detailed information on API usage, parameters, and example requests, view the relevant topics in the **API Reference** section of the Experience Manager Guides documentation.

## Additional resources 

Following is a list of other helpful resources of AEM Guides, which are available on the [Learn & Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) page:

-   User Guide
-   Installation and Configuration Guide
-   Quick Start Guide
-   [Help Archival Page](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(access older release documentation\)
