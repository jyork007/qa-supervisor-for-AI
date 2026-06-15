# qa-supervisor-for-AI

Postman QA suite for validating the `supervisor/generate` integration endpoint.

## Contents

- `supervisor-generate.collection.json`
- `supervisor-generate.environment.json`

## Usage

1. Import both JSON files into Postman.
2. Open the environment and set:
   - `validToken`
   - `expiredToken`
   - `wrongScopeToken`
3. Run collection folders in order.

## Optional CI (Newman)

```powershell
newman run .\supervisor-generate.collection.json -e .\supervisor-generate.environment.json --reporters cli,junit --bail
```

## GitHub Actions

This repository includes a workflow at `.github/workflows/newman.yml` that runs on push, pull request, and manual dispatch.

To enable automated API execution, add these repository secrets:

- `POSTMAN_VALID_TOKEN` (required)
- `POSTMAN_EXPIRED_TOKEN` (optional)
- `POSTMAN_WRONG_SCOPE_TOKEN` (optional)

If `POSTMAN_VALID_TOKEN` is not set, the workflow posts a skip notice instead of failing.
