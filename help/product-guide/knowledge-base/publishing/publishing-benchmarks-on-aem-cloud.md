---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
feature: Publishing
role: User, Admin
---
# AEM Guides Publishing Benchmarks on AEMaaCS

This benchmark evaluates the performance of the new Publishing APIs across different output presets and increasing map sizes in AEM Guides as a Cloud Service. The goal is to understand scalability behavior and identify performance bottlenecks.

The publishing service uses a [microservice-based architecture](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/publish-microservice-architecture-and-performance) with autoscaling, enabling handling of larger workloads through additional pods.

## Execution Environment

- **Environment**: author-p35602-e1337052.adobeaemcloud.com
- **Initial pod count**: 2 pods
- **Autoscaling behavior**: Scaled up to 4 pods across 4 nodes as load increased
- **vCPUs**: 10
- **RAM per pod**: 8 GB
- **Concurrent users**: 1 user

>[!NOTE]
>
> The benchmark was not intended to measure multi-user concurrency. The focus was on publishing behavior under increasing map size.


## Output generation numbers

**Native AEM Site**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 62.378             | Yes          |
| 100     | 64.27              | Yes          |
| 1000    | 93.091             | Yes          |
| 5000    | 496.319            | Yes          |
| 10000   | 922.602            | Yes          |

**Analysis**: Best observed performance is around load = 100–1000. Performance degrades beyond ~1000, with worst at 5000. 433% increase (93s→496s) between 1000→5000 – Major bottleneck.

**Native PDF**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 62.302             | Yes          |
| 100     | 62.431             | Yes          |
| 1000    | 108.666            | Yes          |
| 5000    | 201.379            | Yes          |
| 10000   | 1170.689           | Yes          |

**Analysis:** 85% increase (109s→201s) between 1000→5000 – Moderate degradation. Non-linear scaling observed at higher volumes.

**PDF**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 30.926             | Yes          |
| 100     | 30.987             | Yes          |
| 1000    | 77.007             | Yes          |
| 5000    | 247.505            | Yes          |
| 10000   | 686.61             | Yes          |

**Analysis**: 221% increase (77s→248s) between 1000→5000: Significant degradation.

**HTML5**

| MapSize | Execution Time (s) | Microservice |
| ------- | ------------------ | ------------ |
| 10      | 30.844             | Yes          |
| 100     | 30.834             | Yes          |
| 1000    | 77.384             | Yes          |
| 5000    | 170.237            | Yes          |
| 10000   | 419.166            | Yes          |

**Analysis:** Consistent increase with map size. 120% increase (77s→170s) between 1000→5000: Best scalability.
                          

## Key observations

- **Significant performance degradation at higher map sizes**: Native AEM Site and Native PDF show a sharp increase of approximately 433% and 481%, respectively, when map size increases from 1,000 to 5,000, indicating potential scalability bottlenecks that require further investigation.
- **No system errors observed during testing**: Analysis of Splunk logs indicates no major errors were recorded throughout the test duration, suggesting that the performance degradation is not due to runtime failures but likely related to resource or processing constraints.

