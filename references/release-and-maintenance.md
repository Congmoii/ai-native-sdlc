# Release and maintenance

Read this only when release, deployment, or incident handling is in scope. An implemented feature may be handed off without deploying it.

## Prepare a reviewable release

Identify the target environment, exact revision or artifact, checks completed, configuration or data changes, health signals, and recovery procedure. Reuse the established release system. Explain any irreversible effect before the relevant decision.

Separate authorization by action and environment. Permission to edit code is not automatically permission to publish it, modify live data, or release to production. Honor existing scoped authorization and the project's required gates. If permission is missing, finish safe preparation before asking about the concrete remaining action.

Use the host's available tools and actual permissions. Keep production credentials scoped to the release mechanism; a prose instruction does not enforce credential isolation. Do not install deployment tools or weaken protections merely to finish a feature task.

**Exit:** the release can be assessed from its artifact, impact, evidence, and recovery plan, and the next action has the necessary authorization.

## Execute and confirm

Check the target state before execution and inspect the actual deployment result. If a state-changing call times out, inspect the target before retrying; an ambiguous response may have followed a successful action.

Observe the agreed health signals after deployment. If they fail, follow the authorized recovery procedure or escalate with evidence. Record the distinction between reverting application code and restoring changed data; a code rollback does not necessarily undo a migration.

**Exit:** the result is released and observed, recovered, or explicitly incomplete. Record the actual state instead of inferring success from a command submission.

## Close the loop

For an incident, collect the symptom, timeline, affected version, observed impact, and evidence. Separate confirmed facts from hypotheses. Propose a corrective intent or linked issue, then use the normal change workflow.

Retain regression coverage for the product defect. Add an agent evaluation case when the incident exposes a problem in the agent's decisions, instructions, or tool use. Update shared guidance only within the authorized scope.

If monitoring automation is requested, define a signal, an evidence-based threshold, an owner, allowed responses, and a stopping or escalation condition. Validate detection and response in a safe environment before enabling them. Use a deterministic detector for known thresholds; do not copy statistical bands from the source example without checking whether they fit the metric.

The initial response can be read-only diagnosis or a proposed patch. Automated production response requires a tested, authorized runbook and technical enforcement. Report monitoring as enabled only after an actual scheduler or service has been configured and checked.
