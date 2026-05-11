---
title: Recommendations for performance optimization
description: Learn the Recommendations for performance optimization
exl-id: b2a836a0-de82-4d89-aae3-43276997da74
feature: Performance Optimization
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/6q077Ib1EIQ4AA51ktmZ966RZrSt08xJQh5t4llzgbQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
    internal-label: Administration and security
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Recommendations for performance optimization {#id213BD0JG0XA}

## Configure data store \(Mandatory\) 

**What is the change?**
Set the `minRecordLength` property to a value of `100` under the configuration `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` For more information about file date store and S3 data store, see the [Configuring node stores and data stores in AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html) article.

>[!NOTE]
>
> For S3 data store, the cost for maintaining content in data store depends on the number of requests as well. Therefore, when doing this setting with S3—setup cost per request and cache size should also be considered.

**When to configure?**
After the initial setup, but before any content is migrated. You must perform this change even on an existing system, which ensures that all new content is stored in data store instead of segment store.

**Result of this change**
The DITA files are saved in data store rather than the segment store. This keeps the segment store size under the recommended limits, which improves the responsiveness of the system.

## Update Lucene index \(Mandatory\) 

**What is the change?**
Exclude /var/dxml from oak:index/lucene.

>[!NOTE]
>
> AEM Guides never uses Lucene indexes to search for content in /var/dxml node.

**When to configure?**
If you are making this change on a new system before migrating content, then only updating oak:index/lucene is required. Otherwise, on an existing system where the content is already migrated, then after making the change in oak:index/lucene, rebuild indexes for Lucene \(*which might take few hours to complete*\).

**Result of this change**
This change prevents /var/dxml node from getting indexed and stored in the segment store.

## Java memory optimization \(Mandatory\) 

**What is the change?**
The JVM start parameters should be carefully tuned based on the infrastructure and the disk size. It is recommended that you consult Adobe Support to get help to access the ideal configuration. You may, however, try out the following configurations yourself:

– Set the JVM heap size to a minimum of 1/4th of the total available memory. Use the parameter `-Xmx<size>` to set the heap memory size. Set the value for -`Xms` equals to `-Xmx`.

– Enable `-XX:+HeapDumpOnOutOfMemoryError` and set the path for `-XX:HeapDumpPath=</path/to/folder``>`.

– Enable Java GC log as:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

– In general, for Java 11, use G1GC \(`-XX:+UseG1GC`\) and for Java 8 use CMS \(-`XX:+UseConcMarkSweepGC`\).

– Use `-XX:NewRatio` to control the size of young generation memory size. The default value is 2, which means that 1/3 of the memory is used for young generation. Since there are many objects getting quickly created and destroyed, using a value of 1 will allocate 1/2 of the memory to young generation.

– Control the number of objects being promoted to old generation using `-XX:MaxTenuringThreshold`. Use the value of 15 \(default\) to delay when objects are promoted to old generation.

**When to configure?**
If you are making this change on an existing system, you need to restart the system. In case of a fresh installation, this change should be made in the start script \(.bat or .sh\) file before the system is started.

**Result of this change**
This results in optimal heap size and regulated execution of GC.

## Client library minification on Author instance \(Optional\) 

**What is the change?**
The client libraries should be set to minify in the Authoring instances. This makes sure that there are fewer bytes to download when a user is browsing the system from different locations. To make this change, set the configuration in **HTML Library Manager** from the Felix console.

**When to configure?**
This can be done at run time through Felix console or via code deployment.

**Result of this change**
This change improves the load time of pages on Author instance as fewer bytes are transferred for loading the client libraries.

## Configure concurrent publishing threads \(Mandatory, depending on the use case\) 

**What is the change?**
This change is required if you are using DITA-OT to publish output and a number of concurrent publishing threads is also defined.

By default, AEM Guides sets the publishing threads to the number of CPUs+1. However, it is recommended to set this value to half \(1/2\) or one-third \(1/3\) of the total number of CPUs. To do this, set the **Generation Pool Size** property under the configuration `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` as per the recommendations.

**When to configure?**
This can be done at run time through Felix console or via code deployment.

**Result of this change**
This change ensures that on a running Author instance all resources are not allocated for the publishing operations. This keeps the system resources available for authors as well, which results in a better user experience.

## Configure batch size of nodes for AEM Site output generation \(Mandatory, depending on the use case\) 

**what is the change?**
This change is required if you are generating AEM Sites output.

Set the **Limit AEM Site Pages in Heap** property under `com.adobe.fmdita.config.ConfigManager` to a number based on your system's configuration. This property defines the batch size of nodes to be committed when the site pages are generated. For example, on a system with a larger number of CPUs and heap size, you can increase the default value from `500` to a larger number. You need to test run with the changed value to come to an optimal value for this property.

**When to configure?**
This can be done at run time through Felix console or via code deployment.

**Result of this change**
An increased number of the **Limit AEM Site Pages in Heap** property optimizes the AEM Site output generation process.


**Parent topic:**[Download and install](download-install.md)
