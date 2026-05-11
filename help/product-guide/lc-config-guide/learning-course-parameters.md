---
title: SCORM key metrics for Learner progress and Course completion
description: Learn about the SCORM key metrics for Learner progress and Course completion
feature: Authoring
role: Admin
level: Experienced
exl-id: f25cbbbd-5d9f-47b0-9260-8062e026913d
TQID: https://experienceleague.adobe.com/ZyY9sjaqGANXlUI5l3OsP-i1Pu-es-B-iGnpPJjQYrY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# SCORM key metrics for Learner progress and Course completion

The article lists the key parameters captured in a SCORM package, along with their corresponding fields, and examples. These parameters provide critical insights into learner progress, course completion, interaction details, and quiz performance. Administrators can use this information to validate tracking, configure reporting, and ensure accurate analytics within the LMS environment. Below are sample values provided for each parameter as it appears in the SCORM package.

|**Parameter name**|**Description**|**Fields** |**Example**|
|---|---|---|---|
|**Course completion status** | Indicates if the course is completed or not | cmi.completion_status | incomplete |
|**Attempt count** | Number of attempts made by the learner | LMS-side attempt counter/content | Attempts: 1 |
|**Location of SCORM package** | Current bookmark or location in the course | cmi.location | - |
|**Progress completion** | Learner's progress | cmi.progress_measure |0.87 |
|**Total time (attempt)** | Total time spent in the current attempt | cmi.total_time | 0000:01:09.87 |
|**TOC visibility and topic count** | Shows TOC visibility and topic completion details | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | - |
|**Per topic status** | Completion and pass status for each topic | Custom per-lesson state | - |
|**Per question choice state** | Tracks learner's selected choices per question | value, generated_id, checked | - |
|**Overall Question scoring** | Score achieved at question level and aggregate | {"score":0,"maxScore":1} and % | "score":33.33,"maxScore":100,"minScore":0 |
|**Interactions at each question level** | Details of learner interaction per question | id/type/timestamp/correct_response/learner_response/result/latency | - |
|**Overall course status** | Indicates pass/fail and overall progress | success_status, completion_status, score, progress_measure | Whether passed or failed |
|**Learner details** | Identifies learner by ID and name | cmi.learner_id, cmi.learner_name | Albert |
|**Quiz parameters** | Configurations for quiz timing and passing score | cmi.max_time_allowed, cmi.scaled_passing_score, cmi.time_limit_action | Undefined or configured values |
