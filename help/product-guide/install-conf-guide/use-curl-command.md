---
title: Use curl commands
description: Learn how to use curl commands on the uploaded content in Experience Manager Guides.
feature: Migration
role: Admin
level: Experienced
exl-id: 7772246c-f885-46c0-a1e5-915d111bbc61
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: 5be0fc8f-1cff-5c3e-bb92-2903a56a3de6
    internal-label: Migration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Use curl commands

You can also use curl commands to create a folder in DAM, upload files, and add metadata on the uploaded content.

## Create a folder

Run the following command to create a folder in AEM repository:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Specify the following parameters to create a folder:

-   `<username>:<passowrd>`: Specify the user name and password to access the AEM repository. This user must have the folder creation privileges.

-   `jcr:primaryType=sling:Folder`: Specify this parameter *as is* to create a folder type resource.

-   `<server folder path>`: Complete folder path including the name of the new folder that you want to create in the AEM repository. For example, if you specify the path as `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, then the folder `AEM-Guides` is created within the `projects` folder in DAM.


## Upload a file

Run the following command to upload a file in the AEM repository:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Specify the following parameters to upload a file:

-   `<username>:<passowrd>`: Specify the user name and password to access the AEM repository. This user must have write privileges on the `server folder path`.

-   ``local file path``: Complete file path on your local system that you want to upload.

-   `<server folder path>`: Complete folder path on the AEM server where you want to upload the file.


## Add metadata

Run the following command to add metadata on a file:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Specify the following parameters to add metadata information:

-   `<username>:<passowrd>`: Specify the user name and password to access the AEM repository. This user must have write privileges on the ``metadata node path``.

-   ``-F<attribute name>=<value>``: The `<attribute name>` is the name of the metadata attribute, such as `audience` and the `<value>` could be `internal`. You can specify multiple attribute name-value pairs separated by space.

-   `<metadata node path>`: Complete folder path including the file name and its metadata node. For example, if you specify the path as `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, then the specified metadata information is set on `intro.xml` file.
