# n8n Clay Workflow Notes

## Workflow Details
- **Name**: Manus My workflow 4
- **ID**: 8dZBaxoXJzUExo3W
- **URL**: https://n8n-xmux.onrender.com/workflow/8dZBaxoXJzUExo3W

## What it Does
This workflow runs every 15 minutes and triggers a Clay API table run via PATCH request.

## Fixes Applied (2024-12-31)

### Issues Found in Original
1. Leading space in URL
2. Leading spaces in headers (` Content-Type` and ` application/json`)
3. Expired session cookie - needed API key auth instead

### Changes Made

| Field    | Old (Broken)                     | New (Fixed)                                 |
|----------|----------------------------------|---------------------------------------------|
| URL      | ` https://api.clay.com...`       | `https://api.clay.com...`                   |
| Header 1 | `cookie: claysession=...`        | `Authorization: Bearer 5ab764256439eda7e245`|
| Header 2 | ` Content-Type:  application/json` | `Content-Type: application/json`          |

## API Endpoint
```
PATCH https://api.clay.com/v3/tables/t_0t81wcjDX7iDNWq2RHC/run
```

## Headers
- `Authorization: Bearer 5ab764256439eda7e245`
- `Content-Type: application/json`

## Request Body
```json
{
  "fieldIds": ["f_0t821i8DVvktDi592RE"],
  "callerName": "RunNumRowsModal",
  "runRecords": {
    "viewIdTopRecords": {
      "viewId": "gv_0t81wckSRPupfnYrrpA",
      "numRecords": 100
    }
  }
}
```
