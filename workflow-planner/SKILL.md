---
name: workflow-planner
description: Turn a product specification or complex request into an actionable implementation plan with dependencies and validation. Use for planning and task decomposition; implementation requires the user's requested scope.
---

# Workflow Planner

Read the requirements and available project context. Extract user outcomes, acceptance criteria, constraints, exclusions, and unanswered questions. Keep assumptions visibly separate from confirmed requirements. Avoid inventing technologies, staffing, dates, budgets, or access.

Group work into independently verifiable outcomes. For each meaningful work item, specify its deliverable, inputs or prerequisites, acceptance check, and blocking dependencies. Scale detail to the assignment; a small change does not need an epic hierarchy.

Identify the critical path and distinguish genuine blockers from work that can proceed independently. Include migration, security, operations, and rollback work only when the feature actually requires them. Make external approvals and unavailable access explicit dependencies rather than assumed completed steps.

Choose sequential work when later steps depend on shared contracts or state. Propose parallel work when outputs have clear interfaces and changes can be integrated safely. Do not spawn agents merely because this skill describes decomposition. Delegate only when authorized by the user or governing instructions, and when the environment supports it; define each worker's scope, shared-file boundaries, expected evidence, and integration owner.

For delegated work, track dependencies and unresolved conflicts, verify the combined outcome, and avoid presenting independent worker success as proof that integration works. Keep coordination proportional to the task.

Deliver a practical plan with scope, work items, dependency order, acceptance checks, and open decisions. Respect the user's requested artifact or project template. Planning alone does not authorize implementation, publication, or external messages. If implementation is requested too, use the plan to continue within that scope.
