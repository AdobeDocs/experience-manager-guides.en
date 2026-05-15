---
title: FAQ about Publishing Performance and Scalability in Adobe Experience Manager Guides
description: Learn about the frequently asked questions on Publishing Performance and Scalability in Adobe Experience Manager Guides.
exl-id: d4cd7673-ba66-4e90-9908-b537217d7eb6
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
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
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
    internal-label: Bulk activation
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
    internal-label: Conditional content
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# FAQ 

The following is a list of answers to frequently asked questions that provides detailed insights into how Adobe Experience Manager Guides manages publishing workflows, scaling behavior, and infrastructure performance. It is intended for enterprise users, administrators, and documentation teams using Experience Manager Guides for large-scale publishing. The diagram explains the overall workflow of Experience Manager Guides Publishing Architecture.

![](images/IO_runtime.drawio.png)


## How many publishing requests can Experience Manager Guides run per day?

The number of publishing requests Experience Manager Guides can process per day depends on the size and type of content. As per the configuration, the system allows one publishing job per processor core. In the current setup, 20 publishing jobs can run in parallel (2 pods × 10 cores each).

As the production environment auto-scales, this number can increase to 40 concurrent publishing jobs when the pods scale up to 4. 

## How many publishing requests can run concurrently before they are queued?

- Minimum (default): 20 publishing jobs (2 pods)
- Maximum (scaled): 40 publishing jobs (4 pods)

This number may vary based on overall server load. If other background Sling jobs are running, they share processing cores, potentially reducing the concurrency to below 20.

## Does running multiple publishing requests impact other application functionalities such as editing .dita files?

There may be some performance impact, but it is generally minimal. Most heavy processing occurs on the IO runtime (serverless publishing service), while the AEM instance primarily performs I/O operations for dependency generation and status polling. As a result, CPU utilization within AEM remains low, and authoring/editing experiences are largely unaffected.

## How does Experience Manager Guides manage large files and graphics such as SVGs or .dita files exceeding 500 KB?

All large files are zipped and stored in the JCR (Java Content Repository). The IO runtime fetches the complete zip package before initiating publishing. Even when handling multiple large files (e.g., 500 KB each), this does not significantly affect download or transfer speed because of optimized packaging and parallel I/O handling. 

## What is the publishing infrastructure and configuration used by Experience Manager Guides?

Experience Manager Guides uses containerized, serverless microservices for publishing. Each new version of the publishing service is released as a Docker image, automatically deployed in Adobe's cloud environment. This design ensures:

- No dedicated infrastructure maintenance for customers
- Automatic scaling to handle publishing demand
- Fast updates and minimal downtime

## If the publishing queue or management system crashes due to overload, will other AEM functionalities be affected?

No, the Experience Manager Guides is built with a fault-tolerant architecture. If the publishing queue experiences overload, requests are automatically retried, and pods auto-scale to handle the additional load. Beyond a certain threshold, load throttling is applied to maintain stability. Other application areas (authoring, reviewing, asset management) remain unaffected.

## Is there a monitoring tool or log access available to identify when Experience Manager Guides is under heavy load (similar to Jenkins monitoring)?

No, currently you do not have access to internal monitoring tools. For Adobe internal teams, monitoring can be done using:

- Splunk for log and error tracking
- Kubernetes (K8s) CLI for checking pod-level performance and scaling behavior

If performance degradation is noticed, customers should contact Adobe Support to initiate investigation and analysis.

## What processing is done before dispatching a publishing request to the microservice?

When you trigger a publishing request from the Presets tab in the Map console, the following steps occur:

1. The system accepts the request and validates the baseline and conditional presets.
2. AEM aggregates all qualifying DITA assets and dependencies.
3. These assets are bundled into a zip package.
4. The serverless publishing service spins up a Docker container, downloads the assets, executes the publishing operation, and places the generated output artefacts back into Experience Manager Guides.

This workflow ensures reliable, isolated, and scalable publishing execution.

## How much time does a map take before it starts publishing on the microservice container and what are the factors that define this time?

A publishing request typically takes a few minutes before it is dispatched to the microservice container. This initial time is used for dependency aggregation within AEM.

Once the request is received on the serverless publishing service, the total publishing time depends on:

- Size of the DITA map
- Number of topics and media assets
- Complexity of conditional content and formatting rules

Larger or more complex maps may take proportionally longer to publish.

## Can Experience Manager Guides prioritize publishing requests in the queue (instead of First-Come, First-Serve)?

Currently, all publishing jobs are treated equally and follow a First-Come, First-Serve (FCFS) model. There is no prioritization mechanism available currently.

However, in future releases, prioritization logic (for example, based on job size or business importance) could be introduced as a part of queue optimization enhancements.

## How does Experience Manager Guides handle auto-scaling for publishing requests?

Experience Manager Guides publishing infrastructure supports automatic scaling based on load. When publishing demand increases:

- Additional pods (containers) are automatically spun up.
- Each pod can process multiple publishing jobs in parallel.
- Once the load decreases, pods scale down to optimize cost and performance.

This ensures high availability, consistent performance, and minimal queue time during peak load.

## What happens if a publishing job fails or times out?

If a publishing request fails due to a transient issue (for example, network interruption, service timeout):

- it is automatically retried based on retry logic configured in the publishing service.
- logs and error messages are captured in the backend for diagnostic purposes.
- you can view failure status and retry publishing manually from the Map console if needed.

## Can you monitor or track the progress of a publishing job?

Yes, Experience Manager Guides provides real-time job status updates in the Presets tab of the Map console, including:

- Job start and completion time
- Current stage (zipping, dispatching, publishing, or uploading results)
- Error notifications (if any)

This helps you understand job progress and identify potential delays.

## What best practices can improve publishing performance in Experience Manager Guides?

To ensure optimal publishing speed, follow these best practices:

- Avoid unnecessary large image files or unreferenced topics
- Use baselines to limit the scope of publishing
- Keep DITA map hierarchies manageable and well-organized
- Schedule heavy publishing during off-peak hours
- Use conditional filters effectively to reduce processing load
