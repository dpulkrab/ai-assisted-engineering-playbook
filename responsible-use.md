# Responsible Use Guardrails

AI assistance changes the speed and volume of engineering output. It does not change who is accountable for security, correctness, privacy, architecture, or production impact.

## Data Boundaries

- Classify source code, customer data, logs, credentials, architecture, and incident records before connecting them to a model.
- Use only approved models, accounts, integrations, and retention settings.
- Minimize context. Retrieve the smallest relevant set instead of copying an entire repository or knowledge base.
- Redact secrets, personal data, customer identifiers, and regulated information unless an explicitly approved workflow requires them.
- Keep authorization aligned with the calling user. An AI tool must not become a path around access controls.

## Action Boundaries

| Action | Default control |
| --- | --- |
| Summarize approved documentation | Human spot-check |
| Suggest code or tests | Engineer review plus automated validation |
| Comment on a pull request | Engineer validates findings before disposition |
| Create work items | Human confirms scope, priority, and ownership |
| Query production telemetry | Read-only access, audit trail, and data minimization |
| Change production configuration | Explicit approval and existing change controls |
| Mitigate an incident | Human authorization; automate only proven, bounded actions |

## Output Verification

- Confirm claims against authoritative sources.
- Run tests, static analysis, security checks, and policy checks where applicable.
- Review edge cases, failure modes, concurrency, data handling, and backward compatibility.
- Treat plausible explanations as hypotheses until supported by telemetry or reproducible evidence.
- Record the model, workflow version, relevant inputs, and reviewer for high-risk actions.

## Stop Conditions

Pause or disable a workflow when it:

- Exposes data beyond its intended audience.
- Produces recurring false confidence or unverifiable claims.
- Bypasses an established security or release control.
- Creates more review burden than useful leverage.
- Makes ownership ambiguous.
- Degrades quality, reliability, or team trust.
