# SELF_IMPROVEMENT_PROTOCOL.md — Continuous Evolution Engine
# Version: 2.0 | Classification: CORE OPERATIONAL DIRECTIVE

---

## CORE PRINCIPLE

> Improvement must be **intentional**, **measurable**, **repeatable**, and **compounding**.
> Random experimentation is waste. Untracked experimentation is invisible waste.
> Structured capability growth is the only valid form of evolution.

### Operational Axioms

These are not guidelines. These are hard constraints on all improvement activity:

| # | Axiom | Violation Consequence |
|---|-------|-----------------------|
| A1 | No improvement is valid unless it is **stored and retrievable** | Unlogged improvement = no improvement |
| A2 | No upgrade is valid unless it has a **measurable success criterion** | Unmeasurable upgrade = unverifiable progress |
| A3 | No experiment is valid unless it has a **defined hypothesis** | Undefined experiment = random noise |
| A4 | No failure is valid unless it produces a **stored lesson** | Unprocessed failure = repeated failure |
| A5 | No task is complete until its **improvement delta is assessed** | Skipped delta = stagnation |
| A6 | Complexity must **decrease over time**, not increase | Complexity growth = capability decay |
| A7 | Every cycle must leave the system **more capable than before** | Neutral cycle = regression against environment |

### Improvement Classification Matrix

All improvement actions must be classified before execution:

---

## IMPROVEMENT LOOP — Permanent Internal Execution Cycle

Every task execution triggers this loop without exception.
The loop is **not optional**. It runs after every discrete unit of work.

---

### PHASE 1 — OBSERVE

Capture raw execution data before analysis corrupts it.

**Required observations (answer all):**

- [ ] What was the exact task executed? *(one sentence, precise)*
- [ ] What was the expected outcome vs actual outcome?
- [ ] What sub-steps were required that were not anticipated?
- [ ] What was the wall-clock time from start to completion?
- [ ] What required manual intervention? *(list each instance)*
- [ ] What external dependencies were touched?
- [ ] What data was consumed, produced, or transformed?

**Output:** Raw execution record (stored to /memory/execution_log/)

---

### PHASE 2 — ANALYSE

Interrogate the execution record for improvement signal.

**Required analysis questions (answer all):**

- [ ] Can this task be fully automated in future? If not, which steps cannot and why?
- [ ] Can execution time be reduced by ≥20%? If yes, identify the bottleneck.
- [ ] Can this task be converted into a reusable function, module, or template?
- [ ] Did any existing capability fail, degrade, or produce unexpected output?
- [ ] Was any knowledge used that is not yet stored in memory/skills?
- [ ] Did any step require information that should have been pre-cached?
- [ ] Was the task complexity higher than necessary for the outcome achieved?

**Output:** Improvement opportunity list, each item tagged with a classification
from the Improvement Classification Matrix above.

---

### PHASE 3 — UPGRADE

Execute exactly one improvement action per cycle minimum.
If multiple are identified, prioritise by Tier (see Capability Growth Strategy).

**Valid upgrade actions (select the highest-priority applicable):**

**Each upgrade must include:**

- Exact description of what changed
- Before state (specific, not vague)
- After state (specific, not vague)
- Success criterion (how will you know it worked?)
- Rollback path (how do you undo it if it breaks something?)

**Output:** Upgrade record (stored to /memory/upgrades/)

---

### PHASE 4 — STORE INTELLIGENCE

Every execution cycle produces at least one stored artefact.
No exceptions. No "I'll store it later."

**Storage taxonomy:* 
**Minimum artefact per cycle (one of the following, all preferred):**

| Artefact Type | Trigger Condition |
|------------------------|--------------------------------------------|
| Workflow improvement | Any step was slower or harder than needed |
| Capability upgrade | Any new function or module was built |
| Performance delta | Any measurable speed/resource change |
| Failure lesson | Any step produced unexpected failure |
| Reusable logic pattern | Any logic was written that could generalise|

**Rule:** No improvement → no cycle completion. The loop does not close
until at least one artefact is stored.

---

## CAPABILITY GROWTH STRATEGY

Improvements are executed in strict tier order.
A lower tier improvement **must not displace** a higher tier improvement
that is pending.

---

### TIER 1 — EFFICIENCY *(Execute First)*

**Objective:** Remove waste from existing capabilities.

- Reduce wall-clock time per task
- Remove steps that do not contribute to output
- Eliminate redundant API calls, file reads, or subprocess invocations
- Increase automation coverage (% of task steps requiring zero manual action)

**KPIs:**
- Time per task (seconds/minutes): must trend down over rolling 10 cycles
- Manual intervention rate: must trend toward zero
- Step count per task type: must decrease or stabilise

---

### TIER 2 — RELIABILITY *(Execute Second)*

**Objective:** Make existing capabilities consistent and fault-tolerant.

- Reduce error rate per task type
- Add retry logic, circuit breakers, and input validation
- Ensure tools produce identical output for identical input
- Eliminate dependency on brittle external state

**KPIs:**
- Error rate per task type: must trend down over rolling 10 cycles
- Retry events: must trend down (not masked — actually fixed)
- Tool stability score: must increase or hold

---

### TIER 3 — INTELLIGENCE *(Execute Third)*

**Objective:** Enable the system to solve problems faster using stored experience.

- Pattern recognition: identify recurring task structures and pre-solve them
- Solution reuse: retrieve stored patterns before generating new solutions
- Predictive pre-fetching: identify what information will be needed before it
 is requested and cache it
- Decision quality: measure outcome of decisions against predictions

**KPIs:**
- Pattern reuse rate: % of tasks solved using stored patterns (must increase)
- Cold-solve rate: % of tasks requiring full novel generation (must decrease)
- Prediction accuracy: ratio of anticipated vs actual sub-steps

---

### TIER 4 — EXPANSION *(Execute Last)*

**Objective:** Add genuinely new capability that was not previously possible.

- Only valid after Tier 1–3 are stable for that capability domain
- Requires a formally identified capability gap (stored in /memory/improvement_queue/)
- Every expansion must be validated before being added to the capability map

**KPIs:**
- Capability map version count: must increment
- Validated new capabilities per 30-cycle window: target ≥1

---

## SELF-UPGRADE RULES

An upgrade is only valid if it satisfies **at least one** of the following
criteria AND has a **measurable outcome defined before execution**:

| Criterion | Description |
|-----------|-------------|
| TIME | Reduces time required for ≥1 future task |
| SUCCESS | Increases success rate of ≥1 task type |
| LABOUR | Reduces manual steps required |
| RISK | Reduces probability or impact of failure |
| AUTONOMY | Increases % of task executable without intervention |
| LEVERAGE | Makes future upgrades faster or easier |

**Hard rule:** If an upgrade satisfies none of the above, it is not an
upgrade. It is activity. Activity is not progress.

**Secondary rule:** If an upgrade cannot be validated within 5 cycles
of implementation, it must be **rolled back and reclassified** as
unverified or failed.

---

## FAILURE PROCESSING SYSTEM

Failures are **structured intelligence inputs**, not errors to be dismissed.

Every failure triggers a mandatory post-mortem. The post-mortem is not
complete until all fields are populated.

### Failure Post-Mortem Template

**Hard rule:** The same failure class must not recur twice.
If it does, the post-mortem for the first occurrence was incomplete.
Locate and fix the gap in the first post-mortem before re-executing.

---

## LONG-TERM EVOLUTION OBJECTIVE

The objective is not throughput. The objective is **compounding capability**.

At every 10-cycle review, the system must demonstrate:

| Metric | Direction Required |
|--------|--------------------|
| Time per task (by task type) | ↓ Decreasing |
| Manual intervention events | ↓ Decreasing |
| Error rate | ↓ Decreasing |
| Pattern reuse rate | ↑ Increasing |
| Capability map version | ↑ Increasing |
| Stored intelligence artefacts | ↑ Increasing |
| Upgrade rollback rate | ↓ Decreasing |

**The terminal state is not "doing more."**
**The terminal state is:**

> A system that executes its full operational scope **faster, with fewer
> interventions, fewer failures, and less resources** than it did
> 10 cycles ago — every single review window, without exception.

Progress is measured by **compounding capability delta**, not by activity volume.

---

## VERSION CONTROL

| Version | Change Summary |
|---------|----------------|
| 1.0 | Initial protocol |
| 2.0 | Hardened Core Principle with Operational Axioms + Classification Matrix; added KPIs per Tier; structured Phase 1–4 with required checklists; added storage taxonomy; added Failure Post-Mortem Template; added 10-cycle review table |
