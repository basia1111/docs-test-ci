# dev-repo-api

Simulates the engineering repo that owns the OpenAPI spec. Every push
triggers the workflow, which delivers openapi.yaml into the docs
project at remotes/ci/ (CI/CD remote content, Redocly Reunite).

Do NOT connect this repo to Reunite via Git hosting - the point of
this lane is that it stays outside.

## Tests

- Latency: edit any `summary`, commit to main, time commit -> live
- Preview: same edit on a feature branch -> preview deployment only
- Failure: break a $ref on purpose, push -> pipeline must block
- Governance: toggle auto-merge on the CI/CD source in Reunite
