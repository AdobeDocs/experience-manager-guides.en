# New APIs in the 2026.08.01 release

This article lists the new APIs added to the public Swagger documentation for Adobe Experience Manager Guides as a Cloud Service in the 2026.08.01 release. These operations extend the Assets, Publishing, and Translation external specs, giving developers programmatic access to import and validation workflows, output generation status, and the full set of v1 translation operations.

For more information about the other enhancements in this release, view What's new in the 2026.08.01 release.

<table>
  <thead>
    <tr>
      <th align="center">Release</th>
      <th align="center">Feature/Area</th>
      <th align="center">Sub-feature</th>
      <th align="center">Method</th>
      <th align="left">API</th>
      <th align="left">Description</th>
    </tr>
  </thead>
  <tbody>
    <!-- Assets: 7 rows -->
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center" rowspan="7"><b>Assets</b></td>
      <td align="center" rowspan="7">—</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/asset/import</code></td>
      <td>Imports one or more assets into a target folder; supports multipart upload and conflict resolution</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/asset/list</code></td>
      <td>Returns paginated list of assets under a folder path</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/asset/validatexml</code></td>
      <td>Validates DITA XML for well-formedness, schema validity, and conref integrity</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/asset/version/revert</code></td>
      <td>Reverts an asset to a specified version</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/asset/currentversion/detail</code></td>
      <td>Returns current version details (version name, dirty status, labels, etc.)</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/assets/status</code></td>
      <td>Starts async job to check Guides status of assets under given path(s)</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/assets/status</code></td>
      <td>Retrieves status/results of an asset status job by job ID</td>
    </tr>
    <!-- Publishing: 3 rows -->
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center" rowspan="3"><b>Publishing</b></td>
      <td align="center" rowspan="3">—</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/output/generate</code></td>
      <td>Starts preset execution to generate output for a map</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/output/status</code></td>
      <td>Returns status of a single output generation by map path and generation ID</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/output/status/list</code></td>
      <td>Returns status of all generated presets for a map path</td>
    </tr>
    <!-- Translation: 18 rows total -->
    <!-- Language: 6 rows -->
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center" rowspan="18"><b>Translation</b></td>
      <td align="center" rowspan="6">Language</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/language/copies</code></td>
      <td>Language copies of an asset by path or UUID</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/language/groups</code></td>
      <td>Language groups for a folder profile</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/language/list</code></td>
      <td>Supported translation languages (filtered)</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/language/root</code></td>
      <td>Root languages available for an asset path</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/language/variable</code></td>
      <td>Language variables by type and language codes</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/language/variable</code></td>
      <td>Create, update, or delete language variables</td>
    </tr>
    <!-- Project: 7 rows -->
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center" rowspan="7">Project</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/project/create</code></td>
      <td>Create/update translation project for a DITA map</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/project/sync</code></td>
      <td>Create/update translation project (sync flow)</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/project/creationstatus</code></td>
      <td>Translation sync status for a project by path</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/project/existing</code></td>
      <td>Existing translation projects for current user</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>GET</b></td>
      <td><code>/bin/guides/v1/translation/project/inprogress</code></td>
      <td>InProgress projects for a given asset</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>DELETE</b></td>
      <td><code>/bin/guides/v1/translation/project/delete</code></td>
      <td>Pre-delete update of asset translation statuses/properties</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>DELETE</b></td>
      <td><code>/bin/guides/v1/translation/project/job/delete</code></td>
      <td>Pre-delete update of asset statuses before job removal</td>
    </tr>
    <!-- Reference: 5 rows -->
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center" rowspan="5">Reference</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/reference/accept</code></td>
      <td>Accept translated content from job child pages</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/reference/reject</code></td>
      <td>Reject translated content from job child pages</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/reference/sync</code></td>
      <td>Create language copies in destination folders</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/reference/baseline/export</code></td>
      <td>Export translation baseline to destination languages</td>
    </tr>
    <tr>
      <td align="center">2026.08.01</td>
      <td align="center"><b>POST</b></td>
      <td><code>/bin/guides/v1/translation/reference/status/forcesync</code></td>
      <td>Force-update out-of-sync assets to in-sync</td>
    </tr>
  </tbody>
</table>

*Note: The Assets spec (`guides-assets.yaml`) exposes 20 operations in total, of which the 7 listed above are new in this release. The Publishing spec (`guides-publishing.yaml`) exposes 3 public operations; all remaining publishing APIs are internal-only. The Translation spec (`guides-translation.yaml`) exposes 18 v1 operations, all listed above; the v2 create API (`POST /bin/guides/v2/translation/project/create`) remains internal only.*