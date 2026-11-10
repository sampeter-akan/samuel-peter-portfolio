# GridPulse — Architecture exception and design-risk register
Recorded: 10 November 2026. Scope: project design review. EX-001 is an observed review item; the blank record below is reusable for controlled exceptions.
## EX-001 — Client/server diagnostic rule divergence
State: open design risk; no waiver or approval recorded.
Evidence: client includes an under-frequency condition; server fallback does not include an equivalent branch. Other condition coverage also differs.
Impact: an identical simulated snapshot can receive different classifications depending on which fallback executes.
Accountable owner: assignment required from the project maintainer.
Target remediation date: to be assigned at design review; closure is required before treating both paths as equivalent.
Interim constraint: record diagnostic mode/path and do not claim semantic parity.
Closure evidence: agreed shared rules or documented deliberate differences, regression fixtures covering both paths, reviewed ADR and recorded sign-off.
Sources: [client](https://github.com/sampeter-akan/gridpulse-330app/blob/00f6407f9618d60868c3b1199e65183030e24257/src/services/gemini.ts), [server](https://github.com/sampeter-akan/gridpulse-330app/blob/00f6407f9618d60868c3b1199e65183030e24257/server.ts).
## Reusable exception record
- ID and affected requirement/pattern:
- Scope and business rationale:
- Alternatives and cost/risk assessment:
- Accountable owner:
- Approval authority and decision date:
- Remediation target date:
- Compensating controls:
- Review cadence:
- Expiry/escalation condition:
- Closure evidence and decision reference:
No approval, ownership assignment or completion date is implied by an unfilled record.
