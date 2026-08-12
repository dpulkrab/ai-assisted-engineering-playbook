# AI-Assisted Pull-Request Review

AI can shorten the first review cycle by identifying common issues and assembling context before a human reviewer starts. It should complement, not replace, accountable engineering review.

## Best-Fit Checks

- Missing or inconsistent tests
- Error handling and boundary conditions
- API and schema compatibility
- Concurrency and resource-management risks
- Security-sensitive input or data flows
- Logging, observability, and operational readiness
- Documentation and acceptance-criteria alignment
- Repetition or complexity that reduces maintainability

## Workflow

1. Retrieve the pull-request diff, repository guidance, relevant design decision, and acceptance criteria.
2. Identify changed behavior and affected components.
3. Run deterministic checks first: build, tests, formatting, static analysis, dependency and vulnerability scanning.
4. Ask AI to review areas not fully covered by deterministic tools.
5. Require every finding to identify location, risk, reasoning, and suggested validation.
6. Let the author or reviewer accept, reject, or reframe each finding.
7. Track false positives and missed issues to improve the workflow.

## Review Prompt Contract

An effective review instruction should ask the model to:

- Use only supplied or permissioned context.
- Distinguish evidence from inference.
- Avoid style comments already enforced by automation.
- Prioritize correctness, security, reliability, and maintainability.
- State uncertainty and request missing context.
- Avoid proposing broad refactors unrelated to the change.
- Return no finding when evidence is insufficient.

## Useful Measures

- Time from review request to first useful feedback
- Initial review cycle time
- Findings accepted, rejected, and duplicated by deterministic tools
- Defects caught before merge
- Post-merge defects associated with reviewed changes
- Author and reviewer satisfaction

An improvement in speed is valuable only when quality and reviewer trust remain stable or improve.
