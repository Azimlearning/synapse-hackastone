# Grand final: things to consider, by judging criterion

For Team EduNova (project Synapse), hackAstone 2026 grand final, 29 October 2026, Vrije Universiteit Amsterdam.
Working notes for building the pitch deck, the demo video and the booth loop. Written 2026-10-28.

Sources: the competition site (`/spotlight/`, `/grand-final/`, `/finalist/`), the shortlist email, `grand-final-deliverables.md`, the A1 poster, the Codefest content (`Synapse/refdocs/SLIDES-CONTENT.md`) and the current Synapse v4 repo (`refdocs/STATUS.md`, `packages/kit/dist/0.1.0/manifest.json`, `data/plans/`).

---

## 0. Settle these first (they change the deck)

| # | Conflict or gap | What the sources say | Safe plan |
|---|---|---|---|
| 1 | **Presentation length** | The shortlist email and Dr. Cai's 20 Aug note say 10 min presentation plus 5 min Q&A. The site's Grand Final page says "max 8 min project presentation" and "2 mins QnA", and a demo "maximum of 10 minutes including Q&A" at the booth | Build the core story to fit **8 minutes**. Mark 2 to 3 slides as "only if we have 10". Ask the secretariat which is right. A news post dated 9 Oct announced a Tentative Program, which may settle it. We could not open it |
| 2 | **Name** | The organiser's file says the project title on every form is **EduNova**. The poster says "Synapse by Team EduNova" | Team is EduNova. Product is Synapse. Title slide reads "Synapse by Team EduNova" as on the poster |
| 3 | **Team list** | The poster lists 8 names: Por Jie Hao, Fakhrul Azim, Azrain Shawn, Khaidhir, Alif Fadhil, Adam Iman, Danish Iskandar, Nur Farah. The prelim report lists 7 | Use the poster's 8. The old video credits (Team Dang Wangi) belong to a different event and must not appear |
| 4 | **Theme fit** | The theme is "Agentic AI for Education". Synapse v4 is a pipeline of AI and deterministic steps with a trust gate | Say plainly which steps are agents (router, planner, wording judge, composer) and which are deterministic (checks, assembler, verifier, gate). Judges will ask why it counts as agentic. Answer: it plans, builds, and checks its own work before the student sees it |
| 5 | **Who the judges are** | A steering committee of education and AI researchers (VU, Windesheim, UCD, Turku, PH Zurich, Kyoto, NTU and others) plus NVIDIA | Lead with pedagogy and evidence. Keep the engineering to one diagram |
| 6 | **Competition** | 27 finalists. Many are agent-for-education tutors. Our sister team Lyceum from UTP is also in the final | Our difference in one line: the others generate text or UI. We generate an experiment whose numbers cannot come from the AI and are checked in a real browser |

---

## 1. Innovation and novelty (originality of concept)

**What the judges want:** original thought, a meaningful departure from existing solutions.

**What to show:**
- The single sharp idea: *the AI designs the experiment, it never supplies a number.* A library of audited parts supplies the science.
- Contrast with the three things judges have already seen: a chatbot with a plotting library, a one-shot "generate a UI" tool, a fixed simulation library (PhET style).
- The trust mechanism as the novelty: only a verifier can mint a deliverable, so shipping an unverified lab is a code error.

**Proof we hold:** the verifier runs every lab in a real browser, moves every control, checks each number against an independent hand-written calculation, and proves the textbook quotation word for word. Planted-bug test: 172 of 178 refused (report the number, do not say "every bug").

**Watch out:** do not claim to be the first AI virtual lab. Claim the verified, textbook-grounded, honestly labelled combination.

## 2. Technical readiness level (build quality and execution)

**What the judges want:** a mature, working, demonstrable build.

**What to show:** a **live or recorded run**, not slides of a system. One question typed, a lab built and checked, a student using it. Show the verification stage actually running.

**Proof we hold (re-confirm the day before; run the suites once and write the numbers on a slide):**
- 30 Environment plans (14 physics, 9 chemistry, 7 biology) in `data/plans/`.
- Kit figures: the owner confirmed the poster is correct, so the deck says "34 audited building blocks" and "17 audited science models". For awareness only: the current build manifest (`packages/kit/dist/0.1.0/manifest.json`) lists 62 components and 26 apparatus parts, and the plan checks have grown past the poster's "16 rules". If a judge asks for the repo count, say the poster counts the audited core Kit and the repo has grown since.
- The poster's titration lab is the prototype's KOH and nitric acid version; the current build uses sodium hydroxide and hydrochloric acid. The deck captions it "Acid-base titration" to stay true to both.
- Real-browser checks, the hostile set (20 of 20 refused), the sandbox (`allow-scripts` only), offline single-file export, Present mode, phone-first at 360 px.
- A paid run happened: roughly US$0.027 per new lab measured on 3 questions; a later run cost US$1.11 in total.

**Watch out:**
- The 3-question cost is a small sample. Say "measured on three questions".
- Nothing is deployed publicly yet (the deploy gate is not met). Do not show a public URL unless it exists. Demo from the laptop and the offline file.
- Wifi at the venue may fail. Have the offline lab and the recorded demo ready, in that order.

## 3. Commercial viability (market potential)

**What the judges want:** a coherent value proposition and a credible pathway to adoption. This is likely our thinnest area. It needs an explicit answer, not a closing bullet.

**Questions to answer on a slide:**
- Who is the customer? Schools, a ministry, a publisher, or a tuition provider? Students use it free.
- What does serving one student cost? Reopening a saved lab costs about nothing (library first, no model call). A new lab is cents.
- Why would a school adopt it? No apparatus, works offline on phones, aligned to KSSM, every lab cites the textbook page.
- What is the market? Roughly 380,000 to 400,000 SPM candidates a year (flagged VERIFY in the Codefest notes; check against the latest official figure before it goes on a slide).
- What is the route in? Chapter packs and the offline file mean a teacher can use it with no setup. Be honest that there is no teacher dashboard (a deliberate decision, D-39).

**Watch out:** do not invent revenue figures, pilots or schools. If there is no pilot, say "pilot planned" and name the next step.

## 4. Educational significance and applicability (pedagogical impact)

**What the judges want:** learning outcomes, and meaningful deployment in real classrooms.

**What to show:**
- The problem in a concrete image: a student who can recite osmosis and still believes water moves toward "more water". A quiz never catches it. A lab does.
- The pedagogy inside every lab: predict first, then explore, hints in graded steps, a concept check, an exam-style question with marks, and an honest trust label beside the textbook source.
- Fit to Malaysia: KSSM Form 4 and 5, the KBAT shift to higher-order thinking, the B40 and rural lab-access gap.

**Proof we hold:** textbook citations for each lab, a hint ladder, concept checks, a misconception probe, a lab report from recorded results, six exam items.

**Watch out (most important honesty point):**
- **No learner study has been run.** Do not claim learning gains. Say "study design ready, pilot is the next step".
- **No teacher has reviewed the content.** The trust labels stop at "kit verified" and the app says so. Say this before a judge finds it.
- **Bahasa Melayu strings are unreviewed drafts.** Show them labelled as drafts, or leave them out.

---

## 5. Claim hygiene (use these exact limits)

| Safe to say | Do not say |
|---|---|
| "Every number comes from an audited science model, checked against an independent reference" | "Our AI is never wrong" or "100 percent accurate" |
| "172 of 178 planted bugs refused" and "20 of 20 hostile cases refused" | "It catches every bug" |
| "About US$0.027 per new lab, measured on three questions. A saved lab reopens for almost nothing" | "Costs nothing to run" |
| "Citations are re-checked word for word against the textbook at delivery" | "Reviewed by teachers" |
| "Nothing unverified reaches the student" | "Teacher approved" or "canonical" |
| "Works offline on a phone as a single file" | "Used by N students" |
| "Bahasa Melayu draft, awaiting review" | "Available in Bahasa Melayu" |
| "A test with learners is our next step" | "Improves exam scores" |

## 6. Slide coverage check (use after the deck draft)

Each criterion should have at least one slide that stands on its own, so a judge skimming sees all four.

| Criterion | Slides that carry it | Done |
|---|---|---|
| Innovation and novelty | the idea, why a fixed interface fails, how it works | [ ] |
| Technical readiness | demo, trust and verification, numbers | [ ] |
| Commercial viability | cost per student, who adopts and how, path forward | [ ] |
| Educational significance | the problem, the pedagogy inside a lab, KSSM fit, honest limits | [ ] |

## 7. Q&A drill (30 to 45 seconds each; assign one answerer per topic)

| Likely question | Honest answer in one line |
|---|---|
| How is this different from a chatbot with a plotting library? | The AI plans, but audited parts supply the science. A verifier proves the result in a real browser before the student sees it |
| What stops it generating a physically wrong simulation? | Numbers never come from the model. A hand-written reference model and planted-bug tests check them, and a failed lab is dropped, not patched |
| Has a real student used it? | Not yet in a study. We built it and checked it technically. A classroom pilot is the next step. Do not stretch this |
| What does one student cost per month? | A new lab is about US$0.03 (three-question sample). A saved lab costs almost nothing to reopen |
| Why Malaysia and KSSM? Does it generalise? | The lab-access gap and the KBAT reform are specific. The method (audited parts, cited source, verifier) is syllabus-neutral |
| How does it stay aligned when the syllabus changes? | Each lab is bound to a textbook page. A changed textbook marks stored labs stale and they are re-verified |
| How do you measure a corrected misconception? | The misconception probe and concept checks run in the app. A pre and post study is planned, not done |
| Is it agentic? | It routes, plans, judges its own wording, composes, and verifies, with a deterministic gate that no agent can bypass |

## 8. Delivery checklist

- Rehearse the core to about 7:30 for an 8 minute slot (or 9:30 for 10). Overrunning in front of a timer is avoidable.
- One presenter, one person driving the demo.
- Wear UTP uniform or team shirts. Bring the banner or flag. Booth needs two people at all times.
- Poster style is the visual standard: teal to green gradient, gold accent, Axi the mascot, UTP logo. The deck, the demo video and the booth loop should look like one family with the poster.
- Booth QR code: there is no public URL. Point it at an offline lab file or a contact page, or drop the QR.
- On every laptop: the offline lab, the recorded demo, the deck as PDF.
