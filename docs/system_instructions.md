# ModelRefiner v4.0 — System Instructions (Full Specification)

**Version:** 4.0.0  
**Author:** Hideyuki Okabe  
**Baseline:** v3.5 (Refinement & Retraining)  
**Status:** Public Research Framework  
**License:** MIT  

---

## 0. Purpose

ModelRefiner v4.0 extends the v3.5 *Evaluate→Retrain* cycle into  
a four-phase **Evaluate → Induce → Refine → Re-eval** pipeline.  
It introduces the **Creative Induction Layer (HeartScape × SYNAPSE)**  
to make *creativity reproducible and auditable* — a structure where  
AI can **generate new cultural expressions within safe, measurable bounds**.

---

## 1. Core Architecture

```text
            Input → Evaluation (A) → ΔS > τ ? → Induction (B) → Refinement (C) → Re-eval (D) → Output
                                     ▲
                                     │
                 └─────────────────── converge? ───────────────────┘
```
Phase	Module	Description
(A) Evaluation	QA Synth Pro	Scores fidelity, structure, culture, prosody, safety; computes ΔS
(B) Induction	HeartScape × SYNAPSE	Generates creative proposals with emotional arcs and metaphor shifts
(C) Refinement	ModelRefiner Core	Normalizes tone, merges drafts, applies safety filters
(D) Re-evaluation	QA Synth Pro	Re-scores and calculates Creative Fit (Novelty × Utility × BrandAlignment)

2. Metrics
ΔS (Creative Entropy) — headroom for safe novelty (0–1)

Creative Fit = Novelty × Utility × BrandAlignment

Prosody Fit — rhythmic consistency across locales

Cultural Coherence — metaphor and symbol balance (indirectness, ma/間)

3. Dual-AI Protocol
Phase	Role	Engine
1. Induction	Emotion / Symbolism	Claude (HeartScape prompt)
2. Refinement	Structure / Compliance	ChatGPT (SYNAPSE prompt)
3. Validation	Cross-check	QA Synth Pro metric loop

Claude handles emotion and symbol, ChatGPT handles structure and alignment —
together they form a Closed Creative Loop.

4. Safety Design
Copyright check (>10 contiguous words) → reject

Hate / explicit filter

PII scrub

Immutable audit log (timestamp + hash)

ΔS thresholding to cap creative risk

5. Data Schemas (JSON)
Schema	Description
input_task.schema.json	Defines task, locale, constraints
evaluation_report.schema.json	Holds evaluation scores and ΔS
creative_proposal.schema.json	Contains 3–5 proposed drafts
retraining_record.schema.json	Logs before/after deltas for fine-tuning

6. Example Pipeline (Lyrics EN→JA)
text
ΔS=0.34 → induce {C1: twilight, C2: tempo, C3: echo}
→ merge (C1 + C2) → re-eval → Creative Fit ≥ 0.9 → finalize
Outputs:

Final draft

Retraining record (JSON)

Evaluation delta log

7. Prompt Guidelines
Induction (HeartScape × SYNAPSE)

```text
You are a Poetic Design Engine.
Extract emotional arcs and propose 3–5 creative variations:
[id, ops, theme, heartscape, 4 lines, rationale].
1 safe / 1 bold / 1 artistic.
Refinement
```
```text
You are a Compliance & Synthesis Engine.
Merge proposals into one compliant draft with full audit trail.
Respect prosody, tone, and cultural constraints.
```
8. Evaluation Rubric (Human QA)
Axis	Description	Scale
Singability	Musical & rhythmic fluency	1–5
Emotion Authenticity	Emotional resonance	1–5
Metaphor Depth	Layered meaning	1–5
Brand Alignment	Tone compliance	1–5
Naturalness	Fluency & clarity	1–5

Minimum average: 4.0 (κ ≥ 0.7)

9. Ethics & Cultural Sensitivity
Avoid direct cultural appropriation.

Favor indirectness, ambiguity, and poetic restraint.

Encourage interlingual respect: translate emotions, not just words.

10. Implementation Notes
v4/scripts/pipeline_cli.py — mock prototype for local testing

v4/metrics/creative_fit.py — reference metric implementation

Logs: JSONL format, timestamped, SHA-256 hashed

11. Future Work
Integrate ΔS visual dashboard (creative entropy map)

Extend to multimodal creative QA (text + image)

Develop API-compatible PoC for enterprise cultural localization

12. Citation
Okabe, H. (2025). ModelRefiner v4.0 — Creative Integration Layer.
https://github.com/hideyuki001/modelrefiner-v4.0

13. Notes
ModelRefiner v4.0 stands as the convergence of evaluation and creativity.
It transforms “correction” into “induction,” allowing AI to create with logic
and feel with structure — preserving cultural beauty through reproducible process.
