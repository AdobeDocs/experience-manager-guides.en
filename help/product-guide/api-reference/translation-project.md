---
title: Create translation project
description: Learn about creating API translation project
feature: Post-Processing Event Handler
role: Developer
level: Experienced
---
# Create translation project

## API Endpoint 

POST  /bin/guides/v1/translation/project/create

``` json

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


### Parameters

|Name|Type|Description|
|----|----|-----------|
|`type`|String|newTranslationProject, xliffTranslationProject, newMultiLingualTranslationProject, addToExistingProject, newScopingTranslationProject|
|`versionDetails`, `versionSelector`|String|Baseline, latestVersion, versionAsOfDate|
|`language`|String|Comma separated languages "de", "fr"|
|`map.id`|Integer|GUID of the source map to be translated|
|`map.path`|String|Path of the source map to be translated|
|`referenceType`|String|Indirect, Direct|
|`fileType`|String|Map, Topic, Others|
|`documentState`|String|can be one of the lists assigned by user on map's profile|
|`translationStatus`|String|Out of Sync, In Sync, Up to Date, Out of Date, In Progress, Missing Copy, NONE, N/A|

## API Response

``` json

{
  "executionId": "5c13c571-3407-46d5-8f45-50ea9e05a212",
  "path": "/content/projects/test_project_1_ondec5"
}

```

### Parameters

|Name|Type|Description|
|----|----|-----------|
|`executionId`|String|Unique ID of the translation job creation (used to track project creation status)|
|`path`|String|Path where project is created|


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

## Fetch Translation Project Creation Status

## Status API Endpoint

GET /bin/guides/v1/translation/project/creationstatus

## Request body

path : /content/projects/test_project_1_ondec5

## API response

``` json

{
  "path": "/content/projects/test_project_1_ondec5",
  "languageStatusMap": {
    "de": "Completed"
  }
}

```

### Parameters

|Name|Type|Description|
|----|----|-----------|
|`path`|String|Path of the project|
|`languageStatusMap`|String|For each requested language, returns completion status: In Progress, Completed, Failed, Skipped|


