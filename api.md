# OmniWrap C API

<!-- omniwrap-api-reference eyJjb250cmFjdF9maW5nZXJwcmludCI6IjIyODliY2IwZDY2MWJkZWE2ZGQ0N2M3OTY3ZjM3YWFjZTdkM2ExNTJlMThlN2QyZjY0YzA4NTE0ZmI3M2U3OTUiLCJvcGVyYXRpb25fY291bnQiOjE2LCJyZW5kZXJlciI6ImMiLCJ2ZXJzaW9uIjoiMS41LjAifQ -->

This generated index is tied to Semantic IR `1.14.0` and contract fingerprint `2289bcb0d661bdea6dd47c7967f37aace7d3a152e18e7d2f64c08514fb73e795`. Every operation below is rendered from the same semantic contract and artifact-attested public member allocation as the SDK.

SDK maturity: **experimental**  
Artifact evidence: [`omniwrap-artifact.json`](omniwrap-artifact.json) binds this file by SHA-256 and is revalidated by the package gate.

## Shared types

- `ApiError`
- `Artifact`
- `CancelRequest`
- `CancellationReceipt`
- `ConfigurationRequest`
- `ConfigurationRevision`
- `Cursor`
- `Diagnostic`
- `ErrorDetail`
- `EventPage`
- `Evidence`
- `EvidenceBinding`
- `EvidencePage`
- `ExecutionBinding`
- `GateReport`
- `GateStatus`
- `LogEntry`
- `LogPage`
- `ObservedPhase`
- `OpaqueId`
- `Preview`
- `PreviewEvent`
- `PreviewInputs`
- `PreviewPage`
- `PreviewRequest`
- `PreviewState`
- `PrimaryArtifacts`
- `ProfileId`
- `Project`
- `ProjectPage`
- `Sha256`
- `SourceRevision`
- `StrongEtag`
- `Timestamp`
- `UserContext`

## Resource `artifacts`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfYXJ0aWZhY3QiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRBcnRpZmFjdCIsInBhdGgiOiIvdjEvcHJvamVjdHMve3Byb2plY3RJZH0vYXJ0aWZhY3RzL3thcnRpZmFjdElkfSIsInJlc291cmNlIjoiYXJ0aWZhY3RzIiwic2VjdGlvbl9zaGEyNTYiOiJjNDg0MWY1YTM3NjIyMWIyZDdkYmRlMmRhMjI2ZWUxOWJmNjgyNTg3ZjUxOTAzYzBmOGRjOGRjYzdlNGVlOWFiIiwic2lnbmF0dXJlX3NoYTI1NiI6IjZhZDk2OGU1MzI4ODM0NGJjYzBjZjE0ZTE1ZDE5NGU1MGU1NWFlMTJiZjI5ZjQ5MTJhNDRhZDRiYWFjZjc2NTEifQ -->
### `client.omniwrap_get_artifact`

Operation ID: `getArtifact`  
Route: `GET` `/v1/projects/{projectId}/artifacts/{artifactId}`  

#### Signature

```c
int omniwrap_get_artifact(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_artifact_id, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `artifactId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (Artifact) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "artifactId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRBcnRpZmFjdCJ9 -->

## Resource `configurations`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9jcmVhdGVfY29uZmlndXJhdGlvbl9yZXZpc2lvbiIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJjcmVhdGVDb25maWd1cmF0aW9uUmV2aXNpb24iLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L2NvbmZpZ3VyYXRpb24tcmV2aXNpb25zIiwicmVzb3VyY2UiOiJjb25maWd1cmF0aW9ucyIsInNlY3Rpb25fc2hhMjU2IjoiNmI4NWViY2Y2YWY2MmMwZGI5Zjk4MjZjNGQ1OTI4ZTliODY2ZmY4MDM3YjU2OGYyZjJjYWQ4ZTI3YjBkYjYyMyIsInNpZ25hdHVyZV9zaGEyNTYiOiJjMjRlMmIyNWUzMzcxZTk3OTgwNGJjOTkwYmY5MGU4ZGZjNTM2MmNlNzA1MjVkNzc1NGNmODRhNDJiNTEzZmRiIn0 -->
### `client.omniwrap_create_configuration_revision`

Operation ID: `createConfigurationRevision`  
Route: `POST` `/v1/projects/{projectId}/configuration-revisions`  

#### Signature

```c
int omniwrap_create_configuration_revision(omniwrap_client_t *client, const char *arg_0_project_id, const char *body_json, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `If-Match` | `header` | yes | `StrongEtag` | Exactly one strong ETag. Configuration activation and preview creation compare the current Project ETag, including first activation. Cancellation compares the Preview ETag. Stale = 412; absent = 428. Wildcard, weak tags and lists are rejected. |
| `Idempotency-Key` | `header` | yes | `string` | Required on every mutation. Scope = organization + project + operation; fingerprint includes raw body bytes, media type, resource and If-Match. Same key/content replays the same receipt; changed content is 409. Retained for 86400 seconds; reconcile an ambiguous outcome within retention before retry, never silently allocate a new key. |
| `X-CSRF-Token` | `header` | yes | `string` | Session-bound synchronizer token from the trusted BFF bootstrap, independent of the unreadable session cookie. Validate same-origin Origin and CSRF before mutation. This contract does not implement or provision the session/CSRF exchange. |
| `body` | body | yes | `ConfigurationRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `201` | Created and atomically activated after admitted engine resolution; response ETag identifies the immutable configuration. Reload Project to obtain the new Project ETag. | application/json (ConfigurationRevision) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `409` | idempotency_conflict/reconcile_idempotency, binding_conflict/refresh_snapshot, or retry_requires_reconciliation/refresh_snapshot. No additional effect. | application/json (allOf&lt;ApiError, object&gt;) |
| `412` | precondition_failed; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `413` | request_too_large; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `415` | unsupported_media_type; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `428` | precondition_required; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "body": {
    "profileId": "openapi-typescript-preview/1",
    "sourceRevisionId": "example"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "header",
      "name": "If-Match",
      "value": "\"A\""
    },
    {
      "in": "header",
      "name": "Idempotency-Key",
      "value": "AAAAAAAAAAAAAAAA"
    },
    {
      "in": "header",
      "name": "X-CSRF-Token",
      "value": "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVDb25maWd1cmF0aW9uUmV2aXNpb24ifQ -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfY29uZmlndXJhdGlvbl9yZXZpc2lvbiIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldENvbmZpZ3VyYXRpb25SZXZpc2lvbiIsInBhdGgiOiIvdjEvcHJvamVjdHMve3Byb2plY3RJZH0vY29uZmlndXJhdGlvbi1yZXZpc2lvbnMve3JldmlzaW9uSWR9IiwicmVzb3VyY2UiOiJjb25maWd1cmF0aW9ucyIsInNlY3Rpb25fc2hhMjU2IjoiZDI5ODI2ZGI5Y2JjMGY2ZThkMjFkZmY5MmRiODljZGM5OTM5MDFhYzg0ZDY1MDVlY2M5OTA5ZGYxZDBiMWU2ZSIsInNpZ25hdHVyZV9zaGEyNTYiOiJkNGEzMjc2OWI3YmRkMmE5NjY3Nzk3NmEwNGNlYjg5MTRkMTNhODA0ZDliMzI3ZjVmY2QyMzA5OGQyMDNiZDAyIn0 -->
### `client.omniwrap_get_configuration_revision`

Operation ID: `getConfigurationRevision`  
Route: `GET` `/v1/projects/{projectId}/configuration-revisions/{revisionId}`  

#### Signature

```c
int omniwrap_get_configuration_revision(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_revision_id, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `revisionId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (ConfigurationRevision) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "revisionId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRDb25maWd1cmF0aW9uUmV2aXNpb24ifQ -->

## Resource `context`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfdXNlcl9jb250ZXh0IiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0VXNlckNvbnRleHQiLCJwYXRoIjoiL3YxL21lL2NvbnRleHQiLCJyZXNvdXJjZSI6ImNvbnRleHQiLCJzZWN0aW9uX3NoYTI1NiI6ImEwZjk5Mzk4NDcyZjQ1MjdjODBlZWZlM2U0ZTRjMTMxYTQ0OGE1ZGM1YjAzNTMyZjc3MzI3NGIzZjgzNDQ4ZGUiLCJzaWduYXR1cmVfc2hhMjU2IjoiMDA2ZGEwNmY1OWIxMmNlMWQzOGIyMDhjZTk3MTZmNTI1YTdkZDY5ODRmY2Q2NzVlYTczZmUyNmIxM2EyNDU3YyJ9 -->
### `client.omniwrap_get_user_context`

Operation ID: `getUserContext`  
Route: `GET` `/v1/me/context`  

#### Signature

```c
int omniwrap_get_user_context(omniwrap_client_t *client, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| _none_ | | | | |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (UserContext) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRVc2VyQ29udGV4dCJ9 -->

## Resource `evidence`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfZXZpZGVuY2UiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRFdmlkZW5jZSIsInBhdGgiOiIvdjEvcHJvamVjdHMve3Byb2plY3RJZH0vZXZpZGVuY2Uve2V2aWRlbmNlSWR9IiwicmVzb3VyY2UiOiJldmlkZW5jZSIsInNlY3Rpb25fc2hhMjU2IjoiN2ExZThjNTRlZDRmNTM0ZDE1YjAxMTk5ZGVkZDBhZGEzZDNlZjA1YzZkYzEwNDg5OTUxZDc1OTNhOTVmMGMzNyIsInNpZ25hdHVyZV9zaGEyNTYiOiJjYmRhZDljNTY0M2Y0YzFmOGI4ZTcyNTNhN2YzZjRlYmJmZjVmOGE2ZTZlYjk0MGY0YmQ5MDk3MWQ5ZTNmZWU4In0 -->
### `client.omniwrap_get_evidence`

Operation ID: `getEvidence`  
Route: `GET` `/v1/projects/{projectId}/evidence/{evidenceId}`  

#### Signature

```c
int omniwrap_get_evidence(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_evidence_id, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `evidenceId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (Evidence) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "evidenceId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRFdmlkZW5jZSJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9saXN0X3ByZXZpZXdfZXZpZGVuY2Vfd2l0aF9xdWVyeSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6Imxpc3RQcmV2aWV3RXZpZGVuY2UiLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L3ByZXZpZXdzL3twcmV2aWV3SWR9L2V2aWRlbmNlIiwicmVzb3VyY2UiOiJldmlkZW5jZSIsInNlY3Rpb25fc2hhMjU2IjoiYjNjMzY5OTJjNDNkMzFmNGMwZGZjNTkwZGY2MjNhYjRiMjBkODJlNDBjNzRiOWMwMzVmYWRjNTVlM2ViNmZlZCIsInNpZ25hdHVyZV9zaGEyNTYiOiIzNTU0NmFlZmE0MDk1Nzg5YWVjYmYyMTkxOWU4M2EyNzczNzNhNDg5ZWYwZTFmYmU0OGU4ZWFiYzdmYzg1MmE5In0 -->
### `client.omniwrap_list_preview_evidence_with_query`

Operation ID: `listPreviewEvidence`  
Route: `GET` `/v1/projects/{projectId}/previews/{previewId}/evidence`  

#### Signature

```c
int omniwrap_list_preview_evidence_with_query(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_preview_id, const omniwrap_pair_t *query, size_t query_count, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `previewId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `cursor` | `query` | no | `Cursor` | Opaque scope-bound continuation, never an offset or authority token. Expired/gap = 410 refresh_snapshot; invalid/tampered/wrong filters = 422. Denied objects remain uniform404. |
| `limit` | `query` | no | `integer` | Maximum page size; default 50. |
| `gateId` | `query` | no | `string` |  |
| `availability` | `query` | no | `string` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (EvidencePage) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `410` | cursor_expired; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "previewId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0UHJldmlld0V2aWRlbmNlIn0 -->

## Resource `previews`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9jYW5jZWxfcHJldmlldyIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJjYW5jZWxQcmV2aWV3IiwicGF0aCI6Ii92MS9wcm9qZWN0cy97cHJvamVjdElkfS9wcmV2aWV3cy97cHJldmlld0lkfS9jYW5jZWwiLCJyZXNvdXJjZSI6InByZXZpZXdzIiwic2VjdGlvbl9zaGEyNTYiOiJjNmJmMjE2Y2MzMDA1ZmZiMTQxYjgwMmRlMDhmMDEwYzQwNjY5OTQ3YzIwMjA0YTY1ZDZhNGFhYTliZDVkNWU3Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjhiZjgzMWVhMGM3ZmFkODM3ZDRkNDA0OTY4NjdmYjUxMDk4ZDczNzY4YzhkM2ZjYTdlNmFkNjBjNDkwZTBmZTcifQ -->
### `client.omniwrap_cancel_preview`

Operation ID: `cancelPreview`  
Route: `POST` `/v1/projects/{projectId}/previews/{previewId}/cancel`  

#### Signature

```c
int omniwrap_cancel_preview(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_preview_id, const char *body_json, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `previewId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `If-Match` | `header` | yes | `StrongEtag` | Exactly one strong ETag. Configuration activation and preview creation compare the current Project ETag, including first activation. Cancellation compares the Preview ETag. Stale = 412; absent = 428. Wildcard, weak tags and lists are rejected. |
| `Idempotency-Key` | `header` | yes | `string` | Required on every mutation. Scope = organization + project + operation; fingerprint includes raw body bytes, media type, resource and If-Match. Same key/content replays the same receipt; changed content is 409. Retained for 86400 seconds; reconcile an ambiguous outcome within retention before retry, never silently allocate a new key. |
| `X-CSRF-Token` | `header` | yes | `string` | Session-bound synchronizer token from the trusted BFF bootstrap, independent of the unreadable session cookie. Validate same-origin Origin and CSRF before mutation. This contract does not implement or provision the session/CSRF exchange. |
| `body` | body | yes | `CancelRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Accepted for asynchronous processing; not a completed effect. | application/json (CancellationReceipt) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `409` | idempotency_conflict/reconcile_idempotency, binding_conflict/refresh_snapshot, or retry_requires_reconciliation/refresh_snapshot. No additional effect. | application/json (allOf&lt;ApiError, object&gt;) |
| `412` | precondition_failed; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `413` | request_too_large; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `415` | unsupported_media_type; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `428` | precondition_required; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "body": {
    "reason": "user_requested"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "previewId",
      "value": "example"
    },
    {
      "in": "header",
      "name": "If-Match",
      "value": "\"A\""
    },
    {
      "in": "header",
      "name": "Idempotency-Key",
      "value": "AAAAAAAAAAAAAAAA"
    },
    {
      "in": "header",
      "name": "X-CSRF-Token",
      "value": "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjYW5jZWxQcmV2aWV3In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9jcmVhdGVfcHJldmlldyIsIm1ldGhvZCI6IlBPU1QiLCJvcGVyYXRpb25faWQiOiJjcmVhdGVQcmV2aWV3IiwicGF0aCI6Ii92MS9wcm9qZWN0cy97cHJvamVjdElkfS9wcmV2aWV3cyIsInJlc291cmNlIjoicHJldmlld3MiLCJzZWN0aW9uX3NoYTI1NiI6Ijg1NTUwOGVjOWYyMGQxNmNiN2Y2YmQxM2Q0NzE4Zjc5ZmM5NGY3NjE4ZjFlODJhMWU2MDhjZjM3Y2U3MDI0OTUiLCJzaWduYXR1cmVfc2hhMjU2IjoiMThhOTQ0MzY2Y2FkYTI2MTJlNWUyZmRhZmM3YmEwYTViZjlmZWFkNzFhZTQ0OWFkYjA5YjhiNzQxNWI5MDQ4MiJ9 -->
### `client.omniwrap_create_preview`

Operation ID: `createPreview`  
Route: `POST` `/v1/projects/{projectId}/previews`  

#### Signature

```c
int omniwrap_create_preview(omniwrap_client_t *client, const char *arg_0_project_id, const char *body_json, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `If-Match` | `header` | yes | `StrongEtag` | Exactly one strong ETag. Configuration activation and preview creation compare the current Project ETag, including first activation. Cancellation compares the Preview ETag. Stale = 412; absent = 428. Wildcard, weak tags and lists are rejected. |
| `Idempotency-Key` | `header` | yes | `string` | Required on every mutation. Scope = organization + project + operation; fingerprint includes raw body bytes, media type, resource and If-Match. Same key/content replays the same receipt; changed content is 409. Retained for 86400 seconds; reconcile an ambiguous outcome within retention before retry, never silently allocate a new key. |
| `X-CSRF-Token` | `header` | yes | `string` | Session-bound synchronizer token from the trusted BFF bootstrap, independent of the unreadable session cookie. Validate same-origin Origin and CSRF before mutation. This contract does not implement or provision the session/CSRF exchange. |
| `body` | body | yes | `PreviewRequest` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Accepted for asynchronous processing; not a completed effect. | application/json (Preview) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `409` | idempotency_conflict/reconcile_idempotency, binding_conflict/refresh_snapshot, or retry_requires_reconciliation/refresh_snapshot. No additional effect. | application/json (allOf&lt;ApiError, object&gt;) |
| `412` | precondition_failed; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `413` | request_too_large; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `415` | unsupported_media_type; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `428` | precondition_required; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "body": {
    "configurationRevisionId": "example"
  },
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "header",
      "name": "If-Match",
      "value": "\"A\""
    },
    {
      "in": "header",
      "name": "Idempotency-Key",
      "value": "AAAAAAAAAAAAAAAA"
    },
    {
      "in": "header",
      "name": "X-CSRF-Token",
      "value": "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVQcmV2aWV3In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfcHJldmlldyIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFByZXZpZXciLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L3ByZXZpZXdzL3twcmV2aWV3SWR9IiwicmVzb3VyY2UiOiJwcmV2aWV3cyIsInNlY3Rpb25fc2hhMjU2IjoiN2VkN2NjZDZhZWNjOWM0MTljNWVmNTU1MDMxNzJhNzE3YjBmM2Y3ZWI1MWFmMTA2YzFiMjU3OTRlNTRlMDE4NiIsInNpZ25hdHVyZV9zaGEyNTYiOiJiZjkzZWMzOTQzMWI0Nzg2NDVmMzk0MDY5ODE2Y2IyOGIyMGRkYWRkMjE1MTI5MjY5MjZlMzQ5YmM0MWI1ZjVlIn0 -->
### `client.omniwrap_get_preview`

Operation ID: `getPreview`  
Route: `GET` `/v1/projects/{projectId}/previews/{previewId}`  

#### Signature

```c
int omniwrap_get_preview(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_preview_id, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `previewId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (Preview) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "previewId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQcmV2aWV3In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfcHJldmlld19ldmVudHNfd2l0aF9xdWVyeSIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFByZXZpZXdFdmVudHMiLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L3ByZXZpZXdzL3twcmV2aWV3SWR9L2V2ZW50cyIsInJlc291cmNlIjoicHJldmlld3MiLCJzZWN0aW9uX3NoYTI1NiI6ImUzMDI1YzhlZGYzMzQ1NzBlNzgyMGY0NTI2ZWVmNjk5MmUyY2Y2YmM3OTBlMmYyN2FjZTU3ZGUyZDc0NjhkMDkiLCJzaWduYXR1cmVfc2hhMjU2IjoiYmZkMDE4MDQ1OWU5MTlhMzllYzkwZWZjYjlhMmYzYzdlNDgwMTg4YTg5M2VlNGUxNDJlMDY3ZjJkYzFmMzYxYiJ9 -->
### `client.omniwrap_get_preview_events_with_query`

Operation ID: `getPreviewEvents`  
Route: `GET` `/v1/projects/{projectId}/previews/{previewId}/events`  

#### Signature

```c
int omniwrap_get_preview_events_with_query(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_preview_id, const omniwrap_pair_t *query, size_t query_count, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `previewId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `cursor` | `query` | no | `Cursor` | Opaque scope-bound continuation, never an offset or authority token. Expired/gap = 410 refresh_snapshot; invalid/tampered/wrong filters = 422. Denied objects remain uniform404. |
| `limit` | `query` | no | `integer` | Maximum page size; default 50. |
| `Last-Event-ID` | `header` | no | `Cursor` | SSE resume cursor; replay begins strictly after it. If query cursor also occurs the two must match, otherwise 422. Reauthorization is mandatory on reconnect. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (EventPage), text/event-stream (string) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `410` | cursor_expired; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "previewId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQcmV2aWV3RXZlbnRzIn0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfcHJldmlld19sb2dzX3dpdGhfcXVlcnkiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJnZXRQcmV2aWV3TG9ncyIsInBhdGgiOiIvdjEvcHJvamVjdHMve3Byb2plY3RJZH0vcHJldmlld3Mve3ByZXZpZXdJZH0vbG9ncyIsInJlc291cmNlIjoicHJldmlld3MiLCJzZWN0aW9uX3NoYTI1NiI6IjllODMzNDM2OTY3ZmI4NDQzZTk0YmUzMGY2MTZkMjcyMjc4ZTVkMjAzMDE5YTE4NWMxNzg4M2JmNzU2ZDliMDQiLCJzaWduYXR1cmVfc2hhMjU2IjoiMzVmNmRjYzcwYjFiY2UzZjQ0ZTU2ZDg0MTk0MjEyNjllZmI2ODVjOWEzYTM1Zjg1Y2YwNzBmODkwMTFhMDk4MyJ9 -->
### `client.omniwrap_get_preview_logs_with_query`

Operation ID: `getPreviewLogs`  
Route: `GET` `/v1/projects/{projectId}/previews/{previewId}/logs`  

#### Signature

```c
int omniwrap_get_preview_logs_with_query(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_preview_id, const omniwrap_pair_t *query, size_t query_count, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `previewId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `cursor` | `query` | no | `Cursor` | Opaque scope-bound continuation, never an offset or authority token. Expired/gap = 410 refresh_snapshot; invalid/tampered/wrong filters = 422. Denied objects remain uniform404. |
| `limit` | `query` | no | `integer` | Maximum page size; default 50. |
| `level` | `query` | no | `string` |  |
| `phaseId` | `query` | no | `OpaqueId` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (LogPage) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `410` | cursor_expired; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "previewId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQcmV2aWV3TG9ncyJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9saXN0X3ByZXZpZXdzX3dpdGhfcXVlcnkiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0UHJldmlld3MiLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L3ByZXZpZXdzIiwicmVzb3VyY2UiOiJwcmV2aWV3cyIsInNlY3Rpb25fc2hhMjU2IjoiYTBlYTM4N2NiZTk3MWQ1NDViOGY3ZTZkYTkwZTgwZTBlMWUyYWQzODUxOWUyOTExOGE3NTE0Zjg0MWY1ZDczNSIsInNpZ25hdHVyZV9zaGEyNTYiOiI5N2E2OTYwNTA5ZDViYjE5YzM1ZGY2N2MwYzZhOTk0NTM5NjQwMDk2MDgyZDE3NTQ3ODRhZTM5YmI3NTUyM2RkIn0 -->
### `client.omniwrap_list_previews_with_query`

Operation ID: `listPreviews`  
Route: `GET` `/v1/projects/{projectId}/previews`  

#### Signature

```c
int omniwrap_list_previews_with_query(omniwrap_client_t *client, const char *arg_0_project_id, const omniwrap_pair_t *query, size_t query_count, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `cursor` | `query` | no | `Cursor` | Opaque scope-bound continuation, never an offset or authority token. Expired/gap = 410 refresh_snapshot; invalid/tampered/wrong filters = 422. Denied objects remain uniform404. |
| `limit` | `query` | no | `integer` | Maximum page size; default 50. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (PreviewPage) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `410` | cursor_expired; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0UHJldmlld3MifQ -->

## Resource `projects`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfcHJvamVjdCIsIm1ldGhvZCI6IkdFVCIsIm9wZXJhdGlvbl9pZCI6ImdldFByb2plY3QiLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9IiwicmVzb3VyY2UiOiJwcm9qZWN0cyIsInNlY3Rpb25fc2hhMjU2IjoiNjQ2N2M1NGNkNjFiZGJkMGVjMzg4ZTUzMjI4YWVlYTgyMGQzYjU1YzU3Yzg5ZDM2MDMwYjNlNmNkYjBjOTcyMiIsInNpZ25hdHVyZV9zaGEyNTYiOiJiMTRkNDAwZDk5MDgzMWE0MGRlZTRkMDFiZjNhYzFmMGE2ZWQ3ZDdiM2ZhZDMwYzY0MjE1OGVjMjQzODgyMDI3In0 -->
### `client.omniwrap_get_project`

Operation ID: `getProject`  
Route: `GET` `/v1/projects/{projectId}`  

#### Signature

```c
int omniwrap_get_project(omniwrap_client_t *client, const char *arg_0_project_id, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (Project) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRQcm9qZWN0In0 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9saXN0X3Byb2plY3RzX3dpdGhfcXVlcnkiLCJtZXRob2QiOiJHRVQiLCJvcGVyYXRpb25faWQiOiJsaXN0UHJvamVjdHMiLCJwYXRoIjoiL3YxL3Byb2plY3RzIiwicmVzb3VyY2UiOiJwcm9qZWN0cyIsInNlY3Rpb25fc2hhMjU2IjoiMDdmYTA5MDZmMDkzOTJjZTU3YWQ2MWVmZTI1NDM0ODAwYjIxNTA0MjdiZjUwYjE4MDZlZjFmNDUyNDI1YzM3MiIsInNpZ25hdHVyZV9zaGEyNTYiOiJmMjE5OWEyYTM1ODE1MzkzZGJiNzNkN2U0ZmYzYmM0OTBjZGZlNWUwNTJiZDNhMTQ3YmI1NDYxMDU2YjEwMzQxIn0 -->
### `client.omniwrap_list_projects_with_query`

Operation ID: `listProjects`  
Route: `GET` `/v1/projects`  

#### Signature

```c
int omniwrap_list_projects_with_query(omniwrap_client_t *client, const omniwrap_pair_t *query, size_t query_count, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `cursor` | `query` | no | `Cursor` | Opaque scope-bound continuation, never an offset or authority token. Expired/gap = 410 refresh_snapshot; invalid/tampered/wrong filters = 422. Denied objects remain uniform404. |
| `limit` | `query` | no | `integer` | Maximum page size; default 50. |
| `query` | `query` | no | `string` | Display-name substring filter, case-insensitive Unicode NFC matching. Bound to pagination cursor. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (ProjectPage) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `410` | cursor_expired; recovery=refresh_snapshot. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": []
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJsaXN0UHJvamVjdHMifQ -->

## Resource `sources`

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9jcmVhdGVfc291cmNlX3JldmlzaW9uX3dpdGhfcXVlcnkiLCJtZXRob2QiOiJQT1NUIiwib3BlcmF0aW9uX2lkIjoiY3JlYXRlU291cmNlUmV2aXNpb24iLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L3NvdXJjZS1yZXZpc2lvbnMiLCJyZXNvdXJjZSI6InNvdXJjZXMiLCJzZWN0aW9uX3NoYTI1NiI6ImViMWFhNTQ4MTY0Y2FjNDUyYzQ2ODg5Mzg5MzcwYTJmOTg4NTY5YzgwMjEzYzNjMzBmMjBjMTdmMzYwYTcyMmYiLCJzaWduYXR1cmVfc2hhMjU2IjoiYmI1NWY0OTZlNWJhNWVjYWQ5MGM5OWFlOTE5NTlkZmYxZTMwZDI3NzM4MTg3ZGFmYjg3ODE2YzZjYjEyYzQ0MyJ9 -->
### `client.omniwrap_create_source_revision_with_query`

Operation ID: `createSourceRevision`  
Route: `POST` `/v1/projects/{projectId}/source-revisions`  

#### Signature

```c
int omniwrap_create_source_revision_with_query(omniwrap_client_t *client, const char *arg_0_project_id, const char *body_json, const omniwrap_pair_t *query, size_t query_count, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `Idempotency-Key` | `header` | yes | `string` | Required on every mutation. Scope = organization + project + operation; fingerprint includes raw body bytes, media type, resource and If-Match. Same key/content replays the same receipt; changed content is 409. Retained for 86400 seconds; reconcile an ambiguous outcome within retention before retry, never silently allocate a new key. |
| `X-CSRF-Token` | `header` | yes | `string` | Session-bound synchronizer token from the trusted BFF bootstrap, independent of the unreadable session cookie. Validate same-origin Origin and CSRF before mutation. This contract does not implement or provision the session/CSRF exchange. |
| `displayName` | `query` | yes | `string` | Escaped display text only, never used as a filename or storage key; included in idempotency fingerprint. |
| `body` | body | yes | `any` |  |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `202` | Accepted for asynchronous processing; not a completed effect. | application/json (SourceRevision) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `409` | idempotency_conflict/reconcile_idempotency, binding_conflict/refresh_snapshot, or retry_requires_reconciliation/refresh_snapshot. No additional effect. | application/json (allOf&lt;ApiError, object&gt;) |
| `413` | request_too_large; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `415` | unsupported_media_type; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "body": "example",
  "content_type": "application/json",
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "header",
      "name": "Idempotency-Key",
      "value": "AAAAAAAAAAAAAAAA"
    },
    {
      "in": "header",
      "name": "X-CSRF-Token",
      "value": "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA"
    },
    {
      "in": "query",
      "name": "displayName",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJjcmVhdGVTb3VyY2VSZXZpc2lvbiJ9 -->

<!-- omniwrap-api-operation eyJleGFtcGxlX3JlYXNvbiI6Imxhbmd1YWdlLWV4YW1wbGUtbm90LWdlbmVyYXRlZCIsImV4YW1wbGVfc3RhdHVzIjoidW5zdXBwb3J0ZWQiLCJtZW1iZXIiOiJvbW5pd3JhcF9nZXRfc291cmNlX3JldmlzaW9uIiwibWV0aG9kIjoiR0VUIiwib3BlcmF0aW9uX2lkIjoiZ2V0U291cmNlUmV2aXNpb24iLCJwYXRoIjoiL3YxL3Byb2plY3RzL3twcm9qZWN0SWR9L3NvdXJjZS1yZXZpc2lvbnMve3JldmlzaW9uSWR9IiwicmVzb3VyY2UiOiJzb3VyY2VzIiwic2VjdGlvbl9zaGEyNTYiOiI2MzExNWVkMjM5NzRkMzVkZjAyZTRkZDFjZDhlN2RhN2Y3OWQyYWQzYTM0YzdlYzg3YTI1N2VkOTZmMWM0NmY4Iiwic2lnbmF0dXJlX3NoYTI1NiI6IjU5ZDA5MTM2NmNjYmU4NDgzMzc1ODU5NzViZTYwMmYyZjNhZjBjZTBjMjZiYjliYTQ0OTVhMGY2ZWU2ZGQ0YTUifQ -->
### `client.omniwrap_get_source_revision`

Operation ID: `getSourceRevision`  
Route: `GET` `/v1/projects/{projectId}/source-revisions/{revisionId}`  

#### Signature

```c
int omniwrap_get_source_revision(omniwrap_client_t *client, const char *arg_0_project_id, const char *arg_1_revision_id, omniwrap_response_t *out_response)
```

#### Parameters

| Name | In | Required | Contract type | Description |
| --- | --- | --- | --- | --- |
| `projectId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |
| `revisionId` | `path` | yes | `OpaqueId` | Opaque identity; authorize organization/project and verify every parent relation before lookup or mutation. Knowledge of an ID grants no access. |

#### Responses

| Status | Description | Content |
| --- | --- | --- |
| `200` | Authorized resource snapshot. | application/json (SourceRevision) |
| `401` | unauthenticated; recovery=authenticate. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `403` | forbidden; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `404` | not_found; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `406` | not_acceptable; recovery=none. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `422` | invalid_request, source_not_valid or cursor_invalid; never reinterpret an invalid source as ready. | application/json (allOf&lt;ApiError, object&gt;) |
| `429` | rate_limited; recovery=retry_same_request. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `500` | internal_error; recovery=reconcile_idempotency. See the normative error mapping and operation retry policy. | application/json (allOf&lt;ApiError, object&gt;) |
| `503` | configuration_required/configure_authority when approved JackAI exchange or product configuration is absent; authority_unavailable/retry_same_request on outage/timeout. No fallback identity, cached authorization or synthetic data. | application/json (allOf&lt;ApiError, object&gt;) |

#### Canonical required-input example

```json
{
  "parameters": [
    {
      "in": "path",
      "name": "projectId",
      "value": "example"
    },
    {
      "in": "path",
      "name": "revisionId",
      "value": "example"
    }
  ]
}
```

#### SDK call example

Example status: `unsupported`  
Unsupported reason: `language-example-not-generated`

<!-- omniwrap-api-operation-end eyJvcGVyYXRpb25faWQiOiJnZXRTb3VyY2VSZXZpc2lvbiJ9 -->

