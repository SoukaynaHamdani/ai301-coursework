 
# Evidence guide: where evidence lives in a plan package

## Diagnosis and grounding

- **Where it lives:** In the candidate plan's diagnosis or problem analysis section, read directly against the package's repro-evidence block and the issue context.
- **What good looks like:** The stated cause cites behavior the repro evidence actually shows, without contradicting the terminal logs or targeting a surface-level symptom while evidence points upstream.

## Scope

- **Where it lives:** In the candidate plan's scope statement, specifically looking at the in-scope statement, the not-in-scope line, and the named files or areas.
- **What good looks like:** Clear, explicit boundaries that fence out unrelated components and restrict changes strictly to one bounded change rather than an unrequested drive-by rewrite.

## Executability

- **Where it lives:** In the plan's approach, order of work, and the list of files or areas that will actually be touched.
- **What good looks like:** Names the exact files and details a logical, sequential workflow so that a stranger could start executing without asking the author anything.

## Test plan

- **Where it lives:** In the plan's test plan section, read against the repro evidence's steps and artifacts.
- **What good looks like:** Names a concrete, observable before/after output pair (expected output stated in advance) rather than using a vague instruction like "run tests".

## Honesty

- **Where it lives:** In the plan's risks, unknowns, and deviations sections.
- **What good looks like:** Explicitly acknowledges gaps and technical uncertainties rather than dressing them up as false confidence, and records mid-build changes honestly under deviations.

## Comms

- **Where it lives:** In the draft plan comment read against the issue's maintainer signals (thread highlights) and the repo-facts block's stated templates, contributing asks, and contribution policy.
- **What good looks like:** Directly addresses maintainer instructions and repo policies (including AI-use disclosures) with thread-aware specifics rather than falling back on generic boilerplate.