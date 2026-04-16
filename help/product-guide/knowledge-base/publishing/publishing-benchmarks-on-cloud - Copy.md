---
title: Guides Publishing Benchmarks on AEMaaCS
description: Understand system limits on Publishing on AEM Cloud.
feature: Publishing
role: User, Admin
---
# AEM Guides Publishing Benchmarks on AEMaaCS

This benchmark evaluates the performance of the new Publishing APIs across different output presets and increasing map sizes in an AEM Cloud author environment. The goal is to understand scalability behavior and identify performance bottlenecks.

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

| Sno. | Preset Type    | MapSize | Execution Time (s) | Microservice | Analysis                                                                                                                                                                        |
| ---- | -------------- | ------- | ------------------ | ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1    | Native AEM Site | 10      | 62.378             | Yes          | - Best observed performance is around load = 100–1000.<br>- Performance degrades beyond ~1000, with worst at 5000.<br>- 433% increase (93s→496s) between 1000→5000 – Major bottleneck |
| 2    | Native AEM Site | 100     | 64.27              | Yes          | Same as above                                                                                                                                                                   |
| 3    | Native AEM Site | 1000    | 93.091             | Yes          | Same as above                                                                                                                                                                   |
| 4    | Native AEM Site | 5000    | 496.319            | Yes          | Same as above                                                                                                                                                                   |
| 5    | Native AEM Site | 10000   | 922.602            | Yes          | Same as above                                                                                                                                                                   |
| 6    | Native PDF     | 10      | 62.302             | Yes          | - 85% increase (109s→201s) between 1000→5000 – Moderate degradation.<br>- Non-linear scaling observed at higher volumes                                                             |
| 7    | Native PDF     | 100     | 62.431             | Yes          | Same as above                                                                                                                                                                   |
| 8    | Native PDF     | 1000    | 108.666            | Yes          | Same as above                                                                                                                                                                   |
| 9    | Native PDF     | 5000    | 201.379            | Yes          | Same as above                                                                                                                                                                   |
| 10   | Native PDF     | 10000   | 1170.689           | Yes          | Same as above                                                                                                                                                                   |
| 11   | PDF            | 10      | 30.926             | Yes          | 221% increase (77s→248s) between 1000→5000 – Significant degradation                                                                                                            |
| 12   | PDF            | 100     | 30.987             | Yes          | Same as above                                                                                                                                                                   |
| 13   | PDF            | 1000    | 77.007             | Yes          | Same as above                                                                                                                                                                   |
| 14   | PDF            | 5000    | 247.505            | Yes          | Same as above                                                                                                                                                                   |
| 15   | PDF            | 10000   | 686.61             | Yes          | Same as above                                                                                                                                                                   |
| 16   | HTML 5         | 10      | 30.844             | Yes          | Consistent increase with map size.<br>120% increase (77s→170s) between 1000→5000 – Best scalability                                                                             |
| 17   | HTML 5         | 100     | 30.834             | Yes          | Same as above                                                                                                                                                                   |
| 18   | HTML 5         | 1000    | 77.384             | Yes          | Same as above                                                                                                                                                                   |
| 19   | HTML 5         | 5000    | 170.237            | Yes          | Same as above                                                                                                                                                                   |
| 20   | HTML 5         | 10000   | 419.166            | Yes          | Same as above                                                                                                                                                                   |


## Key observations

- **Significant performance degradation at higher map sizes**: Native AEM Site and Native PDF show a sharp increase of approximately 433% and 481%, respectively, when map size increases from 1,000 to 5,000, indicating potential scalability bottlenecks that require further investigation.
- **No system errors observed during testing**: Analysis of Splunk logs indicates no major errors were recorded throughout the test duration, suggesting that the performance degradation is not due to runtime failures but likely related to resource or processing constraints.

