# SevaSetu AI — Architecture

```text
Citizen
  ↓
React + Vite + Tailwind
  ↓
FastAPI API
  ↓
AI Agent Orchestrator
  ├── search_schemes
  ├── get_scheme_details
  ├── check_eligibility
  ├── get_required_documents
  ├── generate_action_plan
  ├── find_government_service
  ├── get_location_information
  └── log_agent_event
  ↓
Supabase / PostgreSQL
```

## Responsibilities
### Frontend
Owns the citizen experience: problem input, conversation, results, eligibility, documents, action plan, and official navigation.

### Backend
Owns API contracts, validation, persistence, tool execution boundaries, and event logging.

### Agent
Interprets intent, asks targeted questions, chooses tools, and produces structured outputs. It must not be the source of truth for government eligibility rules.

### Database
Stores verified scheme/service records, eligibility rules, documents, locations, requests, sessions, events, and action plans.

## Security and reliability
- Keep API keys server-side.
- Validate every tool input on the backend.
- Store source/reference and last verification date for government information.
- Never trust model output for authorization or data integrity.
- Log important agent events without storing unnecessary sensitive data.
- Fail safely when government data is missing, stale, or ambiguous.

## MVP deployment
- Frontend: Vercel
- Backend: Render or Railway
- Database: Supabase/PostgreSQL
- Source control: GitHub
