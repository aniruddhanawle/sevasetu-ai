# SevaSetu AI — User Flow

```text
Landing
  ↓
Describe your problem (text / voice)
  ↓
Agent extracts intent + known facts
  ↓
Are decision-critical facts missing?
  ├─ Yes → Ask targeted clarification → update profile
  └─ No
  ↓
Search verified schemes
  ↓
Eligibility evaluation
  ↓
Ranked scheme matches
  ↓
Why does this match me?
  ↓
Scheme details + benefits + warnings
  ↓
Required documents
  ↓
Personalized action plan
  ↓
Official government service route
  ↓
Optional clearly-labelled demo/status state
```

## UX rules
- Start from the citizen's problem, not a scheme catalogue.
- Ask the minimum number of questions needed for a reliable decision.
- Separate verified facts from AI interpretation.
- Explain matches using concrete stored eligibility facts.
- Show source/reference and verification date for government information.
- Keep official navigation distinct from simulated actions.
- Always provide a graceful fallback when no scheme matches.
