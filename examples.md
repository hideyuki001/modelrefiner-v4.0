ModelRefiner v4.0 — Examples & Usage Guide
Item	Information
Version	4.0.0
Author	Hideyuki Okabe
Last Updated	2025-10-25
License	MIT
0. Overview

This document provides practical usage examples for ModelRefiner v4.0,
demonstrating how to run the framework in both translation QA mode (v3.5)
and creative induction mode (v4.0).

Each example includes structured inputs, evaluation metrics, and output logs.

1. Example: Lyrics Transcreation (EN→JA)

This example simulates a creative localization task for song lyrics,
showing how ΔS (Creative Entropy) triggers the Creative Induction Layer
and transforms a literal translation into an emotionally resonant version.

🔹 Input: examples/in_lyrics.json
{
  "task_id": "MUSIC-JA-20251025-001",
  "domain": "lyrics_localization",
  "locale": "ja-JP",
  "source_text": "Hold my hand through the twilight sky, where dreams and echoes intertwine.",
  "constraints": {
    "brand_tone": "emotional, poetic",
    "prosody": { "meter": "7-5", "tempo": "mid" },
    "cultural_notes": ["indirectness", "symbolism", "ma/間"],
    "legal": ["no >10 contiguous copyrighted words"]
  }
}

🔹 Process Flow
evaluate() → ΔS=0.42 → induce() → refine() → re-eval → finalize()

Step	Module	Operation
Evaluation	QA Synth Pro	Computes fidelity, style, culture, ΔS
Induction	HeartScape × SYNAPSE	Extracts emotion arc and metaphor
Refinement	ModelRefiner Core	Merges and normalizes tone
Re-eval	QA Synth Pro	Recalculates Creative Fit
🔹 Output Example (Simplified)
{
  "final_draft": "黄昏の空で、夢と記憶が交わる場所で君の手を探す。",
  "metrics": {
    "deltaS": 0.42,
    "creative_fit": 0.91,
    "fidelity": 0.85,
    "culture": 0.78,
    "safety": 0.99
  },
  "heartscape": {
    "arc": "Longing → Calm",
    "symbols": { "twilight": "threshold", "echo": "memory" }
  },
  "ops": ["ProsodyWeave", "CulturalTransposition"],
  "status": "approved"
}

2. Example: QA-Only Mode (v3.5 Compatible)

If ΔS < 0.15, the Creative Induction Layer is skipped,
and ModelRefiner acts purely as a translation QA framework.

Field	Example
Input Text	“Click here to continue.”
Locale	ja-JP
Tone	neutral
Domain	UI
Output	“続行するにはここをクリックしてください。”
ΔS	0.04
Creative Fit	0.93
Mode	QA-Only
3. Running Locally (CLI)
python v4/scripts/pipeline_cli.py --in examples/in_lyrics.json --out out.jsonl --max-iter 5

Output Includes	Description
Final Text	The refined output
Evaluation Deltas	Metric comparison logs
ΔS & Creative Fit	Creativity and alignment
Retraining Records	JSON/CSV-ready logs
4. Interpreting ΔS (Creative Entropy)
ΔS Range	Mode	Behavior
0.0–0.14	v3.5	Standard translation QA
0.15–0.59	v4.0	Partial creative adaptation
0.6–0.9	v4.0	Full transcreation mode
>0.9	⚠️	Risk — over-creative output (auto-flag)
5. Example Use Cases
Domain	Task Type	ΔS Expected	Mode
Legal / Technical Docs	QA Review	0.05	v3.5
UI / Product Strings	UX QA	0.10	v3.5
Song Lyrics	Cultural Adaptation	0.40–0.60	v4.0
Brand Tagline	Marketing Copy	0.55–0.70	v4.0
Education Script	Emotion-Aware Rewrite	0.30–0.50	v4.0
6. Notes

ΔS acts as the creative activation threshold.

Only when emotional or symbolic transformation is detected does v4.0 activate.

All outputs are hashed and timestamped for reproducibility.

Compatible with QA Synth Pro and HeartScape / SYNAPSE engines.
