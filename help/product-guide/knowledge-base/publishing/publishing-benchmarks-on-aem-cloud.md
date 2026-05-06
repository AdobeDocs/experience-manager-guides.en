---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
feature: Publishing
role: User, Admin
---
# AEM Guides Publishing Benchmarks on AEMaaCS

This benchmark evaluates the performance of the new publishing APIs across different output presets and increasing map sizes in AEM Guides as a Cloud Service. The goal is to understand scalability behavior and identify performance bottlenecks.

The publishing service uses a [microservice-based architecture](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) with autoscaling, enabling handling of larger workloads through additional pods.

## Execution environment

- **AEM release**:2026.4.25322.20260407T085152Z
- **Guides Add-on release**: 2026.5.0
- **Initial pod count**: 2 pods
- **Autoscaling behavior**: Scaled up to 4 pods across 4 nodes as load increased
- **vCPUs**: 10
- **RAM per pod**: 8 GB
- **Concurrent users**: 1 user

>[!NOTE]
>
> This exercise focused on how publishing behaves as map size increases, highlighting the impact of larger maps on throughput, latency, and overall publish completion under load.


## Output generation numbers

**Native AEM Site**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 62.378             | Yes          |
| 100     | 64.27              | Yes          |
| 1000    | 93.091             | Yes          |
| 5000    | 496.319            | Yes          |
| 10000   | 922.602            | Yes          |

**Native PDF**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 62.302             | Yes          |
| 100     | 62.431             | Yes          |
| 1000    | 108.666            | Yes          |
| 5000    | 201.379            | Yes          |
| 10000   | 1170.689           | Yes          |

**PDF**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 30.926             | Yes          |
| 100     | 30.987             | Yes          |
| 1000    | 77.007             | Yes          |
| 5000    | 247.505            | Yes          |
| 10000   | 686.61             | Yes          |

**HTML5**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 30.844             | Yes          |
| 100     | 30.834             | Yes          |
| 1000    | 77.384             | Yes          |
| 5000    | 170.237            | Yes          |
| 10000   | 419.166            | Yes          |

 
## Key observations

- AEM Site generation time depends on the template being used. Execution time may increase if a complex template is used.
- Custom publishing execution time is based on a sample custom output. Custom publishing time solely depends on customer's own transformation logic. 