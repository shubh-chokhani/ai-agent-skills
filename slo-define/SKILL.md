---
name: slo-define
description: Define user-centered service level indicators, objectives, error budgets, and alerting from actual telemetry. Use for reliability objective design or repair, with optional monitoring artifacts.
---

# Define Service Level Objectives

Start with a user journey and a measurable successful outcome. Establish the eligible population, good-event definition, exclusions, objective, evaluation window, and owner. Use historical data and product needs to propose a target; do not derive it solely from service criticality labels.

Prefer event-based indicators: successful requests divided by eligible requests, or requests completed within a latency threshold divided by eligible requests. Decide explicitly how client errors, cancellations, retries, maintenance, and missing telemetry count. A percentile latency chart can aid diagnosis but is not by itself an event-based latency error budget.

Read [measurement.md](references/measurement.md) when producing queries, budgets, or alert rules. Inspect actual metric names, labels, units, histogram types, and aggregation boundaries. Never assume an instrumentation library emits a particular metric name. No-data and zero-traffic behavior must be explicit.

Keep target and threshold distinct: for example, 99% of eligible requests below 300 ms over 30 days. A traffic floor measures demand or capacity only in an agreed context; low demand alone is not proof of unreliability.

Generate rules or dashboards only when requested. Match the deployed tool and version, identify its data source, and validate syntax and representative results where access permits. Mark unverified queries as drafts. Deploying rules or sending pages is a separate authorized action.

Deliver the journey, SLI definition, target/window, data source, budget, alert rationale, owner, and caveats. Explain how the team will respond to budget depletion without inventing organizational release policy.
