# 32-Step Product Launch Checklist

**Operational runbook for Tier 1 and critical Tier 2 releases.**
Copy this into Notion, Linear, Jira, or a shared doc. Assign an owner to every step before Phase 1 begins. Steps in Phase 2 include an explicit **Hard Blocker** — the measurable threshold that halts GA advancement if unmet.

---

## Pre-Requisite: Determine Launch Tier

Before activating this checklist, classify the release:

| Tier | Criteria | Checklist Activation |
|------|----------|----------------------|
| **T1** | Net-new product, major architectural shift, new market category entry | All 32 steps, full executive sponsorship |
| **T2** | Significant feature driving upsell or cross-sell | Steps 1–8 condensed; Steps 9–32 in full |
| **T3** | Minor iterative enhancement, bug fix, UX polish | Changelog update + internal brief only — skip this checklist |

**Assigned Launch Tier:** `[ T1 / T2 / T3 ]`
**GA Target Date:** `________________`
**Launch Owner (PM):** `________________`
**Executive Sponsor:** `________________`

---

## Phase 1: Pre-Launch Readiness — T-Minus 60 Days

*Lock the foundational commercial architecture before engineering commits the final build.*

- [ ] **Step 1 — GTM Canvas**
  Lock the internal GTM canvas covering: Ideal Customer Profile (with firmographic + technographic criteria), value proposition, competitive alternatives (including status quo workarounds), and distribution motion.
  **Owner:** Product Marketing
  **Done when:** Canvas is signed off by Product, Sales, and Marketing leads — not still in draft.

- [ ] **Step 2 — GA Date & Executive Sign-Off**
  Finalize the target GA date and secure cross-departmental executive sign-off. The date is a commitment, not an aspiration.
  **Owner:** Program Manager / CPO
  **Done when:** Date is in the company OKR system and calendar-blocked for all cross-functional leads.

- [ ] **Step 3 — Pricing & Packaging Model**
  Finalize the tiering structure (good-better-best or chosen model), trial length (target: 14 days), AI compute guardrails if applicable, and beta-to-paid transition mechanics.
  **Owner:** Product + Revenue Ops
  **Done when:** Pricing page copy is approved, Stripe/Chargebee tier configuration is drafted, and margin model is reviewed by Finance.

- [ ] **Step 4 — Leading Launch Metrics Defined**
  Define primary leading indicators: Day-1 activation rate target, TTFV threshold, Day-14 retention threshold. Document the activation event (specific high-value action, not just login).
  **Owner:** Product Manager
  **Done when:** Metrics are documented in the GTM canvas with numeric targets — not "TBD" or "to be measured post-launch."

- [ ] **Step 5 — Beta-to-GA Rollout Plan Drafted**
  Draft the ring deployment sequence (Ring 0 → Ring 1 at 5% → Ring 2 at 25% → Ring 3 at 100%), feature flag architecture, and rollback procedure.
  **Owner:** Engineering Lead + PM
  **Done when:** Feature flags exist in staging and rollback has been tested at least once.

- [ ] **Step 6 — Security, Compliance & Legal Reviews Initiated**
  Open security review tickets. Initiate legal review of pricing terms, data processing agreements, and any AI-specific compliance requirements (GDPR, EU AI Act, SOC 2 scope).
  **Owner:** Security / Legal
  **Done when:** Review tickets are assigned with target completion dates before Phase 2.

- [ ] **Step 7 — RACI Matrix Published**
  Establish the RACI matrix for all downstream launch tasks. Every Phase 2–4 step must have a single Responsible owner and an Accountable executive.
  **Owner:** Program Manager
  **Done when:** RACI is shared in the team's project management tool with no blank Responsible rows.

- [ ] **Step 8 — Core Positioning Documents Drafted**
  Begin drafting: positioning document (competitive alternatives, unique attributes, differentiated value), one-pager for AEs, and initial press release draft.
  **Owner:** Product Marketing
  **Done when:** Positioning doc reviewed by at least two AEs and two customer success managers for accuracy.

---

## Phase 2: Go/No-Go Launch Criteria — T-Minus 14 Days

*These are absolute technical and commercial thresholds. If any single step fails its Hard Blocker condition, the launch is delayed. No exceptions.*

- [ ] **Step 9 — Zero P0/P1 Bugs in Launch Candidate**
  Confirm zero P0 (critical) and P1 (high) bugs remain open in the build tagged as the GA release candidate.
  **Owner:** Engineering Lead
  **Hard Blocker:** Any single open P0 or P1 bug halts advancement to GA. Do not negotiate this criterion under deadline pressure.

- [ ] **Step 10 — Beta Exit Criteria Achieved**
  Verify that all documented beta exit criteria are met: technical thresholds, commercial activation targets, and operational readiness markers.
  **Owner:** Product Manager
  **Hard Blocker:** If the target activation rate in beta cohorts is not reached, GA is delayed until the cohort data meets the threshold. The date does not override the data.

- [ ] **Step 11 — Feature Flags Tested in Staging**
  Verify all feature flags function correctly in the staging environment. Test both the enable and rollback paths.
  **Owner:** Engineering
  **Hard Blocker:** If rollback of any GA feature flag produces errors in staging, the flag must be fixed before Ring 1 exposure.

- [ ] **Step 12 — Load Testing Passed**
  Complete load testing at a minimum of 2x expected GA day traffic. Confirm infrastructure auto-scaling behavior.
  **Owner:** SRE / DevOps
  **Hard Blocker:** If p95 API latency exceeds the defined SLA threshold under 2x load, infrastructure must be scaled before ring advancement.

- [ ] **Step 13 — Billing Verified in PRODUCTION (Not Sandbox)**
  Test all billing configurations (Stripe, Chargebee, or equivalent) using real payment flows in production. Verify webhook delivery, upgrade flows, downgrade flows, and trial expiration behavior.
  **Owner:** Engineering + Revenue Ops
  **Hard Blocker:** If production billing logs show more than 1% error rate on simulated upgrade transactions, GA is halted. Do not rely solely on sandbox test results — they do not replicate production webhook behavior.
  > **Why this step is starred:** In one major Q2 launch, sandbox billing was clean but production webhook keys were misconfigured. GA day arrived, users upgraded, and the payment gateway silently rejected every transaction for 8 hours.

- [ ] **Step 14 — Security / SOC 2 Audit Complete**
  Confirm mandatory security and compliance audit checks for the new module are completed and signed off.
  **Owner:** Security
  **Hard Blocker:** Outstanding critical or high security findings block GA advancement.

- [ ] **Step 15 — Third-Party API Dependency Verification**
  Verify all external API dependencies are stable and production-ready. Review rate limits, SLA agreements, and fallback behavior.
  **Owner:** Engineering
  **Hard Blocker:** Any dependency with an upcoming planned maintenance window overlapping the GA rollout must be rescheduled or mitigated.

- [ ] **Step 16 — Executive Launch Readiness Review**
  Conduct the formal go/no-go meeting with executive leadership. Present Phase 2 results. Obtain official authorization or documented delay decision.
  **Owner:** CPO / VP Product
  **Hard Blocker:** If Sales Enablement assets (battlecards, pitch decks) are not finalized, or if Support has not completed product training, the launch is delayed. Shipping an unsupported product is worse than shipping a late one.

---

## Phase 3: Sales Enablement & Handoffs — T-Minus 7 Days

*Engineering readiness means nothing if the revenue team cannot articulate the product's value. Every step in this phase must be completed before the GA feature flag flips.*

- [ ] **Step 17 — Pitch Decks Delivered to AEs**
  Distribute finalized internal pitch decks to Account Executives. Include the product demo script with known edge case limitations documented (not just the happy path).
  **Owner:** Product Marketing
  **Done when:** AEs have confirmed receipt and can demo the product unassisted.

- [ ] **Step 18 — Competitive Battlecards Distributed**
  Distribute competitive battlecards covering the new differentiated features. Each card must include: the primary competitive alternative (including the status quo), your unique attributes, objection responses, and deal-win proof points.
  **Owner:** Product Marketing
  **Done when:** Battlecards are in the sales enablement platform, not just emailed.

- [ ] **Step 19 — Objection Handling Training Sessions Conducted**
  Run live objection-handling sessions with SDRs and AEs. Cover the top five objections identified during beta customer conversations.
  **Owner:** Sales Enablement Lead
  **Done when:** Session attendance tracked; AEs can respond to top objections without referencing notes.

- [ ] **Step 20 — Help Center Documentation Published**
  Publish all external help center documentation, API references, and integration guides. Documentation must cover the launched feature set — not planned future functionality.
  **Owner:** Technical Writer / PM
  **Done when:** All help articles are live, indexed, and internally linked from the product UI where relevant.

- [ ] **Step 21 — Support Triage Workflows Finalized**
  Finalize customer support triage workflows and escalation paths for the new feature. Support agents must know which bug reports go directly to engineering, which go to the PM, and how to reproduce the most common failure modes.
  **Owner:** Customer Support Lead
  **Done when:** Triage runbook is published in the support team's knowledge base.

- [ ] **Step 22 — Customer Success Demo Access Provisioned**
  Provision live product access for Customer Success Managers so they can run live demos with customers during onboarding. Test accounts must reflect GA feature configuration — not beta configuration.
  **Owner:** CS Ops / Engineering
  **Done when:** Each CSM has a verified live demo environment.

- [ ] **Step 23 — Public-Facing Copy Locked**
  Finalize and lock all public-facing website copy, landing pages, pricing pages, and press release drafts. No copy changes within 48 hours of GA.
  **Owner:** Product Marketing + Legal
  **Done when:** Legal has reviewed pricing claims; PM has verified no feature capabilities are overstated.

- [ ] **Step 24 — Marketing Sequences Pre-Scheduled**
  Pre-schedule automated marketing email sequences (trial start, activation nudges, trial expiration) and in-app tooltips. Set embargo lift timing.
  **Owner:** Marketing Ops
  **Done when:** Email sequences are in the send queue with correct segmentation; in-app tooltips verified in staging.

---

## Phase 4: GA Day Runbook & Post-Launch Execution

*GA day is a choreographed sequence, not a switch flip. Run steps in order.*

- [ ] **Step 25 — Launch War Room Open**
  Open a dedicated Slack channel or Teams channel as the launch war room. Pin the runbook. Assign on-call rotation for the first 24 hours.
  **Owner:** Program Manager
  **Time:** At least 2 hours before feature flag advancement.

- [ ] **Step 26 — Staged Rollout Executed**
  Advance the feature flag following the ring deployment plan: internal (Ring 0) → 5% (Ring 1) → 25% (Ring 2) → 100% (Ring 3). Wait for monitoring confirmation between rings.
  **Owner:** Engineering Lead
  **Time:** Stagger ring advancements with at least 30–60 minutes of monitoring between each.

- [ ] **Step 27 — Engineering Dashboards Monitored**
  Monitor API latency, error rate, database load, and infrastructure auto-scaling behavior after each ring advancement.
  **Owner:** SRE
  **Escalation trigger:** If p95 latency or error rate exceeds threshold, revert the feature flag and open incident process.

- [ ] **Step 28 — Press Embargo Lifted**
  Authorize marketing to publish external assets: press release, blog post, social posts, email campaigns.
  **Owner:** Marketing Lead
  **Timing:** Lift only after Ring 1 monitoring confirms stability — not simultaneously with the flag flip.

- [ ] **Step 29 — Support Queue Monitored (First 4 Hours)**
  Monitor the initial support queue for unexpected user friction patterns. Tag incoming tickets by feature area for rapid triage.
  **Owner:** Support Lead
  **Escalation trigger:** If ticket volume exceeds 3x the normal hourly baseline, escalate to PM and Engineering.

- [ ] **Step 30 — Activation Telemetry Validated**
  Verify that Day-1 product activation telemetry is accurately flowing into your analytics tool (Mixpanel, Amplitude, PostHog, etc.). Confirm the activation event fires correctly for real user actions — not just test accounts.
  **Owner:** Data / Analytics
  **Done when:** At least 10 real user activation events confirmed in the analytics dashboard.

- [ ] **Step 31 — Bug Reporting Transitioned**
  Transition bug reporting from the launch war room to the standard sustained engineering backlog. Close the war room escalation channel after 24–48 hours of stability.
  **Owner:** Engineering Lead + PM
  **Done when:** Backlog is triaged; no P0 or P1 issues outstanding.

- [ ] **Step 32 — Post-Launch Retrospective Scheduled**
  Schedule and conduct a blameless post-launch retrospective at T-Plus 7 days. Review: what the launch metrics showed vs. the pre-defined targets, the three things that went well, and the three highest-priority fixes for the next release cycle.
  **Owner:** Product Manager
  **Done when:** Retrospective notes published to the team; action items assigned with owners and due dates.

---

## Launch Metrics Tracking Template

Use this table in your retrospective and exec scorecard:

| Metric | Pre-Launch Target | Actual (Day 1) | Actual (Day 14) | Actual (Day 30) | Status |
|--------|-------------------|----------------|-----------------|-----------------|--------|
| Day-1 Activation Rate | ____% | | | | |
| TTFV (hours) | ≤ ____hrs | | | | |
| Day-14 Retention | ____% | | | | |
| Support Ticket Volume | ≤ ____/hr | | | | |
| AE Demo Completion | ≥ ____% | | | | |
| Billing Error Rate | < 1% | | | | |

---

## Common Failure Modes (Add These to Your Retrospective Template)

| Failure | Root Cause | Prevention |
|---------|-----------|------------|
| Payment gateway silent failures on GA day | Billing tested only in sandbox | Step 13: Always verify in production |
| AEs unable to demo on launch day | Enablement assets delivered too late | Step 17 minimum 7 days before GA |
| 40% support ticket spike post-launch | Beta exit criteria softened for deadline | Never remove an exit criterion |
| Power users destroy gross margins in 72 hours | AI/compute features launched with "unlimited" access | Always cap at launch; expand later |
| Repositioning required 9+ months after launch | Positioning written after build, not before | Position during discovery, not launch week |

---

*Source: [productleadersdayindia.org/blogs/product-gtm-launch-strategy/](https://productleadersdayindia.org/blogs/product-gtm-launch-strategy/) — Repo: [github.com/rishabhsaini282/b2b-product-gtm-launch-playbook](https://github.com/rishabhsaini282/b2b-product-gtm-launch-playbook)*
