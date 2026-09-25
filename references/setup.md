# Starting from zero

Read this when the user asks to establish a development workflow or starts with an empty project. A setup request does not authorize inventing an application or choosing a costly service.

## Discover before choosing

Inspect the directory and available tools. If no application exists, establish what the user wants to build before recommending a stack. If an application exists, identify its actual install, run, build, and test commands. Mark a command as unverified until it has run successfully in the relevant environment.

Keep the initial setup small:

1. One place for project instructions.
2. One authoritative place for change records.
3. A way to run the application or inspect its output.
4. A check that can demonstrate a meaningful success or failure.

**Exit:** these four items exist or their missing prerequisites are named. Do not report an environment as ready just because instructions were written.

## Project instructions

Adapt the [project guide template](../assets/templates/project-guide.md) to the host's supported project instruction mechanism. Use `CLAUDE.md` for Claude Code. Other hosts may use a different file or configuration; verify their documentation before installing an adapter.

Record the product's purpose, meaningful architectural boundaries, verified commands, and the mistakes or conventions the environment cannot explain on its own. Link to maintained policies instead of copying them. Keep the main file short; use component-level guidance only when it changes decisions in that component.

For several tools, designate one policy source. Point each supported adapter to it explicitly; a filename alone does not guarantee that a tool will read it. Avoid conflicting copies.

## First feedback loop

Choose a representative local task with an observable result. Establish a baseline, make the change, and verify the outcome. For a UI, include inspection of the rendered result when tools are available. For a bug, preserve the reproduction as regression coverage where practical.

Store the record near the code or in the user's existing issue system. Git makes records reviewable when it is part of the project; use the user's established commit and publication policy.

## Add automation after the workflow works

When repeated manual checks are reliable, consider moving them into CI. Before requiring a hook or permission gate, confirm that the host supports it and test both an allowed action and a blocked action. Documentation is not an enforcement mechanism.

Begin agent evaluation with representative real requests and known acceptable outcomes. Record the host, model, skill version, tools, and budget. Re-run relevant cases after behavior-changing instruction or model updates. Increase the case set as failures reveal useful coverage; the playbook's larger evaluation suite is a later target, not a prerequisite to a first task.

Measure a few useful outcomes: time to a verified result, work repeated after review, and defects discovered after delivery. More generated code is not itself evidence of improvement.
