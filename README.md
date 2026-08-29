# SevaSetu AI

**AI-powered Government Benefits & Services Coordination Agent**

SevaSetu AI helps citizens turn a real-world problem into an actionable path through relevant government schemes and services.

## Hackathon targets

- Smart India Hackathon — SIH26129: Unified Navigator for Fragmented Government Services
- Smart India Hackathon — SIH26092: Scheme-Matching and Action Planner for Marginalised Entrepreneurs
- GalxeCode ’26 — agent-focused implementation and demonstration

## Core flow

**Citizen problem → AI agent → targeted questions → verified scheme search → eligibility → documents → personalized action plan → official service navigation**

## Tech stack

- React + Vite + Tailwind CSS
- Python + FastAPI + Pydantic
- Supabase + PostgreSQL
- OpenAI API with tool calling / structured outputs
- Optional browser speech / ElevenLabs
- Optional Leaflet / Mapbox
- Vercel + Render/Railway

## Repository

```text
frontend/     React application
backend/      FastAPI application
 database/    Database schema and seed data
docs/         Architecture and project documentation
tests/        Test plans and automated tests
```

## Important product rules

- This is not an official government authority.
- Do not invent government schemes, eligibility rules, or official links.
- Government information should retain a source/reference and verification date.
- Do not claim an application was submitted or approved without a legitimate integration.
- Demo/simulated actions must be clearly labeled.
- Never expose API keys in frontend code.

## Status

Phase 0 — Master specification complete. Implementation follows the approved architecture.

See [MASTER_SPEC.md](MASTER_SPEC.md) for the complete project specification.
