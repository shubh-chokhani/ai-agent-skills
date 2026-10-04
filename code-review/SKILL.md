---
name: code-review
description: Review a pull request, merge request, patch, or local diff for actionable defects and test gaps. Use for code review requests across languages and hosting providers.
---

# Code Review

Review the actual change against its intended behavior and repository contracts.

## Gather evidence

Fetch the description, base/head revisions, and complete diff with available tools. For local changes, establish the intended comparison. Inspect surrounding code, callers, tests, and relevant repository instructions. If the diff is truncated or inaccessible, obtain it or explicitly narrow the review; never infer unseen changes.

Detect frameworks and versions from the repository. Read [stack-checks.md](references/stack-checks.md) only for Java/Spring or JavaScript/TypeScript/React changes. For other stacks, use their actual contracts and authoritative documentation when necessary. Do not assume a database, broker, service mesh, or organizational naming standard.

## Evaluate the changed behavior

Prioritize correctness, authorization and input handling, data integrity, resource ownership, dependency failures, compatibility, and realistic performance regressions. Inspect retries for idempotency and boundedness. Consider database and message schema changes in deployment order. Assess tests by the behavior they establish, not raw counts or a universal coverage target.

Treat style, naming, instrumentation, circuit breakers, and feature flags as contextual choices. Raise them only when a concrete contract, operational need, or repository standard supports the finding. Distinguish introduced defects from pre-existing issues.

## Report

Lead with findings ordered by impact. Each finding needs a short title, precise changed-file location, triggering scenario, consequence, and evidence. Offer a small fix when clear. Separate uncertain questions from confirmed defects; avoid speculative warnings and padding.

Summarize intent, relevant test gaps, and review limitations. If no actionable defect was found, say so without implying exhaustive proof of correctness. A readiness recommendation is advisory unless an actual platform review was submitted.

Posting comments, approving, requesting changes, or merging requires the user's authorization for that action. An ordinary request to review authorizes inspection and a review in chat.
