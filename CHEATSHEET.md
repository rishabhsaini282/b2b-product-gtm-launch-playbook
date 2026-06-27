# B2B Product GTM Launch — One-Page Cheatsheet

> Print this. Keep it open during GTM planning sessions and go/no-go reviews.

---

## THE 7-STEP GTM FRAMEWORK

```
1. ICP Definition          → Who buys? Separate economic buyer from end-user.
2. Competitive Positioning  → What's your wedge? Draft a value prop tied to ROI, not features.
3. GTM Motion              → PLG or SLG. Commit. Do not launch both simultaneously.
4. Pricing & Monetization  → Tiering structure and value metric. Set before engineering starts.
5. Distribution            → How does the ICP discover the product? Outbound, partner, community?
6. Operational Readiness   → Go/no-go checklist enforced. Every commercial asset verified.
7. Launch Metrics          → Leading indicators defined before beta. North star metric declared.
```

**Rule:** Steps 1–3 must be complete before the PRD is written. Steps 4–7 must be complete before beta opens.

---

## THE 5-STEP PRE-BUILD POSITIONING SEQUENCE

```
Step 1: Competitive Alternatives
        → What does the ICP use TODAY if your product vanishes?
        → Real answer: usually spreadsheets or a legacy internal tool, not a named competitor.

Step 2: Unique Attributes
        → Objective capabilities your product has that the alternatives do not.
        → "Easy to use" is NOT a unique attribute. Quantify task time reduction.

Step 3: Differentiated Value
        → Translate attributes into business outcomes.
        → Capability:  "Asynchronous data pipeline"
        → Value:       "Financial controller closes books 40% faster"

Step 4: Best-Fit ICP Segment
        → Narrow to the niche that cares MOST about your specific differentiated value.
        → Bad:  "Mid-market businesses"
        → Good: "Mid-market healthcare providers under HIPAA/DPDP"

Step 5: Market Category
        → Choose the category that highlights your strengths, not the most crowded one.
        → Repositioning example: "Business Intelligence Platform" → "Incident Resolution Analytics"
        →   Result: TTFV dropped from 40 days to 4 days; pipeline velocity doubled.
```

---

## GOOD-BETTER-BEST PRICING RULES

| Tier   | Role            | Revenue Target | What It Gates                          |
|--------|-----------------|----------------|----------------------------------------|
| Good   | Acquisition     | ~15%           | Advanced integrations, API rate limits |
| Better | Core ICP fit    | **~70%**       | Full feature set for primary workflow  |
| Best   | Price anchor    | ~15%           | Compliance, SSO, dedicated SLA         |

**Hard rules:**
- Anchor to business value delivered, not competitor average pricing
- AI products: NEVER launch "unlimited" generation — cap at launch, expand later
- Trial length: **14 days maximum** (30-day trials kill urgency)
- Intro pricing expiration: must be absolute — state the exact quarter-end date
- Beta-to-paid transition: offer a 12-month locked founder's rate, not lifetime free access

---

## BETA EXIT CRITERIA (ALL MUST BE MET)

```
Technical:
  ✓ Zero P0 (critical) open bugs
  ✓ Zero P1 (high) open bugs
  ✓ Load test passed at 2x expected GA traffic

Commercial:
  ✓ Target % of beta users reached core activation event
  ✓ Day-14 retention threshold (defined pre-launch) achieved

Operational:
  ✓ All support documentation published
  ✓ Sales battlecards finalized and distributed to AEs
  ✓ Billing webhooks verified in PRODUCTION (not sandbox)
```

**Warning:** Removing any criterion to hit a calendar deadline carries documented risk. One team that dropped the "Zero P2 Bugs" threshold experienced a 40% spike in support tickets and degraded day-30 retention.

---

## RING DEPLOYMENT THRESHOLDS

```
Ring 0  → Internal employees only     | Smoke test
Ring 1  → 5% external traffic         | Monitor: API latency, DB load, error rates
Ring 2  → 25% exposure                | Monitor: Broader load behavior
Ring 3  → 100% GA                     | Full SLA monitoring
```

**Feature flag rule:** If error rates exceed threshold at any ring, revert instantly. Advance only when metrics are clean for a predetermined observation window.

---

## LAUNCH METRICS: LEADING INDICATORS

| Metric                    | Target          | Failure Signal      | When to Measure    |
|---------------------------|-----------------|---------------------|--------------------|
| Day-1 Activation Rate     | ≥ 30%           | < 10%               | First 24–48 hrs    |
| Time-to-First-Value (TTFV)| < 24 hours      | > 72 hours          | Days 1–3           |
| Day-14 Retention          | Pre-set threshold| Flatlines after D3 | Days 14–30         |
| Day-30 Retention          | Above beta cohort| Negative slope      | Days 30–60         |
| Day-90 Retention          | Confirms PMF    | Continued drop      | Days 60–90         |

**Drop these entirely from your executive scorecard:**
- Total registered users (hides churn behind top-of-funnel)
- Website traffic / page views (marketing noise)
- Press mentions (vanity)
- Generic sign-ups without activation event completion

**Replace with:**
- Accounts reaching TTFV within 48 hours
- Feature adoption depth in primary ICP cohort
- Sales pipeline velocity from PQL conversion

---

## LAUNCH TIER DECISION

```
T1 → Net-new product / major architectural shift / new market entry
     → Full 32-step runbook | Executive sponsorship | Max marketing budget

T2 → Significant feature addition driving upsell
     → Strong sales enablement | Limited external PR

T3 → Minor iterative enhancement or bug fix
     → Changelog update | Internal support brief only
```

---

## GA DAY 4-PHASE SEQUENCE

```
Phase 1: Pre-Launch Readiness (T-60 days)
  Lock GTM canvas, GA date, pricing, launch metrics, rollout plan, RACI

Phase 2: Go/No-Go Criteria (T-14 days)
  Zero P0/P1 bugs | Beta exit criteria met | Feature flags tested
  Billing verified in PRODUCTION | Load test complete | Exec readiness review

Phase 3: Sales Enablement & Handoffs (T-7 days)
  Pitch decks delivered | Battlecards distributed | Support docs published
  AEs trained on objection handling | Website copy locked | Email sequences pre-scheduled

Phase 4: GA Day Runbook
  War room open → Feature flag to 100% → Monitor dashboards →
  Lift press embargo → Monitor support queue (4-hr window) →
  Validate activation telemetry → T+7 blameless retrospective
```

---

## AI GTM: THE TRUST SIGNALS THAT MOVE ENTERPRISE DEALS

```
What buyers need before signing:
  □ Hallucination rate disclosed (publishing 92% beats claiming 100%)
  □ Human-in-the-loop fallback documented
  □ Data residency / sovereignty architecture confirmed
  □ GDPR + EU AI Act compliance status stated
  □ Task completion rate vs. ground-truth dataset published
  □ Tool-use correctness scores available

Pricing model for AI:
  Avoid: Flat per-seat (cost scales with tokens; revenue stays flat)
  Prefer: Outcome-based (pay-per-resolution) or hybrid (seat + usage cap)
  Critical: Communicate consumption multipliers BEFORE contract signature
            → Surprise true-ups at quarter-end destroy trust and trigger churn
```

---

## QUICK DIAGNOSTIC: IS YOUR LAUNCH READY?

Rate each on 0/1:

```
[ ] ICP defined with firmographic + technographic criteria
[ ] Competitive alternatives documented (not just named rivals)
[ ] Differentiated value stated in business outcome terms
[ ] GTM motion committed (PLG or SLG — not "both")
[ ] Pricing set based on value delivered, not competitor average
[ ] Beta exit criteria documented and ALL met
[ ] Day-1 activation rate target defined (not inferred after launch)
[ ] TTFV target defined and monitored in analytics
[ ] All billing verified in production environment
[ ] Sales battlecards distributed before feature flag flips to 100%
```

**Score 9–10:** Proceed. | **Score 6–8:** Address gaps before ring advancement. | **Score < 6:** Do not flip to GA.

---

*Sources: productleadersdayindia.org/blogs/product-gtm-launch-strategy/ | Repo: github.com/rishabhsaini282/b2b-product-gtm-launch-playbook*
