---
title: Custom indexing deployment 
description: Learn how to custom index content
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Deploying custom index for Markup Search and Replace feature

## Overview

This guide provides step-by-step instructions for deploying the `guidesAssetLucene-1-custom-1` custom index on Adobe Experience Manager (AEM) as a Cloud Service. This index is required to enable the **Markup Search and Replace** feature, which allows you to search and replace text across DITA XML and Markdown files in your AEM Guides environment.

### Markup Search and Replace feature

The Markup Search and Replace feature enables content authors and administrators to:

- Search for specific text patterns across DITA topics and Markdown files.
- Replace text in multiple files simultaneously.
- Perform bulk content updates efficiently.
- Maintain content consistency across large documentation sets.

### Prerequisites

Before proceeding with the index deployment, ensure you have:

- **AEM as a Cloud Service environment** with AEM Guides installed
- **Access to your project's codebase** (Git repository)
- **Cloud Manager access** with deployment permissions
- **Basic knowledge** of AEM project structure and Maven builds
- **Familiarity** with Cloud Manager CI/CD pipelines

## Index definition

To enable the Markup Search and Replace feature, you need to deploy a custom index named **`guidesAssetLucene-1-custom-1`** to your AEM Cloud Service environment.

### Index name

```
guidesAssetLucene-1-custom-1
```

### Index definition (.content.xml)

Create the following index definition in your project at:  

`ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:dam="http://www.day.com/dam/1.0"
          xmlns:nt="http://www.jcp.org/jcr/nt/1.0" xmlns:oak="http://jackrabbit.apache.org/oak/ns/1.0"
          xmlns:rep="internal"
          jcr:mixinTypes="[rep:AccessControllable]"
          jcr:primaryType="oak:QueryIndexDefinition"
          async="[async,nrt]"
          compatVersion="{Long}2"
          evaluatePathRestrictions="{Boolean}true"
          includedPaths="[/content/dam]"
          reindex="{Boolean}false"
          reindexCount="{Long}18"
          seed="{Long}958982603885135223"
          selectionPolicy="tag"
          tags="[ditaSearch]"
          type="lucene">

    <aggregates jcr:primaryType="nt:unstructured">
        <dam:Asset jcr:primaryType="nt:unstructured">
            <include0
                    jcr:primaryType="nt:unstructured"
                    path="jcr:content/renditions/original/jcr:content"
                    relativeNode="{Boolean}true"/>
        </dam:Asset>
    </aggregates>

    <analyzers jcr:primaryType="nt:unstructured">
        <default jcr:primaryType="nt:unstructured">
            <tokenizer
                    jcr:primaryType="nt:unstructured"
                    name="Whitespace"/>
        </default>
    </analyzers>

    <indexRules jcr:primaryType="nt:unstructured">
        <dam:Asset
                jcr:primaryType="nt:unstructured"
                indexNodeName="{Boolean}true">
            <properties jcr:primaryType="nt:unstructured">
                <cqTags
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/cq:tags"
                        nodeScopeIndex="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        useInSpellcheck="{Boolean}true"
                        useInSuggest="{Boolean}true"/>
                <jcrLastModified
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/jcr:lastModified"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <jcrCreated
                        jcr:primaryType="nt:unstructured"
                        name="jcr:created"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"
                        type="Date"/>
                <guidesParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesParentMaps"
                        propertyIndex="{Boolean}true"/>
                <guidesDirectParentMaps
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/guidesDirectParentMaps"
                        propertyIndex="{Boolean}true"/>
                <ditaClass
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dita_class"
                        propertyIndex="{Boolean}true"/>
                <nodeNameLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(fn:name())"
                        ordered="{Boolean}true"
                        propertyIndex="{Boolean}true"/>
                <cqDriveLock
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/cq:driveLock"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <docState
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/docstate"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <jcrPath
                        jcr:primaryType="nt:unstructured"
                        function="fn:path()"
                        ordered="{Boolean}true"/>
            </properties>
        </dam:Asset>
    </indexRules>

    <tika jcr:primaryType="nt:unstructured">
        <mimeTypes jcr:primaryType="nt:unstructured">
            <application jcr:primaryType="nt:unstructured">
                <xml
                        jcr:primaryType="nt:unstructured"
                        mappedType="application/dita+xml"/>
            </application>
            <text jcr:primaryType="nt:unstructured">
                <markdown
                        jcr:primaryType="nt:unstructured"
                        mappedType="text/markdown+source"/>
            </text>
        </mimeTypes>
    </tika>
</jcr:root>
```

## Deployment steps

For detailed instructions on deploying custom indexes to AEM as a Cloud Service, view **[Content Search and Indexing - AEM as a Cloud Service](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing)**.

### Important points for this Index

When following the deployment guide, use the following specifics for the Markup Search and Replace index:

- **Index name**: `guidesAssetLucene-1-custom-1`
- **Index type**: Fully custom index (not a customization of OOTB index)
- **Location**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Package Properties Required**:
  - `noIntermediateSaves=true`
  - `allowIndexDefinitions=true`

## Reindexing

Reindexing is handled **automatically** by AEM as a Cloud Service when you deploy the index through Cloud Manager's CI/CD pipeline. No manual reindexing steps are required.

### What to Expect

- The indexing job will start automatically after deployment.
- You can monitor progress on the Cloud Manager build page.
- The environment remains fully operational during indexing.

## Verification

After deployment and indexing completion, verify that the index is working correctly.

### Verify Index Deployment

In your development environment (if CRXDE Lite is available):

1. Navigate to `/oak:index/guidesAssetLucene-1-custom-1`.
2. Verify the node exists with the expected configuration.

### Test the Markup Search and Replace feature

The primary verification is testing the feature:

1. Open **AEM Guides**.
2. Navigate to **Tools** > **Guides** > **Find and Replace in Repository**.
3. Configure a search for text in your DITA or Markdown files.
4. Verify that search results are returned correctly.
5. Test the replace functionality on a test file.

## Best practices

- **Test in development first**: Always deploy to a development environment before production.
- **Monitor deployment**: Track the indexing progress through Cloud Manager notifications.
- **Version control**: Commit the index definition with clear commit messages.

## Additional resources

- [AEM as a Cloud Service Indexing Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing)
- [Apache Jackrabbit Oak Indexing Guide](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [AEM Guides Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-guides)
- [Cloud Manager Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)

## Support

If you encounter issues not covered in this guide:

1. **Review AEM logs**: Download and analyze environment logs from Cloud Manager.
2. **Check documentation**: Refer to Adobe Experience League for updated guidance.
3. **Contact Adobe support**: Open a support ticket with:
   - Environment details (Program ID, Environment ID)
   - Deployment logs
   - Error messages and symptoms
   - Steps to reproduce the issue
