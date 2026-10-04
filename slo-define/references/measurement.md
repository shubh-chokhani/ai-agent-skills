# Measurement and error budgets

For an event-based objective S, use:

- SLI = good eligible events / all eligible events.
- Allowed bad-event fraction = 1 - S.
- Allowed bad-event count = eligible event count over the objective window multiplied by (1 - S).
- Burn rate = observed bad-event fraction / (1 - S).

Do not translate a request-based budget into downtime unless explicitly stating the traffic assumptions. A time-based availability SLO can use window duration multiplied by (1 - S). Require 0 < S < 1 for finite burn-rate calculations; a 100% objective has no positive error budget.

For a budget fraction f consumed during a window w within an objective window T, the corresponding burn-rate threshold is f * T / w, with consistent units. This estimates consumption under a sustained observed rate, not a guaranteed future trajectory.

## Prometheus query design

Discover the actual counters and labels. For a rolling event ratio, aggregate counter increases over the same window for numerator and denominator, handling counter resets through the counter function. For short-window alert signals, aggregate counter rates over matched windows. Apply rate/increase before aggregation so individual resets remain visible.

For classic latency histograms, use the cumulative bucket matching the threshold divided by the corresponding count, with identical grouping and eligibility. Verify the bucket exists and its unit. For a diagnostic percentile, aggregate bucket rates with the `le` label retained before histogram_quantile. Native histograms require their supported functions and deployed Prometheus version; do not reuse classic bucket syntax blindly.

Check numerator is a subset of denominator, labels align, exclusions are consistent, and low traffic/no data have explicit handling. Recording rules can make repeated queries cheaper, but aggregation must preserve necessary dimensions.

## Alert calibration

Select thresholds from the budget fraction, observation window, and response time. Consider paired long and short windows to confirm sustained consumption and timely recovery. Test alerts against historical incidents and quiet periods; choose paging versus ticketing according to actionability. A 1% bad-event fraction against a 99.9% target is 10x burn, not 60x.

Reference: [Google SRE workbook: Alerting on SLOs](https://sre.google/workbook/alerting-on-slos/).
