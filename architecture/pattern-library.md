# GridPulse — Architecture pattern library sample
Recorded: 10 November 2026. Scope: project implementation and review criteria.
## P-01 — Explicit diagnostic fallback
Intent: retain a diagnostic report when the AI service is unavailable.
Implementation: client and server deterministic branches with isAiGenerated mode labelling.
Use when: rules cover a bounded scenario set and users can inspect the mode.
Trade-off: duplicate rules can drift. Review rule parity, timeout behaviour and response validation; track the current discrepancy in EX-001.
Evidence: [client service](https://github.com/sampeter-akan/gridpulse-330app/blob/00f6407f9618d60868c3b1199e65183030e24257/src/services/gemini.ts), [server](https://github.com/sampeter-akan/gridpulse-330app/blob/00f6407f9618d60868c3b1199e65183030e24257/server.ts), [advisor](https://github.com/sampeter-akan/gridpulse-330app/blob/00f6407f9618d60868c3b1199e65183030e24257/src/components/AiDispatchAdvisor.tsx).
## P-02 — Region-parameterised assessment
Intent: keep operating limits and regional context explicit in diagnostic requests.
Implementation: request includes region and telemetry; deterministic checks use configured voltage/frequency bounds.
Review: fixture identical scenarios across configured profiles; do not infer regional regulatory compliance solely from configured thresholds.
## Integration standard sample — Diagnostics API boundary
Identify the request owner, consumer, schema version, trust boundary and retention policy. Define validation rules, deadline, error semantics, correlation ID and mode provenance. Assess personal/sensitive content before enabling external AI processing. APIs and event streams are distinct integration mechanisms: the inspected diagnostics path is HTTP JSON, not evidence of a deployed event-streaming platform.
## Cloud portability
Separate UI, diagnostic contract, rule logic, AI-provider adapter, secrets and telemetry concerns. Evaluate hosting against identity, network, recovery, observability and cost requirements. These patterns transfer across cloud vendors; AWS practical delivery and academic Azure/GCP knowledge remain distinct experience statements.
