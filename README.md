# mathtrail-ui-chatgpt
ChatGPT integration — enables students to interact with MathTrail through OpenAI's custom GPTs or plugin ecosystem.

## Mission & Responsibilities
- Expose MathTrail API as OpenAI-compatible actions
- Provide task retrieval and submission via conversational interface
- Translate between ChatGPT function calls and MathTrail API

## Tech Stack
- **Language**: Go or Python
- **API**: OpenAI Actions / Plugin schema
- **Auth**: OAuth2 via Ory Hydra

## API & Communication
- **Inbound**: OpenAI → Actions API
- **Outbound**: mathtrail-task, mathtrail-profile

## Roadmap
1. Define OpenAI Actions schema (get-task, submit-answer, get-progress)
2. Implement OAuth2 flow with Ory Hydra for ChatGPT auth
3. Build action handlers that proxy to internal Dapr services
