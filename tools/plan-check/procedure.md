# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->



## Read order
1. Locate the practice submission file (e.g., `pkg-XX.md` or a real plan file) inside the evaluation packages or root repository directory as requested.
2. Read the `scope.md` file first to understand the target repository constraints and boundary definitions.
3. Read `rubric.md` to load all check names, evidence definitions, pass conditions, and weights into context.
4. Read the target plan file (`plan.md`) and any accompanying draft comment file (`comment.md`) completely from top to bottom before performing any evaluation.

## Evidence gathering
1. For each check defined in `rubric.md`, consult `references/evidence-guide.md` to identify the precise file locations and sections in the practice submission where the required evidence resides.
2. Extract exact, verbatim text lines from the plan and the package context (such as stated diagnosis lines, repro evidence steps, and scope fences) rather than relying on general impressions or vibes.
3. Cross-reference the plan's stated diagnosis and test plan against the original reproduction evidence steps to detect any contradictions or unsupported assumptions.
4. Compile the gathered quotes and references systematically for each individual check row.

## Check execution
1. Iterate sequentially through every check listed in the `rubric.md` checks table.
2. Evaluate the gathered evidence for the current check strictly against its defined **Pass condition**.
3. Assign a deterministic grade for each check: `pass` if the condition is fully met, `fail` if it violates the condition, or `?` (unclear) if the evidence is missing or ambiguous.
4. Record precisely one line of quoted evidence from the submission alongside each check's grade to justify the outcome.

## Verdict assembly
1. Review all assigned check grades (`pass`, `fail`, or `?`) across the entire rubric.
2. Apply the strict **Verdict rule** outlined in `rubric.md`: ensure all required/major checks pass without unhandled failures or ambiguous `?` marks (noting that any `?` defaults to a fail if unhandled).
3. Determine the final binary verdict: output **Accept (ready)** if all criteria are satisfied, or **Hold (reject)** if any critical/major check fails or if evidence collides.
4. Output the final structured evaluation summary containing the per-check results, exact quotes, and the final JSON-compatible verdict block.




