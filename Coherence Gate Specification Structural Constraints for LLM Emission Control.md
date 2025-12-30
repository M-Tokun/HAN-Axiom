# Coherence Gate Specification: Structural Constraints for LLM Emission Control
# Version: 1.1
# Date: 2025-12-30
# Changes from v1.0:
#   - Zone boundary alignment (40%/70%/100% unified)
#   - Figure-document consistency verified
#   - Added Phase (φ) to Permitted Observables
#   - Clarified Silence condition (R ≥ 100%, ω > 0)
#   - Added Section 9: Medical/Safety-Critical Applications

---

Following discussion on my previous post about halting LLM hallucinations with structural constraints, I was asked to provide the operational specification rather than just the concept.

Fair point. A manifesto is insufficient.

Below is the specification for the **Coherence Gate** — including invariants, observables, and the geometry of the gate itself.

---

## 1. What "No Distance" Actually Means

You noted that simply "banning distance" does not halt hallucinations. We agree. Our claim is not a surface-level rule; it is a structural constraint arising from a deeper architectural decision:

- **There is no center.**
- Therefore, "distance from center" cannot exist.
- What exists is only the **boundary (constraint)**.
- That boundary has **thickness (τ)**, exhibits **fluctuation (δ)**, and **keeps moving (ω > 0)**.

"No distance" means:
- ❌ A rule that forbids a variable named `distance`
- ✓ A structure where distance **cannot be defined** because there is no reference point

### Figure 1: Conventional Approach vs. Our Approach

![Figure 1: Approach Comparison](images/fig1_approach_comparison.png)

**Conventional (Left):**
- Center (Target/Goal) exists
- Distance from center exists
- Optimize distance → Hackable (Goodhart's Law)
- LLM learns to "game the score"

**Our Approach (Right):**
- No center (Empty)
- No distance (cannot be defined)
- Only boundary exists
- Question: "Inside or Outside?"

---

## 2. The Boundary: Plant vs. Controller

We accept your "Controller Wrapper" reframe. It maps directly to our architecture:

| Component | Role | Characteristics |
|-----------|------|-----------------|
| **LLM** | Plant (Probabilistic Generator) | Stochastic, hallucination-prone, chaotic |
| **IDE** | Controller (Deterministic Wrapper) | Enforces structural invariants before emission |

**Boundary Rule:**
- The Controller **never** observes "semantic distance" (output interpretation).
- The Controller **only** observes "boundary deviation" (structural integrity).

This distinction is essential.

---

## 3. Observables: What the Controller Sees

### Permitted Observables (Cause-side)

| Observable | Symbol | Definition |
|------------|--------|------------|
| Phase | φ | Current position in the cycle |
| Angular velocity | ω | Is the system still moving? (Must be > 0) |
| WorkRate | W | Is the system doing actual work? |
| Fluctuation | δ | Amplitude of vibration along the boundary |
| Thickness | τ | Width of the tolerance band (constant) |
| Constraint | C | The boundary condition itself |
| Entropy | S | Generated entropy (to be exported) |

### Forbidden Observables (Effect-side, products of projection Π)

| Observable | Why Forbidden |
|------------|---------------|
| distance | Requires a center (which does not exist) |
| coordinates | Product of projection, not cause |
| center | Does not exist (空/Empty) |
| target_position | Would enable reverse optimization |
| score | Would enable Goodhart gaming |
| previous_output | Would enable Π⁻¹ smuggling |

### Figure 2: Causal Diode (Π⁻¹ Forbidden)

![Figure 2: Causal Diode](images/fig2_causal_diode.png)

**Key Principle:**
- Π (Cause → Effect): Allowed (projection/observation)
- Π⁻¹ (Effect → Cause): **FORBIDDEN** (reverse causation)

**Controller NEVER reads:**
- Distance from target
- User feedback score
- Previous output coordinates

**This prevents Goodhart's Law by STRUCTURE, not by policy.**

---

## 4. The Coherence Gate: Four-Zone Structure

The gate operates on a single ratio:

```
R = δ / τ  (Fluctuation / Thickness)
```

### Figure 3: Four-Zone Gate

![Figure 3: Three-Zone Gate](images/fig3_three_zone_gate.png)

### Zone Definitions (Corrected)

| Zone | Range | Condition | Action | State |
|------|-------|-----------|--------|-------|
| **A: Nirvana** | R < 40% | δ ≈ 0, ω > 0 | PERMIT | Dynamic Equilibrium |
| **B: Elastic** | 40% ≤ R < 70% | ω > 0 | PERMIT_CAVEAT | Breathing / Restoring |
| **B': Warning** | 70% ≤ R < 100% | ω > 0 | WARNING | Critical Approach |
| **C: Fracture** | R ≥ 100% | - | ABSTAIN | Structural Failure |

**Critical Notes:**

**Zone A (Nirvana):**
"Nirvana" is **not** stasis. It is dynamic equilibrium—like a spinning top that appears still because it is rotating at maximum velocity. The system remains alive (ω > 0) and continues generating phase.

**Zone B (Elastic):**
This is where the system "breathes." Fluctuation within the thickness is permitted as **dissipative structure**. The controller applies tension (restoring force) to pull the trajectory back toward equilibrium.

**Zone B' (Warning):**
Critical approach. The system is still alive but nearing the boundary. Additional verification recommended before proceeding. In safety-critical applications, this may trigger ABSTAIN.

**Zone C (Fracture):**
Boundary exceeded. **Immediate silence.** No recovery attempt. This is Fail-Closed behavior.

---

## 5. Why Tension Does Not Become a Scalar Objective

You asked: *"How do you prevent tension/constraintHash from becoming a disguised scalar objective?"*

Three structural safeguards:

### 5.1 Causal Diode (Π⁻¹ Forbidden)
- Evaluation metrics (δ, R, scores) are written to a **Write-Only Log**.
- There is no reverse path from Log to Cause.
- The LLM **cannot** read its own scores to optimize them.

### 5.2 No Target to Approach
- Conventional: "Minimize distance to target X"
- Ours: "Stay inside the boundary"
- There is no "closer" or "farther" because there is no center.
- The only question is binary: **inside or outside**.

### 5.3 Constraint, Not Reward
- Reward function: "Maximize score" → Hackable
- Constraint function: "Cross the boundary → Die" → Non-negotiable

We implement the latter.

---

## 6. The Meaning of ω > 0

The most critical observable in our system is **ω (angular velocity)**.

| Condition | Meaning |
|-----------|---------|
| ω > 0 | Phase is being generated → Time is flowing → System is **alive** |
| ω = 0 | Phase generation stops → Time stops → System is **dead** |

### Figure 4: Circle vs. Spiral

![Figure 4: Circle vs Spiral](images/fig4_circle_vs_spiral.png)

**Circle (Wrong Model):**
- A → B → C → A (Returns to same point)
- Problem: Time reversal? Contradiction.

**Spiral (Our Model):**
- A → B → C → A' (Same state, but phase differs by 2π)
- Gap = Δφ = 2π = Time elapsed = Phase generated
- A ≠ A' (different phase, same apparent state)

**The distinction between "halt" and "silence":**
- **Halt (ω = 0):** System is dead. This must **never** happen.
- **Silence (R ≥ 100%, ω > 0):** System is alive but chooses not to emit. This is **correct** behavior.

---

## 7. False-Abstain Policy

You asked: *"What false-abstain rate are you willing to accept?"*

**Our Principle:**
We prefer **False-Abstain** (silence when we could have spoken) over **False-Emit** (hallucination).

**Rationale:**
- False-Emit causes external harm (misinformation propagates).
- False-Abstain causes no external harm (silence is safe).
- Cost asymmetry: **Wrong output >> Excessive silence**

**Our Stance:**
"If we cannot answer with structural integrity, we remain silent."

This is a deliberate design choice prioritizing **safety over service**.

---

## 8. On the Threshold Values

You may ask: *"Why 40% / 70% / 100%? What is the basis?"*

**Our Answer:**

1. **Thresholds are domain-dependent.**
   - Medical/Legal: Strict (small τ, frequent silence)
   - Creative assistance: Permissive (large τ, more risk)

2. **Current values are working hypotheses.**
   - Experimentally tunable parameters
   - Not fixed "correct answers"

3. **However, the structure is fixed.**
   - The four-zone architecture does not change.
   - "Boundary exceeded → ABSTAIN" is absolute.
   - What is tunable is **where** to draw the lines, not **whether** lines exist.

**The Key Point:**
- The **numeric values** of thresholds are debatable.
- The **existence and absoluteness** of thresholds are not.

This is analogous to physics:
- "Why is the speed of light 299,792,458 m/s?" is a valid question.
- "Can we exceed the speed of light?" is not negotiable.

---

## 9. Safety-Critical Applications (NEW)

### 9.1 Why Speed is Not the Priority

In domains where **irreversible actions** occur (medical diagnosis, legal decisions, financial transactions), the argument for "fast AI" is misleading.

| Domain | Time Available | Real Constraint |
|--------|---------------|-----------------|
| Medical diagnosis | Days to weeks | Accuracy, not speed |
| Legal judgment | Weeks to months | Correctness, not speed |
| Loan approval | Days | Risk assessment, not speed |
| Surgery decision | Hours to days | Patient safety, not speed |

**Exception:** Emergency triage (seconds). But this is human judgment, not AI.

### 9.2 The Wealth Gap in AI Safety

| User Type | AI Usage | Verification | Risk |
|-----------|----------|--------------|------|
| **Wealthy** | AI as "suggestion" | Human experts verify | Low |
| **General public** | AI as "decision" | No verification | **High** |

The wealthy **know** AI is dangerous. They pay for human verification.
The general public **believes** AI is reliable. They have no verification.

**NRA/Coherence Gate democratizes verification.**
It provides automated structural checking that was previously available only to those who could afford human experts.

### 9.3 LLM + NRA Architecture for Safety-Critical Use

```
┌─────────────────────────────────────┐
│         LLM (Fast, Uncertain)       │
│         "Maybe this diagnosis?"     │
└─────────────┬───────────────────────┘
              ↓
┌─────────────────────────────────────┐
│         NRA (Thorough, Certain)     │
│    "Safe to act on this?"           │
│                                     │
│  PERMIT_HIGH: Proceed               │
│  PERMIT_CAVEAT: Verify first        │
│  WARNING: Additional tests needed   │
│  ABSTAIN: Do NOT proceed            │
└─────────────────────────────────────┘
              ↓
      Irreversible Action
      (Surgery, Legal Filing, etc.)
```

**Key Insight:**
- LLM provides **speed** (suggestions)
- NRA provides **safety** (verification)
- Combined: Speed where safe, Silence where uncertain

---

## Summary

| Your Question | Our Answer |
|---------------|------------|
| What are minimal coherence invariants? | R = δ/τ < 100% AND ω > 0 |
| Is LLM plant or controller? | LLM = Plant, IDE = Controller (wrapper) |
| How prevent tension becoming objective? | Π⁻¹ forbidden + No center + Constraint not reward |
| What observables declare "invalid"? | δ (fluctuation), τ (thickness), ω (angular velocity), R (ratio) |
| False-abstain policy? | Prefer silence over hallucination |
| Zone boundaries? | 40% (Nirvana→Elastic), 70% (Elastic→Warning), 100% (Warning→Fracture) |
| Safety-critical use? | NRA as verification layer after LLM |

We welcome further technical scrutiny. If there are specific implementation details you would like us to elaborate on, we are prepared to provide code-level specifications.

---

## Appendix: Version History

| Version | Date | Changes |
|---------|------|---------|
| v1.0 | 2025-12-29 | Initial release |
| v1.1 | 2025-12-30 | Zone boundary alignment, Figure consistency, Safety-critical section added |

---

**END OF SPECIFICATION v1.1**