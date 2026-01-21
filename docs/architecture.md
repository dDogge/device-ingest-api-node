# Architecture

## Overview
REST API gateway that receives telemetry from devices/agents.

## Layers
- Routes: HTTP endpoints and routing
- Controllers: translate HTTP <-> service calls
- Services: business rules (validation, idempotency, enrichment)
- Repositories: persistence and external service calls

## Data flow (target)
1) Agent sends telemetry → `POST /ingest`
2) Validate + normalize
3) Store raw event and/or forward to analytics
4) Return ack with request id