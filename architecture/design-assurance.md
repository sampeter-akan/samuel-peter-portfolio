# GridPulse — Design assurance checklist
Recorded: 10 November 2026. Scope: portfolio simulation architecture. This is a review checklist with evidence states, not a production certification.
| Area | Review criterion | Current evidence / required check |
| --- | --- | --- |
| Functional scope | Clearly distinguish simulation from operational control | Portfolio identifies simulation; validate all control boundaries before any operational integration |
| Availability | Keep diagnostic interaction usable during dependency failure | Client/server fallback paths exist; test failure modes and rule consistency |
| Performance | Set response-time budgets and request deadlines | No measured SLO or explicit client fetch timeout established |
| Security and privacy | Protect credentials; validate and minimise payloads | Reviewed Express code reads key server-side; deployment configuration, authentication and telemetry access need assurance |
| Data contracts | Validate inputs and diagnostic responses | Typed client report and server JSON parsing exist; runtime contract enforcement requires review |
| Recoverability | Define state restoration, event retention and replay expectations | Stable-scenario restoration observed; durable retention and recovery need separate evidence |
| Observability | Link region, mode, request and resulting events | SOE workflow observed; distributed tracing and correlation IDs require verification |
| Integration | Document API ownership, schema, versioning, failure and trust boundaries | /api/diagnostics request/response path inspected; production interface contract requires assurance |
| Cost and sustainability | Compare call volume, cost, model use and hosting footprint | Document drivers; establish baseline measurements before numeric targets |
| Human oversight | Separate assessment from authority to execute | UI offers explicit Execute controls; operational authorisation and interlocks are release gates |
## Design review method
Record scope, requirements and at least two viable options. Review cost, quality attributes and risks; capture the decision in an ADR. For exceptions, name the accountable owner, target date, compensating control and closure evidence. An investment assurance position should state evidence reviewed, unresolved risks and approval conditions; this checklist is not that approval.
## Architecture runway
1. Baseline contracts and scenario regression fixtures before expanding diagnostic coverage.
2. Unify fallback semantics and enforce timeouts/schema validation before resilience claims.
3. Establish identity, secure integration boundaries, tracing and recovery evidence before operational connectivity.
4. Measure performance and cost before funding a scale-out design.
These are sequencing criteria, not claims of funded delivery or achieved service levels.
