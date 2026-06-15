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
