# SevaSetu AI — Master Specification

## 1. Project

**SevaSetu AI** is an AI-powered Government Benefits & Services Coordination Agent for Smart India Hackathon and GalxeCode ’26.

### SIH problem statements
- **SIH26129** — Unified Navigator for Fragmented Government Services
- **SIH26092** — Scheme-Matching and Action Planner for Marginalised Entrepreneurs

## 2. Product vision

A citizen describes a real-world problem using text or voice. SevaSetu understands the situation, asks only the necessary follow-up questions, searches verified government-scheme data, evaluates eligibility, explains why schemes match, identifies required documents, generates a personalized action plan, and guides the citizen toward the relevant official government service.

**SevaSetu is an agent, not a generic response bot.** The agent uses explicit tools and structured outputs to perform a workflow.

## 3. Product boundaries

- SevaSetu is not a government authority.
- Never claim an application was submitted, approved, or processed unless a legitimate integration confirms it.
- Demo/simulated actions must be labeled as such.
- Never invent scheme names, eligibility rules, benefits, or official URLs.
- Government information should retain a source/reference and verification date.

## 4. Core user journey

1. Citizen opens SevaSetu.
2. Citizen describes a problem by text or voice.
3. Agent extracts relevant facts.
4. Agent identifies missing decision-critical information.
5. Agent asks targeted clarification questions.
6. Agent searches verified scheme data.
7. Agent evaluates eligibility.
8. Agent ranks matching schemes.
9. Agent explains the match and confidence/warnings.
10. Citizen opens a scheme.
11. System shows required documents.
12. Agent creates a personalized action plan.
13. System identifies the appropriate official government service.
14. Citizen follows the provided official route.
15. Important agent events are logged.

## 5. Agent tools

- `search_schemes`
- `get_scheme_details`
- `check_eligibility`
- `get_required_documents`
- `generate_action_plan`
- `find_government_service`
- `get_location_information`
- `log_agent_event`

All tool inputs must be validated server-side. The model must not be trusted to enforce authorization or data integrity.

## 6. Structured agent output

The agent should expose structured fields where applicable:

- `intent`
- `extracted_profile`
- `missing_information`
- `clarification_question`
- `matching_schemes`
- `eligibility_results`
- `required_documents`
- `action_plan`
- `service_links`
- `confidence`
- `warnings`

## 7. Technology stack

### Frontend
- React
- Vite
- Tailwind CSS
- React Router

### Backend
- Python
- FastAPI
- Pydantic

### Data
- Supabase
- PostgreSQL

### AI
- OpenAI API
- Tool/function calling
- Structured outputs

### Optional integrations
- Browser Speech APIs / ElevenLabs
- Leaflet / Mapbox

### Testing and deployment
- Postman
- Vercel — frontend
- Render/Railway — backend
- GitHub — source control

## 8. Architecture

```text
Citizen
  ↓
React Frontend
  ↓
FastAPI API
  ↓
AI Agent Orchestrator
  ↓
Agent Tools
  ├── Scheme Search
  ├── Eligibility Checker
  ├── Scheme Details
  ├── Document Checker
  ├── Action Planner
  ├── Government Service Navigator
  ├── Location
  └── Event Logger
  ↓
Supabase / PostgreSQL
```

## 9. Database entities

Initial entities:

- `users`
- `citizen_profiles`
- `schemes`
- `scheme_categories`
- `eligibility_rules`
- `scheme_documents`
- `government_services`
- `locations`
- `requests`
- `agent_sessions`
- `agent_events`
- `action_plans`
- `action_steps`

Scheme records should support source URL/reference, last verified date, status, geography, target beneficiaries, eligibility criteria, benefits, documents, and application process.

## 10. Backend API groups

- `GET /api/health`
- `GET /api/schemes/search`
- `GET /api/schemes/{id}`
- `POST /api/eligibility/check`
- `GET /api/schemes/{id}/documents`
- `POST /api/action-plans`
- `GET /api/services`
- `POST /api/agent/session`
- `POST /api/agent/message`
- `POST /api/location`
- `POST /api/events`

Exact contracts will be frozen before implementation.

## 11. Frontend pages

1. Landing
2. Citizen problem input
3. AI conversation
4. Clarification state
5. Scheme results
6. Scheme details
7. Eligibility analysis
8. Required documents
9. Personalized action plan
10. Government service navigation
11. Application/status demonstration
12. Responder/admin-style demo dashboard
13. How it works / About

## 12. Team ownership

### Person 1 — AI Agent
Agent architecture, prompts, tool calling, eligibility reasoning, scheme matching, action planning, structured outputs, agent tests.

### Person 2 — Backend + Database
FastAPI, Supabase/PostgreSQL, schema, REST APIs, validation, logging, database tests.

### Person 3 — Frontend
React/Vite/Tailwind, user journey, scheme cards, eligibility UI, documents, action plan, responsive UX.

### Person 4 — Voice + Integration + Deployment
Voice, location, frontend/backend integration, notifications simulation, environment setup, deployment, end-to-end testing.

## 13. Development phases

0. Master specification
1. Accounts and software setup
2. GitHub project structure
3. Figma UI/UX
4. Database
5. Backend APIs
6. AI agent
7. Frontend implementation
8. Voice/location
9. Integration
10. Testing/security
11. Deployment
12. WOW feature
13. PPT, 2–3 minute demo, judge Q&A

## 14. MVP

The MVP must support one complete end-to-end scenario:

**Problem → clarification → scheme search → eligibility → documents → action plan → official service navigation.**

Everything else is secondary.

## 15. WOW feature candidate

**Why does this scheme match me?**

Show the concrete user facts that caused the match and allow comparison with another scheme. The explanation must be grounded in stored scheme rules.

## 16. Explicit non-goals

Do not spend hackathon time initially on:

- Real government application submission without an official integration.
- Complex microservices.
- Training a custom LLM.
- Building a native mobile app.
- Unnecessary authentication complexity.
- Large-scale scraping before the core workflow works.
- Over-engineered real-time infrastructure.

## 17. Demo scenario

Recommended primary scenario: a small/marginalized entrepreneur seeking financial/business support.

Demo flow:

1. Voice/text problem.
2. Agent asks 2–3 decision-critical questions.
3. Matching schemes appear.
4. One scheme shows a match explanation.
5. Eligibility is displayed.
6. Documents are listed.
7. Personalized action plan is generated.
8. Official service route is shown.
9. Agent/tool activity can be shown briefly as technical evidence.

## 18. Quality bar

The product should feel like a focused civic-tech application, not a ChatGPT clone. Prioritize correctness, source traceability, clear UX, reliable tool execution, graceful failures, and a complete working demo over feature count.
