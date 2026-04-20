---
title: FAQ about Publishing Performance and Scalability in Adobe Experience Manager Guides
description: Learn about the frequently asked questions on Publishing Performance and Scalability in Adobe Experience Manager Guides.
---

# Asset Processing

Asset Processing is a critical workflow responsible for ensuring that content assets are structured, validated, indexed, and made accessible within the platform. With evolving scalability demands and cloud-native requirements, the architecture has undergone a significant transformation from a single-threaded, hierarchical processing model to a distributed, graph-enabled, multi-threaded system.

## Current Asset Processing Flow

### Processing Overview

When an asset is imported into Experience manager Guides, the following sequential processing steps are executed:

- Unique Key Assignment: Each document is assigned a unique identifier to ensure traceability and reference integrity.
- Parsing: Content (e.g., DITA XML) is parsed into structured components for system-level understanding.
- Validation: Structural and schema validation ensures compliance with document standards.
- Reference Resolution: Cross-references (links, images, dependencies) are resolved across assets.
- Metadata Extraction: Metadata such as title, author, and custom attributes are extracted for indexing and search.
- Reprocessing on Modification: Incremental reprocessing ensures consistency after content updates.

### Architectural characteristics

- **Single-Threaded Processing**: Prevents corruption of JCR (Java Content Repository) structures, which rely on B-Tree implementations.This ensures data integrity but introduces processing bottlenecks during bulk ingestion.

- **Parent-Map Dependency**: Maintains hierarchical relationships between assets using graph traversal. This is an intensive operations with high latency during large-scale processing with increased computational overhead, and strain due to traversal-heavy operations.

## New asset processing flow

The core processing steps remain functionally consistent but are now executed within a distributed and parallelized framework, significantly improving throughput.

### Architectural enhancements

- **Graph database integration**:
    - Transition from hierarchical JCR to a native graph database
    - Enables efficient handling of relationships and dependencies
    - Eliminates complexity of simulating graph operations on hierarchical storage
- **Multi-Threaded distributed processing**: 
    - Processing is executed across multiple pods in a cloud environment
    - Removes dependency on a single leader node
    - Enables horizontal scalability and parallel execution  
- **Elimination of Parent-Map Dependency:**
    - Removes need for explicit graph traversal
    - Reduces I/O operations and processing latency
    - Simplifies processing pipeline
- **Synchronized Unique ID Allocation**
    - Centralized coordination ensures:
    - No duplication of document IDs
    - Consistency across distributed nodes
    - Maintains referential integrity in a concurrent environment
- **Cloud-Native Scalable Database (AWS Hosted)**
    - Highly available and resilient database layer
    - Supports elastic scaling based on workload
    - Improves overall system reliability and performance 

## Advantages of the new architecture

- Performance improvements:
    - Parallel execution significantly reduces processing time
    - Elimination of traversal-heavy operations lowers latency
    - Optimized graph handling improves dependency resolution speed
- Scalability:
    - Horizontal scaling across pods enables handling of large ingestion volumes
    - Cloud-native infrastructure adapts dynamically to workload demands
- Reliability & availability:
    - Distributed processing removes single point of failure
    - AWS-hosted database ensures high availability and fault tolerance
- Efficiency gains:
    - Reduced I/O overhead due to removal of parent-map traversal
    - Better resource utilization across compute nodes
- Data integrity:
    - Synchronized ID allocation maintains consistency across distributed systems
    - Retains robustness while enabling concurrency

## Configure database

Experience Manager Guides enables streamlined database configuration for AEM Cloud environments. To set up the database for your AEM Cloud instance, perform the following steps:

1. Access the AEM Cloud Manager: Navigate to Adobe Experience Cloud Manager using the URL below, replacing the placeholders with your organization, program, and environment details: `https://experience.adobe.com/#/${orgName}/cloud-manager/environments.html/program/${programId}/environment/${envId}` 

1. Configure the Environment: After you open the environment configuration page through Cloud Manager, you will be able to adjust the settings specific to your instance, including setting up the required database configurations.

This streamlined approach ensures easy access and configuration for AEM environments within the Adobe cloud infrastructure.

1. Configure the below properties:


| Property Name                     | Value                          | Service Applied | Type     |
|----------------------------------|--------------------------------|-----------------|----------|
| DATABASE_URL                     | `<host>:<port>/<db_name>`        | Author          | Variable |
| GUIDES_ENABLE_DATABASE           | `true`                          | Author          | Variable |
| DATABASE_PASSWORD                | `password`                     | Author          | Secret   |
| DATABASE_USERNAME                | `username`                     | Author          | Variable |
| RUN_POSTPROCESS_IN_PHASES        | `true`                           | Author          | Variable |
| DATABASE_CONNECTION_POOL_SIZE    | `10`                             | Author          | Variable |


1. Save Changes: After making the configuration changes, ensure you **save** them within the Cloud Manager interface.

1. System Availability: Once the configurations are fully applied, open GET `http://host/bin/guides/v1/system/status` and check for below properties:
    - `<isDatabase>`: must be true
    - `<databaseConnectionCheck>`: must be passed
    
     If the above values are correct in the response, the system is available to be used with the newly configured database.

By following this process, you'll have a properly set up and ready-to-use AEM cloud environment.

>[!NOTE]
>
> If you are migrating to an existing environment with pre-existing content, you must first execute the Phase 2 (Migrate existing content) before ingesting any new content. This is to ensure that temporary GUIDs are assigned correctly for the new content.

## Ingest data in AEM DAM (Cloud Environment) (Phase 1)

For setting up a new folder in AEM DAM (Digital Asset Manager), ingesting data, and comparing it with a JCR-based environment follow the below steps.

1. Create a new folder in DAM.

2. Ingest data using the Data Upload Tool: For details, view the **Uploading Assets to AEM Cloud**.

3. Verify the system
   - Once the upload completes, verify that the assets are present in DAM.
   - Ensure that metadata (such as file types, descriptions, and tags) has been extracted and associated with the assets.
   - Check Experience Manager Guides processing (multi-threaded) to confirm that all references, metadata extraction, and validations were successful.
   - Test accessing and editing a document to confirm system integrity.

4. Comparison with JCR-based environment
   - Compare results across various test cases.
   - Evaluate ingestion speed.


To migrate content that was uploaded and processed before switching Experience Manager Guides to a database-based setup, a migration script can be used. The script leverages a set of APIs to initiate and monitor the migration process. The following steps outline the recommended approach.

## Migrate content from JCR to database (Phase 2)

To migrate content that was uploaded and processed before switching Experience Manager Guides to a database-based setup, you must use a migration script. The script leverages a set of APIs to initiate and monitor the migration process. The following steps outline the recommended approach. 

1. Trigger the migration API using any REST client.
2. Check the migration progress.
3. Monitor the migration until completion: Continue monitoring until the progress API reports 100% completion. Once complete, all previously uploaded and processed content from the JCR repository is migrated to the database.

    >[!NOTE]
    >
    > - Ensure that the required authorization headers (such as OAuth tokens, API keys, or access tokens from the developer console) are included to authenticate requests with AEM.
    > - Migration duration depends on the size of the content repository. Periodic progress checks are recommended, along with monitoring for errors or interruptions.
    > - Review migration logs, if available, to assess migration performance and identify any issues.

4. To support migration for large repository sizes, follow the below configuration

    >[!NOTE]
    >
    > Apply this configuration only if repository traversal errors are encountered during migration.

    `file name: `org.apache.jackrabbit.oak.query.QueryEngineSettingsService.xml``

    ```xml

    <?xml version="1.0" encoding="UTF-8"?>
    <jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0"
          xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          queryLimitInMemory="5000000"
          queryLimitReads="1000000"
    />
    ```


## Migration API

### Start migration

- endpoint: `POST /bin/guides/v1/assets/process`
- request body: (`application/json`):

```json
  {
    "path": "/content/dam/dita-templates",
    "excludedPaths": [
      "/content/dam/demo",
      "/content/dam/demo1"
    ],
    "type": "ASSET_PROCESSING"
  }

```

- returns the processingId for the migration.
- triggers the asset processing workflow built into the product.

### Check migration status

endpoint: `GET /bin/guides/v1/assets/process/status?processingId=<processingId>`

### Cancel a running migration

- endpoint: `POST /bin/guides/v1/assets/process/cancel`
- request body (application/json):

    ```

    {
     "processingId": "processingId"
    }
    ```

### Resume a failed or cancelled migration

- endpoint: `POST /bin/guides/v1/assets/process/resume`
- request body (application/json):

    ```

    {
     "processingId": "processingId"
    }
    ```

## Upload assets to AEM cloud

Adobe Experience Manager (AEM) as a Cloud Service provides multiple approaches for bulk content ingestion. To ensure optimal performance, particularly for Experience Manager Guides post-processing, it is essential to adopt a supported and scalable ingestion strategy.

### Bulk ingestion using cloud storage integrations

AEM supports bulk content ingestion through supported cloud storage providers, allowing organizations to connect their preferred storage solution and import content directly into AEM. This approach is recommended for large-scale and performance-sensitive ingestion due to the following benefits:

- Scalable infrastructure: The ingestion process runs on Adobe-managed cloud infrastructure, enabling automatic scaling based on load and content volume. This ensures consistent ingestion performance even for large datasets.

- Predictable ingestion planning: Users can estimate ingestion duration in advance, which helps with release planning, scheduling, and coordination with dependent teams.

- Comprehensive logging and tracking: The ingestion workflow includes detailed logging and tracking capabilities, providing visibility into progress, success states, and potential issues throughout the import process.

- Scheduled ingestion: Content ingestion can be scheduled to occur during predefined time windows, ensuring minimal or no impact on end users and ongoing operations.

For more information, view [Using Bulk Import](https://experienceleague.adobe.com/en/docs/experience-manager-learn/cloud-service/migration/bulk-import).

## Bulk ingestion using AEM upload

AEM also provides [AEM upload](https://github.com/adobe/aem-uploa), a library and Command-Line Interface (CLI) that enables users to ingest content directly from a local file system. This option can be integrated into custom solutions or used as a standalone CLI tool to upload content.

Because this approach runs on the users local machine, it requires a stable and uninterrupted network connection to ensure a reliable and seamless ingestion experience.


## Health check for Experience Manager Guides database connectivity

Experience Manager Guides deployments that are configured to use a database require stable and consistent database connectivity to operate reliably. Verifying the database connection status is a key health check step to rule out connectivity-related issues that may impact system functionality.

This health check allows users to confirm whether the database is configured, reachable, and functioning as expected. To check the DB connection status follow the below steps.

1. Open any browser or REST client
2. Trigger a GET call using this [URL](https://host:port/bin/guides/v1/system/status)
3. The below fields can be used to determine the system configuration and health status
    1. isDatabase: 
        - true: environment is configured with database.
        - false: environment is not using database

    2. databaseConnectionCheck: 
        - passed: Experience Manager Guides will check for connection status and if Guides is able to connect with database it will return status as passed.
        - failed: Environment is not able to communicate with database. Customers should immediately stop using the system and should reach out to Adobe support.

## Log Monitoring

Experience Manager Guides with Database efficiently logs the details to give an insight into the system state. 
Use the below queries in Splunk to get logs for different scenarios. 

1. Migration logs:
    - `index IN ("dx_aem_engineering") aem_service=cm-${programid}-${environmentId} sourcetype=aemerror "AssetProcessingJob" OR "AssetJobProducerDb" NOT "ServiceEvent"`
2. Post-Processing logs:
    - `index IN ("dx_aem_engineering") aem_service= cm-${programid}-${environmentId} sourcetype=aemerror com.adobe.fmdita.uuid.concrete.Cor*`


>[!NOTE] 
>
> Read more about [Splunk querying capabilities](https://www.splunk.com/en_us/blog/learn/splunk-cheat-sheet-query-spl-regex-commands.html) to filter these logs based on time duration, log level or for searching some specific patterns. 
   







   

