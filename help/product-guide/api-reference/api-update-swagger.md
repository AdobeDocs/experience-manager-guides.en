# New APIs in the 2026.08.01 release

This article lists the new APIs added to the public Swagger documentation for Adobe Experience Manager Guides as a Cloud Service in the 2026.08.01 release. These operations extend the Assets, Publishing, and Translation external specs, giving developers programmatic access to import and validation workflows, output generation status, and the full set of v1 translation operations.

For more information about the other enhancements in this release, view What's new in the 2026.08.01 release.

| Release | Feature/Area | Sub-feature | Method | API | Description |
|---|---|---|---|---|---|
| 2026.08.01 | Assets | | POST | `/bin/guides/v1/asset/import` | Imports one or more assets into a target folder; supports multipart upload and conflict resolution |
| | | | POST | `/bin/guides/v1/asset/list` | Returns paginated list of assets under a folder path |
| | | | POST | `/bin/guides/v1/asset/validatexml` | Validates DITA XML for well-formedness, schema validity, and conref integrity |
| | | | POST | `/bin/guides/v1/asset/version/revert` | Reverts an asset to a specified version |
| | | | GET | `/bin/guides/v1/asset/currentversion/detail` | Returns current version details (version name, dirty status, labels, etc.) |
| | | | POST | `/bin/guides/v1/assets/status` | Starts async job to check Guides status of assets under given path(s) |
| | | | GET | `/bin/guides/v1/assets/status` | Retrieves status/results of an asset status job by job ID |
| 2026.08.01 | Publishing | | POST | `/bin/guides/v1/output/generate` | Starts preset execution to generate output for a map |
| | | | GET | `/bin/guides/v1/output/status` | Returns status of a single output generation by map path and generation ID |
| | | | GET | `/bin/guides/v1/output/status/list` | Returns status of all generated presets for a map path |
| 2026.08.01 | Translation | Language | GET | `/bin/guides/v1/translation/language/copies` | Language copies of an asset by path or UUID |
| | | | GET | `/bin/guides/v1/translation/language/groups` | Language groups for a folder profile |
| | | | GET | `/bin/guides/v1/translation/language/list` | Supported translation languages (filtered) |
| | | | GET | `/bin/guides/v1/translation/language/root` | Root languages available for an asset path |
| | | | GET | `/bin/guides/v1/translation/language/variable` | Language variables by type and language codes |
| | | | POST | `/bin/guides/v1/translation/language/variable` | Create, update, or delete language variables |
| | | Project | POST | `/bin/guides/v1/translation/project/create` | Create/update translation project for a DITA map |
| | | | POST | `/bin/guides/v1/translation/project/sync` | Create/update translation project (sync flow) |
| | | | GET | `/bin/guides/v1/translation/project/creationstatus` | Translation sync status for a project by path |
| | | | GET | `/bin/guides/v1/translation/project/existing` | Existing translation projects for current user |
| | | | GET | `/bin/guides/v1/translation/project/inprogress` | InProgress projects for a given asset |
| | | | DELETE | `/bin/guides/v1/translation/project/delete` | Pre-delete update of asset translation statuses/properties |
| | | | DELETE | `/bin/guides/v1/translation/project/job/delete` | Pre-delete update of asset statuses before job removal |
| | | Reference | POST | `/bin/guides/v1/translation/reference/accept` | Accept translated content from job child pages |
| | | | POST | `/bin/guides/v1/translation/reference/reject` | Reject translated content from job child pages |
| | | | POST | `/bin/guides/v1/translation/reference/sync` | Create language copies in destination folders |
| | | | POST | `/bin/guides/v1/translation/reference/baseline/export` | Export translation baseline to destination languages |
| | | | POST | `/bin/guides/v1/translation/reference/status/forcesync` | Force-update out-of-sync assets to in-sync |

> **Note:** The Assets spec (`guides-assets.yaml`) exposes 20 operations in total, of which the 7 listed above are new in this release. The Publishing spec (`guides-publishing.yaml`) exposes 3 public operations; all remaining publishing APIs are internal-only. The Translation spec (`guides-translation.yaml`) exposes 18 v1 operations, all listed above; the v2 create API (`POST /bin/guides/v2/translation/project/create`) remains internal only.
