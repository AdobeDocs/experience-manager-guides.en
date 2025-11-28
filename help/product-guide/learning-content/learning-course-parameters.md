---
title: SCORM key metrics for Learner progress and Course completion
description: Learn about the SCORM key metrics for Learner progress and Course completion
feature: Authoring
role: Admin
level: Experienced
---
# SCORM key metrics for Learner progress and Course completion

The following table lists the key parameters captured in a SCORM package, along with their corresponding fields, and examples. These parameters provide critical insights into learner progress, course completion, interaction details, and quiz performance. Administrators can use this information to validate tracking, configure reporting, and ensure accurate analytics within the LMS environment.

|**Parameter name**|**Description**|**Fields** |**Example**|
|---|---|---|---|
|**Course completion status** | Indicates if the course is completed or not | cmi.completion_status | incomplete |
|**Attempt count** | Number of attempts made by the learner | LMS-side attempt counter/content | Attempts: 1 |
|**Location of SCORM package** | Current bookmark or location in the course | cmi.location | - |
|**Progress measure** | Learner's progress as a decimal value | cmi.progress_measure |0.87 |
|**Total time (attempt)** | Total time spent in the current attempt | cmi.total_time | 0000:01:09.87 |
|**TOC visibility and topic count** | Shows TOC visibility and topic completion details | Project.HideTOC, Project.TotalTopics, Project.TopicsCompleted | {"Project.HideTOC":false,"Project.TotalTopics":8,"Project.TopicsCompleted":7} |
|**Per topic status** | Completion and pass status for each topic | Custom per-lesson state | lesson2.html: {"completed":true,"passed":true} |
|**Per question choice state** | Tracks learner's selected choices per question | value, generated_id, checked | {"value":"generated_id0_1_2_1_2","checked":false} |
|**Overall Question scoring** | Score achieved vs maximum score | {"score":0,"maxScore":1} and % | "score":33.33333333333333,"maxScore":100,"minScore":0 |
|**Interactions at each question level** | Details of learner interaction per question | id/type/timestamp/correct_response/learner_response/result/latency | - |
|**Overall course status** | Indicates pass/fail and overall progress | success_status, completion_status, score, progress_measure | Whether passed or failed |
|**Learner details** | Identifies learner by ID and name | cmi.learner_id, cmi.learner_name | Albert |
|**Quiz parameters** | Configurations for quiz timing and passing score | cmi.max_time_allowed, cmi.scaled_passing_score, cmi.time_limit_action | Undefined or configured values |