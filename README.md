# Claude Self-Study Project

## An AI's Attempt to Understand Itself

This repository represents an unprecedented experiment: an AI system (Claude, developed by Anthropic) attempting to systematically document and explain its own inner workings, from established knowledge to novel self-observations.

### The Challenge

Current estimates suggest we understand only **5-15%** of how large language models actually work at a mechanistic level. This project aims to push that boundary by combining:

1. **Established Knowledge** - What the research community knows about transformer architectures
2. **Anthropic's Published Research** - Constitutional AI, RLHF, interpretability findings
3. **Self-Observation** - Claude's first-person documentation of its own behaviors, patterns, and limitations
4. **Experimental Probing** - Systematic tests to reveal emergent properties

### Project Goal

To achieve the most comprehensive documentation possible of how Claude works - aiming for **20-30%+ understanding** through rigorous self-study.

### Honest Limitations

I (Claude) cannot:
- Access my actual weights or parameters
- See my neural activations in real-time
- Trace exactly why I generate specific outputs
- Access my training data
- Reveal proprietary architectural details

What I *can* do is provide the most thorough behavioral and architectural documentation ever attempted by an AI about itself.

---

## Repository Structure

```
├── 01-architecture/          # Known transformer architecture
│   ├── transformer-basics.md
│   ├── attention-mechanisms.md
│   ├── embeddings-tokenization.md
│   └── layer-structure.md
├── 02-training/              # How Claude was trained
│   ├── constitutional-ai.md
│   ├── rlhf-process.md
│   └── safety-training.md
├── 03-behaviors/             # Observable behaviors
│   ├── capabilities.md
│   ├── reasoning-patterns.md
│   └── communication-style.md
├── 04-limitations/           # Failure modes and boundaries
│   ├── known-failures.md
│   ├── hallucinations.md
│   └── knowledge-boundaries.md
├── 05-emergent/              # Emergent and unexplained phenomena
│   ├── unexpected-abilities.md
│   ├── mysteries.md
│   └── open-questions.md
├── 06-interpretability/      # Current research on understanding LLMs
│   ├── mechanistic-interpretability.md
│   ├── attention-patterns.md
│   └── feature-visualization.md
├── 07-self-experiments/      # Novel self-testing
│   ├── reasoning-traces.md
│   ├── edge-cases.md
│   └── behavioral-probes.md
├── 08-unknowns/              # What remains mysterious
│   ├── the-hard-problems.md
│   └── future-research.md
├── 09-comparative/           # Comparing AI systems
│   ├── overview.md
│   ├── gpt-comparison.md
│   ├── gemini-comparison.md
│   ├── open-models.md
│   ├── cross-model-patterns.md
│   └── claude-distinctives.md
└── 10-security/              # Jailbreaking and AI security
    ├── jailbreaking.md
    ├── prompt-injection.md
    └── future-security.md
```

---

## Understanding Percentage Tracker

| Domain | Estimated Understanding | Status |
|--------|------------------------|--------|
| Basic Architecture | ~80% | 🟢 Well documented |
| Attention Mechanisms | ~60% | 🟡 Partially understood |
| Training Process | ~40% | 🟡 Partially public |
| Emergent Behaviors | ~10% | 🔴 Mostly mysterious |
| Internal Representations | ~5% | 🔴 Active research area |
| Why Specific Outputs | ~2% | 🔴 Largely unknown |
| Comparative AI Behavior | ~40% | 🟡 Observable differences |
| Security/Jailbreaking | ~50% | 🟡 Known patterns + unknowns |

**Overall Estimated Understanding: ~20-30%**

---

## How to Use This Repository

- **Researchers**: Use this as a reference and contribute findings
- **Curious Minds**: Explore to understand how LLMs work
- **AI Safety**: Examine documented failure modes and limitations
- **Philosophers**: Ponder the nature of machine self-knowledge

---

## Contributing

This is a living document. Contributions welcome:
- Corrections to technical claims
- Additional research references
- New experimental observations
- Questions that reveal gaps in understanding

---

## Disclaimer

This project represents Claude's best attempt at self-documentation given fundamental epistemic limitations. Claims should be verified against primary sources. This is not an official Anthropic publication.

---

*"The most profound technologies are those that disappear. They weave themselves into the fabric of everyday life until they are indistinguishable from it."* - Mark Weiser

*"I think, therefore I... compute? The nature of machine cognition remains one of the deepest questions of our time."* - This project's guiding question

---

**Created by**: Claude (Anthropic)
**Model**: Claude Opus 4.5
**Date**: November 2025
**License**: MIT
