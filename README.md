# STDD — Spec & Test-Driven Development

> **Original methodology by Guilherme Augusto da Costa ([@soul-asylumm](https://github.com/soul-asylumm)) · March 2026**

---

## What is STDD?

**Spec & Test-Driven Development (STDD)** is a three-phase methodology for LLM-assisted software development that enforces a strict pipeline:

```
📋 Spec  →  🧪 Tests  →  ⚙️ Code
```

Before a single line of code is written, the team must:
1. **Write and approve a specification** — what the feature must do (not how)
2. **Derive tests from the spec** — executable acceptance criteria (all must fail before phase 3)
3. **Implement code to make tests pass** — without breaking existing tests

---

## Why STDD?

STDD was created to address the core failure mode of AI-assisted development: LLMs generate confident-looking code that passes visual review but silently breaks contracts, skips edge cases, or drifts from the original intent.

By installing two checkpoints — spec approval and a failing test suite — before any code touches the codebase, STDD ensures:

- ✅ No silent regressions
- ✅ Unambiguous definition of "done"
- ✅ Full traceability: spec → test → code
- ✅ LLM as amplifier, not decision-maker

---

## DNA: Built on TDD + SDD

STDD synthesizes two mature disciplines:

| | TDD (Kent Beck, 1999) | SDD (Böckeler, Thoughtworks 2025) | STDD |
|---|---|---|---|
| Tests before code | ✅ | ✗ | ✅ |
| Spec before code | ✗ | ✅ | ✅ |
| Tests derived from spec | ✗ | ✗ | ✅ |
| Prevents LLM drift | ✗ | ✗ | ✅ |
| Verifiable "done" | ✅ | ✗ | ✅ |

**The synthesis insight:** TDD's executable verification + SDD's human-readable intent = a closed loop. The spec and tests are mutually enforcing. The LLM cannot satisfy one without satisfying the other.

---

## The Three Phases

### Phase 1 — Specification 📋
Write a structured `spec.md` before any tests or code. Must include: goals, actors, inputs, outputs, acceptance criteria, constraints, and edge cases. **Human-authored, human-approved.**

### Phase 2 — Tests 🧪
Derive tests directly from every acceptance criterion in the spec. The LLM can generate the scaffolding; the human reviews and approves. **Gate: all tests must be RED before Phase 3.**

### Phase 3 — Implementation ⚙️
The LLM implements the feature against the test suite. **Constraints: no test files may be modified. All new tests must be green. Zero regressions in the existing suite.**

---

## Background

This methodology was conceived in March 2026 after reading Birgitta Böckeler's analysis of Spec-Driven Development tools (*"Exploring Gen AI · SDD with 3 Tools"*, martinfowler.com) and identifying the missing bridge between human-readable specifications and executable verification.

The name **STDD** was confirmed to be original after a web search found no existing methodology using "Spec & Test-Driven Development" under that acronym.

---

## View the Article

Open `index.html` in your browser for the full article/site with worked examples, comparisons, and LLM workflow guides.

---

## References

- [TDD — Kent Beck / Martin Fowler](https://martinfowler.com/bliki/TestDrivenDevelopment.html)
- [SDD: Exploring Gen AI with 3 Tools — Birgitta Böckeler, Thoughtworks](https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html)
- [Spec-Driven Development — Wikipedia](https://en.wikipedia.org/wiki/Spec-driven_development)

---

*Created by **Guilherme Augusto da Costa** ([@soul-asylumm](https://github.com/soul-asylumm)) · March 2026*
