# APIs in the 2026.08.0 release

This article lists the new APIs added to the public Swagger documentation for Adobe Experience Manager Guides as a Cloud Service in the 2026.08.0 release. These operations extend the Assets, Publishing, and Translation external specs, giving developers programmatic access to import and validation workflows, output generation status, and the full set of v1 translation operations.

# APIs in this release

This article lists the new APIs added to the public Swagger documentation for Adobe Experience Manager Guides as a Cloud Service. These operations extend the Assets, Publishing, and Translation external specs, giving developers programmatic access to import and validation workflows, output generation status, and the full set of v1 translation operations.

**Release 2026.08.0**

|Feature | Sub-feature | Method | API | Description |
|---|---|---|---|---|
|Assets | | POST | `/bin/guides/v1/asset/import` | Imports one or more assets into a target folder; supports multipart upload and conflict resolution |
| | | POST | `/bin/guides/v1/asset/list` | Returns paginated list of assets under a folder path |
| | | POST | `/bin/guides/v1/asset/validatexml` | Validates DITA XML for well-formedness, schema validity, and conref integrity |
| | | POST | `/bin/guides/v1/asset/version/revert` | Reverts an asset to a specified version |
| | | GET | `/bin/guides/v1/asset/currentversion/detail` | Returns current version details (version name, dirty status, labels, etc.) |
| | | POST | `/bin/guides/v1/assets/status` | Starts async job to check Guides status of assets under given path(s) |
| | | GET | `/bin/guides/v1/assets/status` | Retrieves status/results of an asset status job by job ID |
| Publishing | | POST | `/bin/guides/v1/output/generate` | Starts preset execution to generate output for a map |
| | | GET | `/bin/guides/v1/output/status` | Returns status of a single output generation by map path and generation ID |
| | | GET | `/bin/guides/v1/output/status/list` | Returns status of all generated presets for a map path |
| Translation | Language | GET | `/bin/guides/v1/translation/language/copies` | Language copies of an asset by path or UUID |
| | | GET | `/bin/guides/v1/translation/language/groups` | Language groups for a folder profile |
| | | GET | `/bin/guides/v1/translation/language/list` | Supports translation languages (filtered) |
| | | GET | `/bin/guides/v1/translation/language/root` | Root languages available for an asset path |
| | | GET | `/bin/guides/v1/translation/language/variable` | Language variables by type and language codes |
| | | POST | `/bin/guides/v1/translation/language/variable` | Creates, updates, or deletes language variables |
| | Project | POST | `/bin/guides/v1/translation/project/create` | Create/update translation project for a DITA map |
| | | POST | `/bin/guides/v1/translation/project/sync` | Creates/updates translation project (sync flow) |
| | | GET | `/bin/guides/v1/translation/project/creationstatus` | Translation sync status for a project by path |
| | | GET | `/bin/guides/v1/translation/project/existing` | Existing translation projects for current user |
| | | GET | `/bin/guides/v1/translation/project/inprogress` | InProgress projects for a given asset |
| | | DELETE | `/bin/guides/v1/translation/project/delete` | Pre-delete update of asset translation statuses/properties |
| | | DELETE | `/bin/guides/v1/translation/project/job/delete` | Pre-delete update of asset statuses before job removal |
| | Reference | POST | `/bin/guides/v1/translation/reference/accept` | Accept translated content from job child pages |
| | | POST | `/bin/guides/v1/translation/reference/reject` | Reject translated content from job child pages |
| | | POST | `/bin/guides/v1/translation/reference/sync` | Create language copies in destination folders |
| | | POST | `/bin/guides/v1/translation/reference/baseline/export` | Export translation baseline to destination languages |
| | | POST | `/bin/guides/v1/translation/reference/status/forcesync` | Force-update out-of-sync assets to in-sync |

{style="table-layout:fixed"}

<table style="table-layout:auto">
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
