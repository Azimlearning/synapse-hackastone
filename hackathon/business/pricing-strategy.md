<!-- /founder:pricing-strategy · 2026-10-29 · input: (none; the product, payers and goal were stated earlier in the session) -->

# Synapse pricing strategy

Assumption: the founder has no pricing idea of their own. This builds on `refdocs/business/2026-10-29-pricing-strategy.pdf`, with Teacher folded into Free and a launch price added.
Assumption: charging needs accounts, which ADR D-11 lists as a non-goal for v1. Nothing here goes live until the founder reopens D-11.

## 1. Pricing model analysis

| Model | Fit | Pros | Cons |
|---|---|---|---|
| Flat subscription | 3 | Parents understand it. Revenue is predictable | Unlimited labs: one heavy user can cost more than they pay, at the stress cost of RM0.35 a lab |
| Usage-based | 2 | Matches cost exactly | Teenagers can't budget per lab. Every question feels like spending |
| Per-seat | 3 | Right for schools, which buy per student | Wrong for a single student |
| Freemium | 5 | A library lab costs RM0 to serve, so free can be generous. Fits reach first | Needs a paid tier and schools to carry the free users |
| Credits | 3 | Caps the cost per user | Confusing as the only model. Works better as an allowance inside a plan |
| One-time purchase | 2 | Easy for a parent | Model cost keeps running after the sale |

**Recommendation: freemium, plus a flat subscription with a monthly allowance of new labs, plus a per-student school licence.** Free is cheap because repeat questions hit the library, the allowance caps the one cost that grows with use, and schools buy yearly and per student.

## 2. Tier design

### Free: RM0
- Every library lab, unlimited (30 verified labs in English and 30 in Malay today)
- 3 new labs a month
- Hints, the predict card, the concept check and the exam mirror on every lab
- Offline single-file export and share links
- Full citations and trust labels, never behind a paywall
- Teachers get Present mode and offline chapter packs, plus 10 new labs a month

**Upgrade trigger:** the student asks a 4th question that the library can't answer, in a month before an exam.

### Plus: RM12.90 a month, or RM109 a year (30% off)
- Everything in Free
- 30 new labs a month (about one a day)
- Labs and progress saved across devices (not built: needs accounts)
- Lab report export as a PDF (not built)
- Served first when demand is high during the SPM months

**Upgrade trigger:** a teacher wants a whole class on Plus, or a parent pays for more than one child.

### School: RM15 per student a year, minimum RM1,500 (sales-led, invoiced)
- Plus for every enrolled student
- A pool of 20 new labs per student a year, shared by the school
- Class codes (not built)
- A shelf of labs chosen by the teachers (not built)
- A termly usage report for the science panel (not built)
- Annual only, because school and PIBG budgets are yearly

**Upgrade trigger:** none above this. The next step is renewal and a district or state deal.

## 3. Competitive pricing context (checked 2026-10-29)

| Competitor | Price | What's included | Where Synapse sits |
|---|---|---|---|
| [Pandai](https://pandai.org/en/premium-users) | Premium Lite RM30/mo, Premium RM96/mo. Its [FAQ](https://pandai.org/en/faq) gives conflicting figures | KSSM practice questions; Premium adds live tuition | **Below**, because Synapse covers three sciences, not every subject |
| [GoLearn SPM online tuition](https://www.golearn.com.my/tuition/spm-online-tuition) | RM49 to RM89 per subject a month | Live online classes, 4 a month | **Far below**, because Synapse goes with a teacher rather than replacing one. The tuition fee is the price parents compare against |
| ChatGPT Go | RM24/mo ([Lowyat, 2026](https://www.lowyat.net/2026/384132/openai-knocks-down-chatgpt-go-price-to-rm24-month/); launched at RM38.99, [SoyaCincau](https://soyacincau.com/2025/10/09/chatgpt-go-plan-priced-at-rm38-99-month/)) | A general chatbot with no checking against KSSM | **Below**, because a student who already pays for a chatbot needs Plus to be an easy extra |
| [Labster](https://www.labster.com/es/precios) | Custom quotes. Older figures: [$9 per student a month (2017)](https://www.edsurge.com/news/2017-09-09-stem-startup-labster-nabs-10m-funding-to-expand-3d-lab-simulations), [about $50 per student a year (2019)](https://www.edsurge.com/news/2019-04-25-labster-raises-21-million-to-bring-more-digital-lab-simulations-to-classrooms) | Virtual science labs for institutions | **Far below** (RM15 is about $3.60), because government schools have little budget. Private and international schools could take RM30, so test that price there |
| DELIMa | Free to students ([Tech Wire Asia](https://techwireasia.com/?p=205746)) | The Ministry platform: Google, Microsoft and Apple tools | **Inside it, not against it.** A share link should open from Google Classroom |

## 4. Unit economics

**Cost per new lab:** a measured $0.057 per delivered lab (paid run, 2026-10-28, 14 questions) × RM4.20 = RM0.24. Plan with RM0.25, and use RM0.35 for stress. Estimate: the exchange rate of RM4.20.

**Fixed costs a month:**
- **Render (API):** Standard plan $25 ([Render article](https://render.com/articles/render-vs-railway); verify on [render.com/pricing](https://render.com/pricing)) plus a 1 GB disk at $0.25, so $25.25.
- **Vercel (web):** Estimate: $20 for a paid plan, not checked this session.
- **Support:** the founder's time, RM0 cash.
- **Total:** about $45, or RM190 (estimate).

**Payment fee:** Estimate: RM1 a charge.

| Tier | Revenue a month | Cost a month (expected: half the cap) | Gross margin | At full cap |
|---|---|---|---|---|
| Free | RM0 | 3 × 33% × 0.25 = RM0.25 | n/a | 3 × 0.25 = RM0.75 |
| Plus monthly | RM12.90 | 15 × 0.25 + 1 = RM4.75 | **63%** | 30 × 0.25 + 1 = 8.50, so 34% |
| Plus annual | 109 / 12 = RM9.08 | 3.75 + 1.5 / 12 = RM3.88 | **57%** | 7.63, so 16% |
| School (per student) | 15 / 12 = RM1.25 | 10 × 0.25 / 12 = RM0.21 | **83%** | 0.42, so 67% |

**Break even (fixed RM190 a month plus RM0.25 per free user):**
- **Plus only:** (190 + 0.25 × free users) / 8.15. That is 24 subscribers with no free users, or 54 for every 1,000 free users. 54 per 1,000 is 5.4%, which is too high to count on.
- **School only:** RM1.04 margin per student a month, so 183 students, or 2 schools at the minimum.
- **Both:** two schools pay the fixed cost, and Plus only has to pay for the free users: 31 per 1,000, or 3.1%.

**Target blended ARPU:** Estimate: RM3.80 per paying student a month. This assumes 70% are school students (RM1.25), 25% on Plus annual (RM9.08) and 5% on Plus monthly (RM12.90): 0.88 + 2.27 + 0.65.

## 5. Pricing psychology

- **Anchoring:** Plus monthly is the anchor, shown next to "one month of tuition in one subject: RM49". RM12.90 for all three sciences then reads as small, and the RM49 figure is a price the parent already pays.
- **Decoy:** Plus monthly is also the decoy for Plus annual: 12 × RM12.90 = RM154.80 against RM109. A fourth tier as a decoy would confuse 16-year-olds, so the plan doesn't use one.
- **Annual framing:** call it the "Form 5 year pass: RM109, about RM9 a month, 3 months free". It maps to the SPM year the student is already counting down, and "3 months free" (RM45.80 saved) lands harder than "30% off".

## 6. Launch pricing and scale pricing

**Launch (first 90 days of Plus):** RM9.90 a month, or RM79 a year. School pilots are free for one term, in exchange for interviews and usage data. **Because** the library covers only 16 of 53 topics today, the launch has to measure conversion rather than maximise it, and RM9.90 still clears a 52% expected margin ((9.90 minus 4.75) / 9.90).

**Grandfathering:** founding Plus users keep RM9.90 or RM79 for as long as they stay subscribed without a break. Pilot schools pay RM10 per student in their first paid year. **Because** these users test the product while it's least finished, and a price kept for life costs about RM3 a month per user.

**Price increases.** Raise to the scale price when any one of these happens:
1. The library covers 40 of 53 topics (75%), **because** Plus then buys more.
2. Free to Plus conversion stays at 5% or more for 2 months in a row at the current price.
3. The Van Westendorp survey (40 students and 20 parents) puts the optimal price above the current price.
4. The measured cost per new lab goes above RM0.35. This is a cost trigger, and it raises only the allowance price, never Free.
5. 80% or more of schools renew.

Give 60 days' notice. Raise prices for new users first and existing users one billing cycle later, and never cut the free library.

**Correction to the earlier PDF:** its sponsored seat (RM79 a year) loses RM12.50 a seat at full use. Price sponsored seats at the Plus annual price of RM109, or cap them at 20 new labs a month.
