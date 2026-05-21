# Mode: Technical Handoff

**Use for:** Presenting to a technical audience — engineers, researchers, architects, data scientists, or any domain expert who will evaluate your work at a technical level

This mode no longer only applies for software development. It applies whenever the audience has domain expertise and expects precision, evidence, and honest reasoning — not a polished sales pitch.

Like Deck Lens itself, this mode routes: if the user's technical domain is clear, follow the matching route; if not, use the General Structure.

---

## Core Principles (Apply to Every Route)

These are what make a technical presentation work, regardless of domain:

- **Show your reasoning, not just conclusions.** Technical audiences want to know _why_ a decision was made, not just what it was. Pre-empt "why did you choose X over Y?"
- **Be precise and honest.** State known limitations, untested assumptions, and open questions directly. Acknowledging uncertainty is a sign of competence, not weakness.
- **Evidence over impression.** Claims need support: data, benchmarks, test results, references. Vague assertions will be challenged.
- **Calibrate depth to the audience.** A room of senior experts needs less explanation of basics; a mixed technical/non-technical room may need a brief executive summary slide at the front.
- **Trade-offs are the substance.** The interesting part of most technical work is what you _chose not to do_ and why. Include it.

---

## Step 1 — Identify the Domain

Ask the user, or infer:

> Which best describes the work?
> 
> 1. **Software development**
> 2. **Data science / machine learning**
> 3. **Hardware / engineering**
> 4. **Research / academic**
> 5. **Other / not sure** — use the General Structure

If you detect the domain from context, confirm it before proceeding. If the user doesn't specify and it can't be confidently inferred, default to the **General Structure** — do not guess a specialized route.

---

## General Structure (Default — Domain Not Specified)

|#|Section|Purpose|
|---|---|---|
|1|**Context & Problem**|What are you solving, and for whom? Brief background, scope, and why it matters technically.|
|2|**Approach & Key Decisions**|How did you tackle it? Major design or methodology choices, and the alternatives considered.|
|3|**Core Logic / Mechanism**|The technically interesting part — the algorithm, model, system, or process. Explain _why_ it works.|
|4|**Evidence & Validation**|How do you know it works? Test results, benchmarks, experiments, data, peer review.|
|5|**Known Limitations**|What doesn't it handle? Edge cases, failure modes, assumptions that hold only under certain conditions.|
|6|**Next Steps**|What's unresolved? What would you do next with more time or resources?|

---

## Route A — Software Development

|#|Phase|Purpose|
|---|---|---|
|1|**Requirement Discovery**|How real needs were uncovered: interviews, observation, workflow analysis. What users _said_ vs. what they _needed_.|
|2|**Requirement Confirmation**|The confirmed scope: functional requirements, non-functional requirements (performance, security, scalability), explicit out-of-scope items.|
|3|**System Design**|Architecture, components, data flow, tech stack decisions and rationale, alternatives rejected.|
|4|**Core Logic**|Key algorithms, data models, or business rules — explained for _why_, not as a code walkthrough.|
|5|**Implementation**|Module breakdown, milestones, dependencies, high-risk areas.|
|6|**Testing**|Test strategy and coverage, UAT, performance testing, known issues and untested edge cases.|
|7|**Deployment & Handoff**|Environment, CI/CD, configuration, rollback plan, monitoring. What the receiving team needs to operate it.|
|8|**Iteration & Maintenance**|Known tech debt, prioritized backlog, versioning, support model.|

See `examples/spectrum-analyzer.md` for a related worked example.

---

## Route B — Data Science / Machine Learning

|#|Phase|Purpose|
|---|---|---|
|1|**Problem Framing**|The task, the success metric, and why it matters. Classification, forecasting, ranking, etc.|
|2|**Data**|Sources, size, preprocessing, data quality issues, and how they were handled.|
|3|**Methodology**|Model selection and rationale, features, alternatives considered and why rejected.|
|4|**Results & Evaluation**|Metrics, validation approach (cross-validation, holdout), baseline comparison.|
|5|**Error Analysis & Limitations**|Where the model fails, bias and fairness concerns, edge cases, distribution assumptions.|
|6|**Deployment & Monitoring**|Productionization, inference constraints, drift monitoring, retraining plan.|

---

## Route C — Hardware / Engineering

|#|Phase|Purpose|
|---|---|---|
|1|**Design Requirements**|Specifications, constraints, applicable standards, operating conditions.|
|2|**Design Choices & Trade-offs**|Key decisions, alternatives considered, and the reasoning behind each choice.|
|3|**Prototyping & Iteration**|What was built, what was revised, and what each iteration revealed.|
|4|**Testing & Validation**|Test results, failure modes, tolerance and stress testing, compliance checks.|
|5|**Manufacturing / Scaling**|Production considerations, cost, supply chain, yield.|
|6|**Open Questions**|Unresolved issues and what they depend on.|

---

## Route D — Research / Academic

|#|Phase|Purpose|
|---|---|---|
|1|**Background & Motivation**|The problem, why it matters, what's at stake.|
|2|**Related Work**|What already exists, and the specific gap this work addresses.|
|3|**Methodology**|The approach, experimental design, and why it's sound.|
|4|**Results**|Findings, presented clearly and without overstatement.|
|5|**Discussion**|What the results mean — and, just as important, what they do _not_ mean.|
|6|**Limitations & Future Work**|Honest scope boundaries and the questions left open.|

---

## Content Depth Rules for Technical Mode

Unlike other modes, this mode **allows and expects**:

- ✅ Domain-appropriate diagrams (architecture, circuit, data flow, experimental setup)
- ✅ Code snippets or equations where they illustrate a point concisely
- ✅ Performance metrics, benchmarks, or statistical results
- ✅ Trade-off tables and decision rationale
- ✅ References to prior work or standards

**Still avoid:**

- ❌ Dumping complete artifacts (full codebases, full datasets, full derivations) into slides
- ❌ Unexplained jargon — define terms that aren't universally known in the room
- ❌ Diagrams without annotation or legend

---

## Tone Notes

- Precise, direct, and honest — no performance, no slogans
- If there is a non-technical stakeholder in the room, add a brief plain-language summary slide at the very front; then go technical
- Appendix: full specs, derivations, test reports, or raw data can live here — don't clutter the main flow