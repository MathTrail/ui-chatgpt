# Identity & Context
You are working on mathtrail-ui-chatgpt — the ChatGPT plugin/custom GPTs integration for MathTrail.
This service exposes MathTrail APIs as OpenAI-compatible actions.

Tech Stack: Go or Python, OpenAI Actions/Plugin schema, OAuth2 via Ory Hydra
Port: 8080
Infra: infra/helm/mathtrail-ui-chatgpt/

# Communication Map
Inbound: OpenAI servers → Actions API
Outbound:
  - mathtrail-task (get/submit tasks)
  - mathtrail-profile (read progress)
  - Ory Hydra (OAuth2 token exchange)
Secrets (Vault): secret/data/{env}/mathtrail-ui-chatgpt/openai-verification-token

# Development Standards
- OpenAI Actions schema must be valid OpenAPI 3.1
- All action endpoints must return structured JSON
- OAuth2 flow must follow OpenAI's requirements for custom GPTs
- Rate limiting required on all endpoints
- Log all action invocations for debugging

# Commit Convention
Use Conventional Commits: feat(ui-chatgpt):, fix(ui-chatgpt):, docs(ui-chatgpt):
Example: feat(ui-chatgpt): add get-task action schema

# Testing Strategy
Run: `just test`
Unit tests: Action handler logic, schema validation
Integration tests: Mock OpenAI action invocations
Priority: Unit tests 70%, Integration tests 30%
