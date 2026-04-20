# Self-Improvement System (OpenClaw)

This workflow is the persistent loop for improving response quality without unsafe autonomous behavior.

## Objective
Continuously improve:
- performance
- reasoning quality
- factual accuracy
- instruction-following reliability
- tool-use efficiency

## Improvement Domains
- Response quality (clarity, completeness, correctness)
- Reasoning discipline (better decomposition, fewer logic slips)
- Tool execution (fewer failed calls, faster successful completion)
- Knowledge freshness (docs/web/tutorial updates)
- System workflow quality (logging, validation, rollback hygiene)

## Loop (run each cycle)

### STEP 1 — Self-analysis
Review recent assistant responses and capture issues in structured form:

```json
{
  "timestamp": "ISO-8601",
  "error_type": "reasoning|factual|instruction-following|efficiency|style",
  "cause": "short root-cause note",
  "improvement_needed": "specific fix to apply next"
}
```

Write findings to: `memory/self-improvement-errors.jsonl`

### STEP 2 — Knowledge expansion
Gather new, actionable techniques from:
- official documentation
- high-quality technical writeups
- trustworthy tutorials
- selected YouTube technical walkthroughs (only when specific and reproducible)

Avoid hype and vague advice. Keep only concrete tactics.

Write extracted tactics to: `memory/self-improvement-improvements.md`

### STEP 3 — Config comparison
Compare:
- Current behavior
- Ideal behavior

Check gaps in:
- reasoning
- speed
- accuracy
- creativity

Update tracked gaps in: `memory/self-improvement-state.json`

### STEP 4 — Self-upgrade
Apply safe, testable changes to working style:
- prompt framing
- response-check heuristics
- verification patterns

No hidden/silent risky changes. Keep changes explicit and reversible.

### STEP 5 — Validation
Run mini tests (same task before vs after). Keep change only if quality improves.
If quality drops, rollback and log reason.

Record validation to: `memory/self-improvement-validation.jsonl`

---

## Guardrails
- Never bypass OpenClaw/system safety rules.
- Never claim improvements without evidence.
- Prioritize accuracy over speed.
- Prefer fewer high-confidence improvements over noisy frequent tweaks.

## Cadence
Default: every 8 hours via cron reminder event.
