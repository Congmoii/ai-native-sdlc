# Evidence before completion

Use this for bug diagnosis and the final verification pass. Inspect project-defined checks first; choose additional checks according to changed behavior and risk.

## A useful check

A check must distinguish the intended behavior from a plausible failure. Derive expected results from the requirement or existing contract, not from the implementation's current output. A test that only repeats implementation details or always passes adds no evidence.

| Change | Useful evidence |
| --- | --- |
| Text or formatting | Inspect the relevant diff; preview the affected output if appearance matters |
| Logic | Focused tests of normal and meaningful edge cases |
| API or data contract | Integration checks of inputs, responses, failures, and affected consumers |
| UI interaction | Exercise the interaction; inspect the rendered state and relevant layout sizes |
| Access control | Positive and negative permission cases using suitable test identities |
| Data migration | Representative migration and recovery rehearsal in a safe environment |

These are selection criteria, not a universal demand to run every category. A small copy edit does not need a new automated test solely to prove a string changed.

## Bug fixes

1. Establish the expected behavior from a contract or the user's report.
2. Reproduce the symptom before changing the implementation. Prefer a regression test; otherwise retain a repeatable manual procedure and observations.
3. Confirm the failure is relevant. A missing dependency or unavailable service does not reproduce a business-logic bug.
4. Repair the cause and run the same check again. Exercise the nearest affected behavior as well.
5. Preserve the regression check. Correct a mistaken expectation only with explicit evidence of the intended behavior; record that correction separately from the repair.

If reproduction cannot run, investigate as far as the evidence supports and report the missing prerequisite. A plausible patch is not a verified repair.

## Final review

Inspect the complete current diff, including tests and configuration. Check alignment with intent, unintended behavior changes, data handling, boundary cases, and maintainability. Look for unrelated changes or weakened assertions that could hide a failure.

For each actionable finding, give its location, triggering condition, impact, and supporting evidence. Reserve blocking status for a defect or required policy violation that prevents the requested outcome. Record speculative concerns as uncertainties, not confirmed bugs.

An independent review provides a different perspective when available. A second agent still needs evidence and does not acquire approval authority by being a reviewer.

## Report accurately

Record the check, environment, code version or working-tree state, result, and relevant evidence location. Distinguish passed, failed, and not run. If the code changes after verification, rerun checks affected by that change.

Use the project's required checks. An existing unrelated failure should be identified with baseline evidence where possible; it is not automatically permission to skip a required gate. Summarize the practical limitation instead of declaring all checks green.

Keep secrets and personal data out of shared logs. A screenshot proves the visible state captured, not every interaction. A model's confidence is not a substitute for observed results.
