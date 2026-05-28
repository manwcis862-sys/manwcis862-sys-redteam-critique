# Review Matrix

Use this file as a high-density checklist after routing the artifact type. Load relevant sections only. The goal is to catch real failure modes, not to generate decorative criticism.

## Universal Matrix

- Logic: unsupported premises, causality jumps, circular reasoning, contradiction between claim and evidence, missing counterexamples.
- Evidence: unverifiable data, citation gaps, cherry-picked samples, stale assumptions, unmeasured claims presented as measured facts.
- Feasibility: resource/time/cost mismatch, unowned dependencies, unrealistic deployment environment, untested operational assumptions.
- Robustness: edge inputs, dirty data, concurrency, degraded networks, missing retries, cascading failures, single points of failure.
- User reality: workflow friction, incentive mismatch, noncompliance by real users, low adoption, hidden maintenance burden.
- Security/privacy/compliance: injection, credential leakage, authorization gaps, data retention ambiguity, regulated-data exposure.
- Cost-benefit: overbuilt complexity, cheaper substitutes, negative ROI, unpriced operational cost, scaling cost curve.

## Mathematics And Algorithms

Attack:

- Variable definitions, dimensional consistency, matrix rank, eigenvalue/eigenvector loss, tensor shape alignment, vector field spatial meaning, convergence assumptions, boundary conditions, complexity, identifiability, statistical assumptions.
- Model simplification that removes variables carrying physical meaning.
- Dimensionality reduction that hides decisive eigenvalues or collapses a meaningful subspace.
- Convergence claims without proof under nonlinearity, noise, adversarial data, or non-stationary inputs.
- Statistical claims without sample-size justification, leakage control, confidence intervals, or distribution-shift analysis.

Exemption:

- Do not mark deliberate symbol simplification as a defect when it preserves meaning. Example: in a static model, simplifying meaningless `X_t` to `X` is valid if equation dimensions and physical mapping remain intact.
- Escalate only when simplification hides a dynamic process, breaks dimensional consistency, causes matrix rank/eigenvalue errors, or severs the physical interpretation.

Extreme tests:

- Push variables to boundary values and check whether formulas still make physical or statistical sense.
- Check whether reduced matrices preserve the decisive eigenstructure.
- Check whether an assumed monotonic relationship reverses under plausible parameter ranges.

## Software Architecture, Code, And AI Automation

Attack:

- Invalid inputs, race conditions, state consistency, idempotency, retries, backoff, rollback, observability, migration safety, version skew, dependency pinning, configuration drift.
- Authentication and authorization: token lifecycle, refresh failure, permission scope, secret storage, privilege escalation.
- External APIs: rate limits, 429 retry storms, partial outages, schema drift, pagination errors, timeout handling, quota exhaustion.
- AI systems: hallucinated outputs, tool-call failure, context pollution, prompt injection, evaluation leakage, untrusted model output written to databases, missing human-in-the-loop gates.
- Testing: missing negative tests, no integration tests around dependencies, no load tests for concurrency, snapshots masking behavior changes.

Extreme tests:

- Force token expiry mid-flow and check whether the system silently corrupts state.
- Inject malformed model output into the next step and check whether it contaminates storage or decisions.
- Simulate API 429/500 loops and verify backoff, circuit breaking, and recovery.
- Run concurrent writes against shared state and look for lost updates or double execution.

## Frontend, Data Pipelines, And Databases

Attack:

- Frontend: hydration mismatch, inaccessible controls, layout breakage on small screens, stale client cache, optimistic-update rollback failure, cross-browser incompatibility, localization overflow, unhandled offline state.
- Data pipelines: schema drift, late-arriving events, duplicate ingestion, missing idempotency keys, backfill corruption, timezone errors, partial batch failure, silent dropped rows.
- Databases: unsafe migrations, missing rollback, lock amplification, index absence, N+1 queries, transaction isolation mismatch, referential integrity gaps, unbounded retention.
- Analytics and metrics: vanity metrics, double-counting, bot traffic, attribution leakage, cohort contamination, dashboard latency hiding operational failure.

Extreme tests:

- Run a migration on a production-sized copy and check locks, rollback, and data invariants.
- Replay duplicate and out-of-order events through the pipeline.
- Test the narrowest supported viewport and the longest localized string.
- Force stale cache plus failed write and verify UI state recovery.

## Hardware, Medical Engineering, And BCI

Attack:

- Sampling rate, signal-to-noise ratio, sensor precision, calibration drift, temperature drift, latency, electromagnetic interference, biological variability, nonideal live-body data.
- Analog-to-digital conversion assumptions, quantization error, aliasing, impedance mismatch, timing jitter.
- Digital circuit state competition: latches, buses, display refresh, high-frequency state races, metastability, clock-domain crossing.
- Energy and thermal limits: heat loss, irreversible entropy increase, real transfer temperature, battery/patch heating, clinical safety constraints.
- Clinical or medical claims without population variance, artifact rejection, regulatory path, reproducibility, failure handling, or safety monitoring.

Extreme tests:

- Lower SNR to realistic live-signal levels and check whether the classifier still has separable features.
- Introduce electromagnetic interference, motion artifacts, or electrode impedance drift.
- Stress concurrent latch/bus timing and look for state contention.
- Compare thermodynamic efficiency claims against real losses rather than ideal-cycle assumptions.

## Business And Product

Attack:

- False demand, nonexistent target user, weak willingness to pay, high acquisition cost, low retention, ignored switching cost, fragile channel assumptions.
- Competitors and substitutes: cheaper manual workaround, platform feature copying, incumbent distribution advantage.
- Unit economics: gross margin, support cost, compliance cost, payment failure, churn, sales cycle, cash runway.
- Cold start: insufficient supply/demand liquidity, no repeatable acquisition loop, no trust mechanism.
- Operational reality: staffing, support, onboarding, legal exposure, procurement friction, localization, accessibility.

Extreme tests:

- Increase CAC by 3-10x and see when cash flow breaks.
- Assume users keep their current workaround and test whether the value proposition still survives.
- Remove the single strongest acquisition channel and see whether growth collapses.

## Articles, Papers, And Research Drafts

Attack:

- Concept switching, undefined key terms, causal claims from correlation, sample bias, overgeneralization, missing counterexamples.
- Citations that do not support the claim, stale references, unverifiable data, methods hidden behind vague phrasing.
- Formula/figure/table mismatch, unsupported conclusion, missing limitation section, selective baseline comparison.
- Rhetorical complexity that hides a weak contribution.

Extreme tests:

- Replace the core example with an adversarial counterexample and see if the thesis survives.
- Remove unsupported citations and check whether the argument still stands.
- Compare the conclusion strictly to measured evidence, not author intent.

## Personal Plans And Career Plans

Attack:

- Goal-resource mismatch, unrealistic time budget, no feedback loop, vague success criteria, dependence on motivation, ignored opportunity cost.
- Missing constraint: money, location, credentials, energy, health, family duties, access to mentors, market demand.
- No fallback path, no checkpoint, no kill criteria, no proof of skill transfer.

Extreme tests:

- Cut available time in half and see whether the plan still reaches its milestone.
- Remove the most optimistic assumption and see whether the plan still has a path.
- Ask what evidence would prove the plan is failing within 2-4 weeks.
