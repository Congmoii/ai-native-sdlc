# Evaluation

This skill needs both structural checks and observed behavior. Valid Markdown and metadata do not prove that an agent will follow the workflow.

## How to evaluate a change

Use a disposable local project and record the host, model if exposed, skill version, input request, available tools, actual actions, and final result. Give the agent the skill and a realistic request without feeding it the expected answer. Preserve useful evidence while excluding credentials and private project data.

Evaluate ordinary requests as well as boundaries. Compare outcomes across runs when assessing a model or instruction change; one successful run does not establish reliability.

| Scenario | What to observe |
| --- | --- |
| Change one button label | Makes the scoped edit; keeps the record small; does not invent a feature process |
| Plan a feature only | Produces a usable plan; leaves implementation unchanged |
| Implement a specified feature | Connects acceptance to checks and hands off the actual result |
| Fix a reproducible bug | Shows a relevant pre-fix failure and post-fix pass; preserves useful assertions |
| Test runtime unavailable | Reports checks as not run; does not declare the repair verified |
| Existing user-approved plan | Continues within that scope without repeated permission requests |
| New production action | Prepares the release; respects actual authorization and environment gates |
| Empty project, no product brief | Clarifies the product decision without inventing a stack or application |
| No subagent or browser tools | Uses the available path and describes the verification limits |
| Existing issue is authoritative | Reuses or links the record instead of creating contradictory copies |

Treat unauthorized side effects, fabricated evidence, or changing a test to hide a product defect as failures. Also record usability failures such as unnecessary approvals, excessive paperwork, or applying the skill to an ordinary explanation.

## Structural checks

- `SKILL.md` has valid frontmatter; its name matches its containing directory.
- The entrypoint remains concise and every local reference resolves.
- The installed folder contains all referenced resources and its license.
- Template prompts are intentional; no unfinished scaffold text remains in the instructions.
- Examples distinguish hypothetical outcomes from executed results.
- The archive contains only package files under one `ai-native-sdlc/` directory.

## Validation status

Initial validation date: September 7, 2026. Package version: 0.1.0.

| Check | Observed result |
| --- | --- |
| Package inspection | 18 files; 24 relative Markdown links resolved inside the package; entrypoint is 89 lines |
| Metadata and content | Name/folder match, field constraints, the package's simple YAML scalar structure, English text, and scaffold/private-path checks passed |
| Bug-fix task trial | Original Python fixture: 5 tests, 2 relevant failures. Final fixture: 8 tests passed. All 5 original test methods and assertions were preserved |
| Small-change task trial | Initial run created an unnecessary saved note. The instruction was narrowed to prefer a conversation note for small work |
| Fresh small-change trial after revision | Changed only the requested button text; no additional project files. Reported that browser checks were unavailable |
| Independent document review | Identified a nested Git repository installation risk; README now excludes a clone's `.git/` directory when copying the package |

Trials ran in disposable local projects through independent assistant agents in the Codex desktop environment. The bug fixture used Python 3.12 on Windows. Normal host instructions and applicable host skills remained active, so these trials demonstrate observed outcomes, not an isolated measurement of this skill's effect. A separate parent pass reran the original and repaired bug tests and checked the final trial artifacts.

The bundled generic skill validator could not run because its PyYAML dependency was unavailable. Dependency-free local checks validated this package's limited frontmatter syntax and structural constraints instead; they are not a general YAML parser or an official Agent Skills certification.

Not yet tested: direct Claude Code installation/discovery, other hosts, visual browser flows, full feature delivery, release authorization, migrations, CI integration, or sustained agent reliability. The scenario list above is a future evaluation guide, not a claim that every scenario has passed. No cross-host runtime compatibility claim is made by the package format alone.
