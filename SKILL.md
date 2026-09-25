---
name: ai-native-sdlc
description: Guide software work from intent through design, implementation, verification, and handoff using an AI-native development workflow. Use when starting a project workflow, implementing a feature, fixing a bug, or preparing a release with an explicit delivery outcome. Scale the process to the change; ordinary explanations and isolated code questions do not need this workflow.
license: MIT
metadata:
  version: "0.1.0"
---

# AI Native SDLC

Turn a software request into a verifiable result. Follow the user's requested endpoint: a plan, an implementation, a review, or an authorized release. Default to a solo developer workflow; preserve existing team policies when present.

This is an independent adaptation of Anthropic's [AI-Native SDLC Playbook](https://academy.claude.com/courses/ai-native-sdlc-playbook/introduction). See [source map](references/source-map.md) when explaining its origins or changing the workflow. It provides instructions, not enforced permissions, a background service, or a deployment integration.

## 1. Establish the task and available context

Read the user's request, existing authorization, applicable project instructions, and the relevant code or records. Identify the requested result, current behavior, constraints, and available verification tools. Resolve instructions using the host's precedence rules; this skill does not override them.

For a new workflow or an empty project, read [setup](references/setup.md). For an established project, reuse its commands, architecture, and record locations. Keep unrelated changes intact.

Ask only about missing decisions that materially affect behavior, data, architecture, cost, or authorization. Continue independent work while waiting. State reversible assumptions and proceed within scope. A request for explanation or planning ends at that deliverable unless implementation was also requested.

**Exit:** the requested endpoint, relevant context, and unresolved decisions are explicit.

## 2. Choose the lightest adequate path

| Path | Choose it when | Working record |
| --- | --- | --- |
| Small change | Local, well understood, reversible, with a clear expected result | A short task note or existing issue |
| Feature or substantial change | New behavior, multiple components, uncertain design, or a difficult reversal | Linked intent, spec, and plan |
| Bug fix | Existing behavior is wrong | Reproduction, intended behavior, fix plan, and regression evidence |

Record size and action risk are separate. Even a one-line access-control change can require a careful design and review. Data deletion, permissions, production operations, and irreversible migrations require explicit impact and recovery assessment under the project's policy.

For a small change, keep the note in the conversation unless the user or project requires a saved record. Use [change template](assets/templates/change.md) when a compact saved record is needed. For larger work, use [intent](assets/templates/intent.md), [spec](assets/templates/spec.md), and [plan](assets/templates/plan.md). Reuse an authoritative issue or document instead of creating a competing copy. For substantial work without an existing record location, use a unique `docs/changes/<change-id>/` folder in the user's project. Template placeholders are prompts to resolve or mark as not applicable.

Keep records versionable and link them to the change. Creating files does not require a commit; follow the user's Git workflow for commits, pushes, and pull requests.

**Exit:** the path and authoritative record are selected without adding unnecessary paperwork.

## 3. Capture intent and define acceptance

Write what the user wants, why it matters, affected users, constraints, and exclusions. For behavior changes, define acceptance criteria with observable outcomes, including relevant empty, error, and permission cases.

For substantial work, describe the design decisions that affect implementation: interfaces, data changes, user interaction, compatibility, and material tradeoffs. Keep product decisions distinct from implementation choices. Resolve a blocking ambiguity before changing the dependent behavior; carry nonblocking questions forward explicitly.

Treat an already explicit user request as established intent. Present new material decisions for the user's input; do not demand repeated approval of information already supplied.

**Exit:** someone outside the conversation can determine whether the proposed behavior satisfies the request.

## 4. Plan the change and its proof

Inspect the actual implementation before naming affected components. Map each acceptance criterion to a check. State the order of work, likely failure points, and recovery approach where needed. Keep a small change's plan to a few sentences.

For a bug, read [verification](references/verification.md) before editing: establish a reproduction and confirm that its failure matches the reported symptom. If reproduction is unavailable, distinguish the proposed repair from a confirmed fix.

A plan-only request finishes with the plan and open decisions. When implementation is authorized, continue after resolving material decisions. Preserve approvals already given; ask again only for a newly uncovered action outside that scope or a required gate.

**Exit:** the implementation approach and meaningful proof are clear enough to execute.

## 5. Implement with a feedback loop

Make cohesive changes and run the relevant fast checks as work progresses. If findings change the plan materially, update the record and explain the impact. Escalate a new product decision; resolve ordinary implementation details yourself.

Use parallel agents only when supported and useful: give independent tasks explicit boundaries, isolate conflicting edits, and verify the combined result. Serial execution remains a complete path. Follow the host's delegation policy.

Keep shared project guidance concise. A recurring failure may justify a targeted instruction, reusable skill, or automated check. Propose changes to shared policy or installed skills unless maintaining them is already in scope.

If the same failure recurs without new evidence, stop repeating the operation, summarize what is known, and choose a different diagnostic step or identify the missing prerequisite. A failed state-changing action needs state inspection before retrying.

**Exit:** the intended implementation exists, deviations are recorded, and relevant checks are ready for final verification.

## 6. Verify and review the current result

Read [verification](references/verification.md). Run checks against the current version, connect the results to acceptance criteria, and review the final diff for behavior, security, scope, and maintainability. Use an independent reviewer or fresh context when available and worthwhile; otherwise label the review as self-review.

Classify findings by impact. Resolve blocking findings or report the work as incomplete. Cosmetic suggestions do not automatically block delivery. Preserve the strength of acceptance checks; any correction to an invalid check needs an explicit reason and review of the changed expectation.

**Exit:** evidence supports the completion claim, or unmet criteria and missing verification are stated precisely.

## 7. Hand off; release only within the task

Use [handoff template](assets/templates/handoff.md) for substantial work, or the same fields in a short response: outcome, changes, verification, remaining limitations, and release status. Distinguish implemented, verified, released, and observed in operation. A passing build alone proves neither behavior nor deployment.

For release preparation, deployment, or incident work, read [release and maintenance](references/release-and-maintenance.md). A feature request alone does not establish production authorization. When authorization is required, prepare the concrete release and recovery details before requesting it. Existing scoped authorization remains valid.

For an incident, preserve evidence and propose the next corrective task. Add regression coverage and relevant workflow lessons within scope. Monitoring or scheduled follow-up requires an actual configured service and user authorization; a skill cannot keep itself running.

**Exit:** the user receives a truthful result at the requested endpoint, with any necessary next action explicit.
