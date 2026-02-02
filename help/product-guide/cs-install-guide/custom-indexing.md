---
title: Custom indexing deployment 
description: Learn how to custom index content
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Deploying custom index for Find and replace (Source view) feature

## Overview

This guide provides step-by-step instructions for deploying the `guidesAssetLucene‑1‑custom‑1` custom index on Adobe Experience Manager (AEM) as a Cloud Service. While the standard Find and replace feature in the Author view works without this index, the custom index is specifically required to enable Find and replace in the Source view. The Find and replace (Source view) allows you to search not only the visible authored content but also the underlying XML structure; including elements, tags, and attribute values.

## Prerequisites

Before proceeding with the index deployment, ensure you have:

- **AEM as a Cloud Service environment** with AEM Guides installed
- **Access to your project's codebase** (Git repository)
- **Cloud Manager access** with deployment permissions

## Index definition

To enable the Find and replace (Source view) feature, you need to deploy a custom index named **`guidesAssetLucene-1-custom-1`** to your AEM Cloud Service environment.

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
          reindexCount="{Long}1"
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
                <dcTitleLowerCase
                        jcr:primaryType="nt:unstructured"
                        function="fn:lower-case(jcr:first(jcr:content/metadata/@dc:title))"
                        propertyIndex="{Boolean}true"
                        ordered="{Boolean}true"/>
                <dcTitle
                        jcr:primaryType="nt:unstructured"
                        name="jcr:content/metadata/dc:title"
                        propertyIndex="{Boolean}true"/>
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

When following the deployment guide, use the following specifics for the Find and replace index:

- **Index name**: `guidesAssetLucene-1-custom-1`
- **Index type**: Fully custom index (not a customization of OOTB index)
- **Location**: `ui.apps/src/main/content/jcr_root/_oak_index/guidesAssetLucene-1-custom-1/.content.xml`
- **Package Properties Required**:
  - `noIntermediateSaves=true`
  - `allowIndexDefinitions=true`

## Reindexing

Reindexing is handled **automatically** by AEM as a Cloud Service when you deploy the index through Cloud Manager's CI/CD pipeline. 

Indexing is typically handled automatically. However, if the old data remains unsearchable even after correct deployment and the completion of the indexing process, a manual re‑index of the index should be performed once.

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

### Test the Find and replace feature

The primary verification is testing the feature:

1. Open **AEM Guides**.
2. Navigate to **Tools** > **Guides** > **Find and Replace in Repository**.
3. Configure a search for text in your DITA or Markdown files.
4. Verify that search results are returned correctly.
5. Test the replace functionality on a test file.

## Additional resources

- [AEM as a Cloud Service Indexing Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/operations/indexing)
- [Apache Jackrabbit Oak Indexing Guide](https://jackrabbit.apache.org/oak/docs/query/indexing.html)
- [AEM Guides Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-guides)
- [Cloud Manager Documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager)
