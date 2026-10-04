# AI Agent Skills

A collection of reusable skills that help AI agents perform focused engineering tasks with evidence, clear scope, and practical validation.

The skills are portable across repositories and teams. They avoid company-specific services, internal infrastructure, and mandatory tool integrations. Agents adapt each workflow to the project and tools available to them.

## Skills

| Skill | Purpose |
| --- | --- |
| [Code Review](code-review/SKILL.md) | Review patches and pull or merge requests for actionable defects, compatibility risks, and meaningful test gaps. |
| [SLO Define](slo-define/SKILL.md) | Define user-centered reliability indicators, objectives, error budgets, and alerting from actual telemetry. |
| [Performance Engineer](performance-engineer/SKILL.md) | Diagnose measured performance problems and validate targeted improvements under comparable conditions. |
| [Workflow Planner](workflow-planner/SKILL.md) | Turn requirements into actionable work items, dependency order, and acceptance checks. |

## Structure

Each skill has its own folder with a `SKILL.md` entrypoint. Conditional supporting guidance lives in that skill's `references/` folder and is linked from the entrypoint.

## Using the collection

Read the relevant `SKILL.md` and provide the agent with the task and project context. For agents that support skill discovery, copy the entire skill folder into the location documented by that agent. Keep reference files alongside the entrypoint. Installation and invocation conventions vary by agent.

Skills guide decisions; they do not supply credentials, grant permissions, or guarantee results. Follow the project's instructions and validate outcomes with the available tools. External actions remain subject to the user's authorized scope.

## Adding skills

Give each skill a focused name and description, a clear scope, and guidance that improves decisions beyond generic advice. Include supporting resources only when useful. Keep examples free of secrets and internal assumptions, and verify links and behavior before submitting a change.
