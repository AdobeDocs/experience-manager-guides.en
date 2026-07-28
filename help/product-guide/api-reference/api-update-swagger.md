---
title: API updates in Experience Manager Guides releases
description: Laern about the various API updates in Experience Manager Guides releases
--- 

# API updates in Experience Manager Guides releases

This article provides details of the newly added APIs in the Swagger documentation for Adobe Experience Manager Guides releases. You can access the Swagger documentation through the AEM interface by navigating to **Tools** > **Guides** > **API Swagger**.

<table style="border: 1; border-collapse: collapse; table-layout:fixed">
    <tr>
        <td colspan="5"><strong>Release 2026.08.0</strong></td>
    </tr>
    <tr>
        <td>Feature</td>
        <td>Sub-feature</td>
        <td>Method</td>
        <td>API</td>
        <td>Description</td>
    </tr>
    <tr>
        <td rowspan="7">Assets</td>
        <td rowspan="7"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/import`</td>
        <td>Imports one or more assets into a target folder; supports multipart upload and conflict resolution</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/list`</td>
        <td>Returns paginated list of assets under a folder path</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/validatexml`</td>
        <td>Validates DITA XML for well-formedness, schema validity, and conref integrity</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/asset/version/revert`</td>
        <td>Reverts an asset to a specified version</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/asset/currentversion/detail`</td>
        <td>Returns current version details (version name, dirty status, labels, etc.)</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/assets/status`</td>
        <td>Starts async job to check Guides status of assets under given path(s)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/assets/status`</td>
        <td>Retrieves status/results of an asset status job by job ID</td>
    </tr>
    <tr>
        <td rowspan="3">Publishing</td>
        <td rowspan="3"></td>
        <td>POST</td>
        <td>`/bin/guides/v1/output/generate`</td>
        <td>Starts preset execution to generate output for a map</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status`</td>
        <td>Returns status of a single output generation by map path and generation ID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/output/status/list`</td>
        <td>Returns status of all generated presets for a map path</td>
    </tr>
    <tr>
        <td rowspan="18">Translation</td>
        <td rowspan="6">Language</td>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/copies`</td>
        <td>Language copies of an asset by path or UUID</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/groups`</td>
        <td>Language groups for a folder profile</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/list`</td>
        <td>Supports translation languages (filtered)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/root`</td>
        <td>Root languages available for an asset path</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Language variables by type and language codes</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/language/variable`</td>
        <td>Creates, updates, or deletes language variables</td>
    </tr>
    <tr>
        <td rowspan="7">Project</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/create`</td>
        <td>Create/update translation project for a DITA map</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/project/sync`</td>
        <td>Creates/updates translation project (sync flow)</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/creationstatus`</td>
        <td>Translation sync status for a project by path</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/existing`</td>
        <td>Existing translation projects for current user</td>
    </tr>
    <tr>
        <td>GET</td>
        <td>`/bin/guides/v1/translation/project/inprogress`</td>
        <td>InProgress projects for a given asset</td>
    </tr>
    <tr>
        <td>DELETE</td>
        <td>`/bin/guides/v1/translation/project/delete`</td>
        <td>Pre-delete update of asset translation statuses/properties</td>
    </tr>
    <tr>
        <td>DELETE</td>
        <td>`/bin/guides/v1/translation/project/job/delete`</td>
        <td>Pre-delete update of asset statuses before job removal</td>
    </tr>
    <tr>
        <td rowspan="5">Reference</td>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/accept`</td>
        <td>Accept translated content from job child pages</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/reject`</td>
        <td>Reject translated content from job child pages</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/sync`</td>
        <td>Create language copies in destination folders</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/baseline/export`</td>
        <td>Export translation baseline to destination languages</td>
    </tr>
    <tr>
        <td>POST</td>
        <td>`/bin/guides/v1/translation/reference/status/forcesync`</td>
        <td>Force-update out-of-sync assets to in-sync</td>
    </tr>
</table>
