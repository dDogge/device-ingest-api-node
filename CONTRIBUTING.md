# Contributing

Thanks for contributing to **device-ingest-api-node**!

This is a Node.js + TypeScript REST API for ingesting device telemetry. We aim for consistent structure, strict input validation, strong error handling, and tests from day 1.

## Changelog and decisions (required)
- **Update `CHANGELOG.md` on every push** (at minimum the `Unreleased` section).
- For major decisions (framework choices, auth strategy, API contract changes, storage approach), **add/update an ADR** in `docs/decisions/`.

## Prerequisites
- Node.js (LTS recommended)
- npm

## Setup
```bash
npm install
cp .env.example .env
```

## Run locally
```bash
npm run dev
```

## Testing
```bash
npm test
```

## Lint / format / build
```bash
npm run lint
npm run build
```

## Project conventions

### Architecture (recommended)
Keep code in layers:
- `src/routes` — route definitions
- `src/controllers` — request/response wiring (thin)
- `src/services` — business logic
- `src/repositories` — persistence/external calls
- `src/middleware` — cross-cutting (auth, errors, logging)

### Validation and error handling
- Validate all external input (e.g. with zod).
- Use consistent error responses (status + message + optional details).
- Avoid leaking stack traces to clients.

### Naming
- Functions: verbs (e.g. `ingestTelemetry`)
- Types/Interfaces: nouns (e.g. `TelemetryEvent`)
- Prefer explicit, descriptive names.

## Documentation
- Update `README.md` when endpoints or environment variables change.
- Update `docs/architecture.md` when flows or boundaries change.
- Add an ADR under `docs/decisions/` for major choices.

## Commit message guidelines
Use clear, imperative messages:
- "Add health endpoint"
- "Validate ingest payload with zod"
- "Add integration test for /ingest"

## Pull requests
- Include a summary and how to verify locally.
- Add/update tests when behavior changes.
- Keep changes scoped and reviewable.
