# AI Native SDLC

**A practical skill for taking software work from an idea to a verified result.**

Version 0.1.0. Written in English for an international audience. Designed for solo developers, with room for an existing team's policies.

Based on the ideas in Anthropic's [AI-Native SDLC Playbook](https://academy.claude.com/courses/ai-native-sdlc-playbook/introduction). This is an independent implementation, not an official Anthropic product or a copy of the course.

## What it does, in plain English

Give your AI a request. The skill helps it understand the outcome, inspect the project, choose an approach, make the change, check the result, and explain what is ready.

```text
Understand -> Design -> Plan -> Build -> Verify -> Hand off
    ^                                                 |
    +------- Feedback or an authorized incident -------+
```

It scales the paperwork to the work:

| Your request | What the skill uses |
| --- | --- |
| Fix a typo | A short plan, the edit, and an appropriate check |
| Fix a bug | A reproduction, a targeted repair, and regression evidence |
| Add a feature | An intent, a spec, a plan, implementation, and verification |
| Plan a feature only | The plan and unresolved decisions; implementation waits for a request |
| Prepare a release | A specific release artifact, checks, impact, and recovery details |

You make important product decisions. The AI handles ordinary implementation details within the scope you have given it. Existing approval is reused; a newly discovered action outside that scope still needs the appropriate decision.

## Install in Claude Code

Extract the distribution ZIP, or download or clone this repository. Copy the **complete skill package**, including `SKILL.md`, `references/`, and `assets/`, into one of these locations, naming the folder `ai-native-sdlc`. If copying a Git clone, exclude its `.git/` directory so the installation does not become a nested repository:

- Personal installation: `~/.claude/skills/ai-native-sdlc/`
- Installation shared with a project: `<your-project>/.claude/skills/ai-native-sdlc/`

On Windows, `~` means your user profile directory. Verify that `SKILL.md` sits directly inside `ai-native-sdlc`; avoid an extra nested repository folder. If a skill with that name already exists, compare it before replacing it.

Start or restart Claude Code if the new skill is not discovered, then use:

```text
/ai-native-sdlc Add product search by name to this application.
```

Claude Code can also select skills based on their descriptions. Explicit invocation is a useful way to check the installation. These paths and invocation syntax follow the [official Claude Code skill documentation](https://code.claude.com/docs/en/skills).

## Use with another AI tool

The package uses the [Agent Skills format](https://agentskills.io/specification), ordinary Markdown, relative references, and standard frontmatter. It has no required executable helpers or service connections.

If your tool supports Agent Skills, use its documented installation location and invocation syntax. If it does not, provide `SKILL.md` and its referenced files as instructions and context. That fallback requires you to make the files available; it does not provide automatic skill discovery.

Formatting compatibility does not guarantee equal behavior across tools. Project access, command execution, browser inspection, subagents, permissions, and deployment depend on the host. The package has not been validated inside every supported host; see [evaluation status](EVALUATION.md).

## Your first task

For a project that already exists:

```text
Use ai-native-sdlc to add product search by name.
Reuse the project's existing stack and conventions.
Search should ignore letter case and surrounding spaces.
An empty search should show all products.
Implement and verify the change locally.
```

For a new workflow:

```text
Use ai-native-sdlc to establish a lightweight development workflow here.
Inspect the project first, document the commands you can verify,
and set up the smallest useful change record and feedback loop.
```

For planning only:

```text
Use ai-native-sdlc to plan a CSV export feature.
Explain the proposed behavior and tradeoffs before implementation.
Stop at the plan.
```

You do not need to speak in templates. Describe what you want in your own words; the agent can draft the records. The package is in English, but it does not force a language on your conversations or project documents.

## Three documents, three questions

| Document | Question it answers |
| --- | --- |
| `intent.md` | What do we want, and why? |
| `spec.md` | How should the result behave? |
| `plan.md` | How will we build and check it? |

These records belong to the project being changed, not to the installed skill. The default folder for substantial work is `docs/changes/<change-id>/`; an existing issue system can remain authoritative instead. Small tasks can use a single note.

## What is included

- [SKILL.md](SKILL.md): the main instructions the AI follows.
- [Setup guide](references/setup.md): establishing a workflow from zero.
- [Verification guide](references/verification.md): useful checks and honest completion claims.
- [Release and maintenance guide](references/release-and-maintenance.md): conditional release and incident work.
- [Templates](assets/templates/change.md): compact change, intent, spec, plan, handoff, and project guide.
- [Feature example](examples/feature.md), [bug example](examples/bug-fix.md), and [small change example](examples/small-change.md): examples of the workflow at different sizes.
- [Source map](references/source-map.md): links to the original lessons and the adaptations made here.
- [Evaluation guide and status](EVALUATION.md): scenarios and the limits of validation.

## What still needs real tooling

A skill cannot enforce permissions, run without a host, keep monitoring after a conversation ends, or prove a result it cannot inspect. Build commands, tests, access controls, CI, and deployment systems remain project responsibilities. The skill asks the AI to report unavailable checks clearly.

It does not install hooks, start scheduled jobs, create accounts, or publish a repository merely by being loaded. Those are separate actions governed by the user's request and available permissions.

## Share on GitHub

Use this folder as the repository root. A suggested repository name is `ai-native-sdlc`. Include the full folder contents, especially the supporting files and license. Do not upload only `SKILL.md`.

Suggested repository description:

> A practical Agent Skill for software delivery, inspired by Anthropic's AI-Native SDLC Playbook. Lightweight by default, with verifiable outcomes.

When distributing a ZIP, keep one top-level `ai-native-sdlc/` folder so recipients can copy it directly into their tool's skill directory. Remove any local task records, credentials, or private project files before sharing your own modified package.

## Contribute

Open an issue with a realistic request, expected behavior, actual behavior, and the host/model used. Remove private data. For a pull request, explain the behavioral improvement, run the relevant scenarios in [EVALUATION.md](EVALUATION.md), and check that every local link still resolves. Prefer a specific correction over a growing list of universal rules.

## License and attribution

Original package material is provided under the [MIT License](LICENSE). Linked third-party materials remain subject to their own terms. The source map identifies inspiration; it does not imply endorsement or extend this package's license to the course.
