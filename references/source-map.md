# Sources and adaptations

Reviewed on September 7, 2026. This package expresses its own workflow instructions and templates; it does not reproduce the course, its illustrations, or its configuration examples.

## Playbook mapping

| Original lesson | Principle used here | Where it appears |
| --- | --- | --- |
| [Introduction](https://academy.claude.com/courses/ai-native-sdlc-playbook/introduction) | Connect stages through inspectable outputs and feedback | Main workflow |
| [Capture as intent.md](https://academy.claude.com/courses/ai-native-sdlc-playbook/capture-intent) | Record the requested outcome and constraints | Intent template |
| [Requirements and design](https://academy.claude.com/courses/ai-native-sdlc-playbook/requirements-and-design) | Make intended behavior and decisions explicit | Spec template |
| [Plan mode](https://academy.claude.com/courses/ai-native-sdlc-playbook/plan-mode) | Inspect before implementation; keep the approach reviewable | Planning step |
| [The CLAUDE.md](https://academy.claude.com/courses/ai-native-sdlc-playbook/claude-md) | Maintain concise project knowledge | Setup guide and project guide template |
| [Skills as institutional knowledge](https://academy.claude.com/courses/ai-native-sdlc-playbook/skills-as-institutional-knowledge) | Reuse instructions; distinguish guidance from enforcement | Skill boundaries and setup |
| [Parallel sessions and subagents](https://academy.claude.com/courses/ai-native-sdlc-playbook/parallel-sessions-and-subagents) | Isolate independent work and integrate deliberately | Optional parallel implementation |
| [Give Claude a feedback loop](https://academy.claude.com/courses/ai-native-sdlc-playbook/give-claude-a-feedback-loop) | Verify through observed results and preserve regression evidence | Verification guide |
| [Continuous evals in CI](https://academy.claude.com/courses/ai-native-sdlc-playbook/continuous-evals-in-ci) | Evaluate changes to agent behavior on representative tasks | Setup and evaluation guide |
| [AI in the PR review loop](https://academy.claude.com/courses/ai-native-sdlc-playbook/ai-in-the-pr-review-loop) | Review intent, defects, and risk consistently | Final review |
| [Hooks as approval gates](https://academy.claude.com/courses/ai-native-sdlc-playbook/hooks-as-approval-gates) | Enforce critical boundaries through technical controls | Setup and release guide |
| [CI/CD integration and deployment](https://academy.claude.com/courses/ai-native-sdlc-playbook/ci-cd-integration-and-deployment) | Scope automation by environment and prepare recovery | Release guide |
| [Closing the loop on metrics](https://academy.claude.com/courses/ai-native-sdlc-playbook/closing-the-loop-on-metrics) | Turn observed incidents into corrective work | Maintenance guide |
| [Closing thoughts and resources](https://academy.claude.com/courses/ai-native-sdlc-playbook/closing-thoughts-and-resources) | Introduce capabilities in a deliberate order | Setup guide |

## Deliberate adaptations

- **Solo developer default:** the user owns product decisions and risk acceptance. Existing team roles and policies still apply where present.
- **Proportionate records:** small tasks use a compact note; significant changes use intent, spec, and plan. The source's committed artifact chain is not forced onto every edit.
- **Existing authorization:** explicit requests can already establish intent and authorize implementation. The skill asks about new material decisions and actual gates, rather than adding repeated sign-offs.
- **Portable instructions:** standard frontmatter and Markdown replace dependencies on Claude-only commands or services. Claude Code installation is documented as a verified format and path, not a claim of runtime testing.
- **Optional parallelism:** a single agent can complete the workflow; additional agents are a capability-dependent aid.
- **Evidence over a blanket test-file freeze:** the source describes blocking edits to tests during repairs. This package preserves assertions while allowing an invalid expectation to be corrected with explicit evidence and review.
- **Automation as a later step:** CI evaluations, hooks, monitoring, and production actions need actual infrastructure and authorization. This package does not implement that infrastructure.
- **No universal metric thresholds:** choose thresholds from a project's data and operational needs instead of applying the source's illustrative statistical bands everywhere.

## Packaging references

The [Agent Skills specification](https://agentskills.io/specification) defines the folder and metadata format. The [Claude Code skills documentation](https://code.claude.com/docs/en/skills) defines Claude Code's installation and invocation behavior. Consult the current documentation for another host before adding host-specific instructions.
