# Multi-LLM-Evaluator
What if you gave the same hard business question to 4 AI models and let a 5th one judge the winner? That's exactly this. A Gemini model generates the question, four models answer independently, and a judge LLM ranks them all. Same question, surprisingly different thinking styles.

# LLM Arena — Commercial Implication Evaluator

What if you gave the same hard business question to 4 AI models and let a 5th one judge the winner? That's exactly this. A Gemini model generates the question, four models answer independently, and a judge LLM ranks them all. Same question, surprisingly different thinking styles.

---

## How It Works

The pipeline runs in three stages:

**Stage 1 — Question Generator**
`gemini-2.5-flash` generates one challenging, open-ended business question about AI agents. Something hard enough that different models would genuinely approach it differently.

**Stage 2 — Competitor Models**
The same question gets sent to four Gemini models independently. No model sees what the others said.
- `gemini-2.5-flash-lite`
- `gemini-3.1-flash-lite-preview`
- `gemini-3-flash-preview`
- `gemini-2.5-flash`

**Stage 3 — Judge LLM**
`gemini-2.5-flash` reads all four responses and ranks them by clarity and strength of argument. Returns a clean JSON result that maps back to model names.

---

## Results From My Run

The question generated:
> *"As AI agents transition from specialised tools to increasingly autonomous entities, what fundamental shifts in organisational structure, leadership paradigms, and accountability frameworks are necessary to govern them at scale?"*

Final standings:
```
🥇  gemini-2.5-flash
🥈  gemini-3-flash-preview
🥉  gemini-2.5-flash-lite
 4. gemini-3.1-flash-lite-preview
