---
title: Create translation project
description: Learn about creating API translation project
feature: Post-Processing Event Handler
role: Developer
level: Experienced
---
# Create translation project

A POST method that helps you create a translation project by accepting the required project details.

## Request URL

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/create`

## Request type

POST

## Request parameters

|Name|Type|Description|
|----|----|-----------|
|`type`|String|newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject|
|`versionDetails`, `versionSelector`|String|Baseline, latestVersion, versionAsOfDate|
|`language`|String|Comma separated languages "de", "fr"|
|`map.id`|String|GUID of the source map to be translated|
|`map.path`|String|Path of the source map to be translated|
|`referenceType`|String|Indirect, Direct|
|`fileType`|String|Map, Topic, Others|
|`documentState`|String|can be one of the lists assigned by user on map's profile|
|`translationStatus`|String|Out of Sync, In Sync, Up to Date, Out of Date, In Progress, Missing Copy, NONE, N/A|

>[!NOTE]
>
>You can either use `map.id` or `map.path` when creating a translation project.

## Request example

```JSON
{
  "title": "Test Project 1 on Dec 5",
  "type": "newTranslationProject",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en",
      "path": "/content/dam/ajay-test/lang/en/m2.ditamap"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "latestVersion"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
   ]

```

## Response values

```JSON

{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}

```

**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 internal server error

## Sample requests

### Add to existing project

``` json

{
  "title": "Add to existing Project",
  "type": "addToExistingProject",
  "path": "/content/projects/test_project_1_existing",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "versionAsOfDate",
      "version": "2025-12-05T10:30:00+01:30"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": [] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}

```

### Add to existing project with Baseline

``` json

{
  "title": "Add to existin project Project with baseline",
  "type": "addToExistingProject",
  "path": "/content/projects/existing_project_path",
  "translationDetails": {
    "map": {
      "id": "GUID-06527014-062d-46dc-8fea-48b4b4497c51-en"
    },
    "languages": ["de"],
    "versionDetails": {
      "versionSelector": "baseline",
      "version": "test1"
    }
  },
  "filterDetails": [
    { "name": "referenceType", "values": ["Direct"] },
    { "name": "fileType", "values": [] },
    { "name": "documentState", "values": [] },
    { "name": "translationStatus", "values": [] }
  ]
}

```

## Translation project creation status

A GET API that tracks the translation status for a newly created translation project.

## Request URL

`http://<aem-guides-server>:<port-number>/bin/guides/v1/translation/project/creationstatus`

## Request type

GET 

## Request parameters

|Name|Type|Description|
|----|----|-----------|
|`path`|String|Path of the project|
|`languageStatusMap`|String|For each requested language, returns completion status: In Progress, Completed, Failed, Skipped|


## Request example

``` json

{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}

```



