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

You can use Java-based APIs available in Experience Manager Guides to create custom plugins and extend out-of-the-box workflows. View [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) for the latest and detailed documentation on using the Java-based API.

**Configure and use the service API JAR from public Maven repository**

Perform the following steps to configure and use the service API JARs from the public Maven repository in your projects:

1.  To use the service API JAR in a project, configure AEM Guides public Maven repository in your pom.xml file.
2.  Configure the public Maven repository in Maven's settings.xml file as follows:

    ```XML
    <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
    ```

3.  Once the repository is setup, add the service API JAR as a project dependency in the project's pom.xml file.

    >[!NOTE]
    >
    > Use the same version of the API JAR as the AEM Guides package which you have installed on the server.

4.  Configure the Maven dependency as shown below:

    ```XML
    <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>4.0</version>
    </dependency>
    ```


Once service API JAR is added as a project dependency in the project's pom.xml file, you can build and use AEM Guides Java APIs in your project.


**Using API JAR from Maven Central repository for AEM Guides as a Cloud Service**

For AEM Guides as a Cloud Service the API JAR has been deployed to Maven Central. You can use the API JAR without any setup.

>[!NOTE] 
>
> The naming convention of the API jar has been updated as per the cloud add-ons naming convention.

To use the API JAR, you need to add the dependency to your project's pom.xml as shown below:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-dox-sdk-api</artifactId>
   <version>${RELEASE}</version>
</dependency>
```

>[!NOTE] 
>
> Since the packages inside the API JAR are still the same, no code change is required to use this API JAR in the existing cloud projects.

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
