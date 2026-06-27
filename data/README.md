# Data Directory — README

## `launch-metrics-benchmarks.csv`

Structured benchmark data for B2B product GTM launches. Extracted from nine field-tested articles covering enterprise SaaS and AI product commercialization. Use this to calibrate your pre-launch success criteria, build an executive scorecard, or pressure-test your current GTM assumptions.

---

## Column Definitions

| Column | Description |
|--------|-------------|
| `metric_category` | High-level grouping: Activation, Retention, Bug Quality, Ring Deployment, Trial Design, Pricing, GTM Lead Time, AI GTM, Positioning, Support, Scorecard |
| `metric_name` | The specific measurable metric |
| `healthy_target` | The benchmark range or threshold indicating a healthy product launch — derived from source articles |
| `failure_signal` | The condition that indicates the launch is failing and requires immediate intervention |
| `measurement_window` | When to measure this metric relative to GA day |
| `applies_to` | Whether the benchmark applies to standard SaaS, AI Products, a specific launch tier, or all |
| `source_article` | The article slug(s) from productleadersdayindia.org that contain the original data or case study |
| `notes` | Context, caveats, and field observations from the source articles |

---

## Important Caveats

1. **Baselines are context-dependent.** The Day-1 activation rate target of ≥30% is a general benchmark for B2B SaaS. Your actual target should be set from your own beta cohort data, not this CSV alone. If your historical activation rate for similar features is 15%, targeting 30% requires a specific explanation in your GTM canvas.

2. **Failure signals are immediate escalation triggers, not definitive failures.** A <10% activation rate on Day-1 does not mean the launch is over; it means you initiate product intervention immediately rather than celebrating top-of-funnel traffic.

3. **AI product benchmarks are early-stage.** The AI GTM benchmarks (task completion rates, consumption cap guidelines) reflect current best practices as of June 2026. This market is evolving rapidly — treat these as directional rather than fixed.

4. **The billing error rate (>1%) is a hard gate.** This is not a benchmark to optimize toward; it is a binary blocker. Any error rate above 1% on production upgrade transactions must be resolved before ring advancement.

---

## Source Articles

All benchmarks traceable to:

| Slug | Full URL |
|------|----------|
| `launch-metrics-success-criteria` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/launch-metrics-success-criteria.html |
| `beta-to-ga-rollout-plan` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/beta-to-ga-rollout-plan.html |
| `product-launch-checklist` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/product-launch-checklist.html |
| `pricing-packaging-at-launch` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/pricing-packaging-at-launch.html |
| `gtm-for-ai-products` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/gtm-for-ai-products.html |
| `product-positioning-framework` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/product-positioning-framework.html |
| `go-to-market-strategy-framework` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/go-to-market-strategy-framework.html |
| `product-gtm-launch-strategy` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/product-gtm-launch-strategy.html |
| `product-launch-templates` | https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/product-launch-templates.html |

---

## Suggested Uses

- **Pre-launch baseline setting:** Filter `measurement_window` for entries mentioning "T-14 days" or "pre-launch" to identify what needs to be defined before beta exits.
- **Executive scorecard:** Filter `metric_category = Scorecard` and `metric_category = Activation` for the metrics that belong in a board-facing dashboard.
- **Go/no-go review:** Filter for rows where `healthy_target` contains "0 (zero)" or "<1%" — these are your hard blockers, not optimization targets.
- **AI product launches:** Filter `applies_to = AI Products` for the AI-specific benchmarks.

---

*Repo: [github.com/rishabhsaini282/b2b-product-gtm-launch-playbook](https://github.com/rishabhsaini282/b2b-product-gtm-launch-playbook) | Updated: June 2026*
