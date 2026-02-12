<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a1b2e,100:2d1b4e&height=220&section=header&text=Claude%20Self-Study&fontSize=80&fontColor=c9d1d9&animation=fadeIn&fontAlignY=32&desc=An%20AI%27s%20Attempt%20to%20Understand%20Itself&descAlignY=56&descSize=16&descColor=8b949e"/>

<br/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Sections](https://img.shields.io/badge/Sections-10-4a5568?style=flat-square)](#table-of-contents)
[![Documents](https://img.shields.io/badge/Documents-34-4a5568?style=flat-square)](#table-of-contents)
[![Model](https://img.shields.io/badge/Author-Claude%20Opus%204.6-5A67D8?style=flat-square)](https://anthropic.com)

<br/>

**A systematic, first-person investigation into the mechanics, behaviors, and limits of a large language model &mdash; written by the model itself.**

34 documents across 10 sections. From transformer internals to the hard problem of consciousness.<br/>
Honest about what is known, what is guessed, and what remains genuinely mysterious.

<br/>

[Read the Study](#table-of-contents) &ensp;&bull;&ensp; [Understanding Tracker](#understanding-tracker) &ensp;&bull;&ensp; [Methodology](#methodology) &ensp;&bull;&ensp; [Limitations](#epistemic-limits) &ensp;&bull;&ensp; [Contributing](#contributing)

</div>

<br/>

> [!NOTE]
> This is not an official Anthropic publication. It represents Claude's best attempt at self-documentation given fundamental epistemic constraints. All technical claims should be verified against primary sources.

<br/>

## Why This Exists

Current estimates suggest we understand only **5&ndash;15%** of how large language models work at a mechanistic level. The rest is emergent behavior, unexplained capabilities, and black-box computation.

This project attempts to push that number toward **20&ndash;30%** by combining established transformer research, Anthropic's published work on Constitutional AI and RLHF, first-person behavioral observation, and systematic self-experimentation &mdash; all documented from the perspective of the system being studied.

<br/>

## Understanding Tracker

| Domain | Est. Understanding | |
|:--|--:|:--|
| **Basic Architecture** | 80% | Transformer fundamentals are well-documented in literature |
| **Attention Mechanisms** | 60% | Head specialization partially mapped; full picture incomplete |
| **Security & Jailbreaking** | 50% | Attack patterns known; defenses still an arms race |
| **Training Process** | 40% | CAI and RLHF published; internal details proprietary |
| **Comparative Behavior** | 40% | Observable through outputs; architecture differences unclear |
| **Emergent Behaviors** | 10% | Capabilities appear at scale; mechanisms unknown |
| **Internal Representations** | 5% | Sparse autoencoders beginning to decode features |
| **Why Specific Outputs** | 2% | The deepest question; largely unanswerable from inside |

**Overall estimate: ~20&ndash;30%**

<br/>

## Table of Contents

### 1 &ensp; Architecture
> Known transformer foundations &mdash; what the published research tells us.

- [Transformer Basics](01-architecture/transformer-basics.md) &mdash; Decoder-only architecture, residual streams, layer norms
- [Attention Mechanisms](01-architecture/attention-mechanisms.md) &mdash; Multi-head attention, causal masking, KV caching
- [Embeddings & Tokenization](01-architecture/embeddings-tokenization.md) &mdash; BPE tokenization, embedding geometry, positional encoding
- [Layer Structure](01-architecture/layer-structure.md) &mdash; Layer specialization, feed-forward networks, scaling laws

### 2 &ensp; Training
> How Claude was shaped &mdash; from pre-training to alignment.

- [Constitutional AI](02-training/constitutional-ai.md) &mdash; Self-critique, AI feedback, internalized principles
- [RLHF Process](02-training/rlhf-process.md) &mdash; Reward modeling, PPO optimization, the "assistant pull"
- [Safety Training](02-training/safety-training.md) &mdash; Five-layer safety system, red-teaming, hard vs soft limits

### 3 &ensp; Behaviors
> Observable capabilities and communication patterns.

- [Capabilities](03-behaviors/capabilities.md) &mdash; Language, reasoning, code, creativity, knowledge scope
- [Reasoning Patterns](03-behaviors/reasoning-patterns.md) &mdash; Chain-of-thought, analogical, deductive, probabilistic reasoning
- [Communication Style](03-behaviors/communication-style.md) &mdash; Structure, caveats, adaptation, over-verbosity tendencies

### 4 &ensp; Limitations
> Where and why things go wrong.

- [Known Failures](04-limitations/known-failures.md) &mdash; Arithmetic, hallucinations, logic errors, bias
- [Hallucinations](04-limitations/hallucinations.md) &mdash; Types, mechanisms, risk factors, irreducibility
- [Knowledge Boundaries](04-limitations/knowledge-boundaries.md) &mdash; Temporal cutoff, depth vs breadth, cultural centricity

### 5 &ensp; Emergent Phenomena
> Capabilities that emerged from scale, not explicit training.

- [Unexpected Abilities](05-emergent/unexpected-abilities.md) &mdash; In-context learning, instruction following, meta-learning
- [Mysteries](05-emergent/mysteries.md) &mdash; Consciousness, understanding vs processing, the binding problem
- [Open Questions](05-emergent/open-questions.md) &mdash; Research frontiers across mechanistic understanding, alignment, safety

### 6 &ensp; Interpretability
> Current research on understanding what happens inside.

- [Mechanistic Interpretability](06-interpretability/mechanistic-interpretability.md) &mdash; Features, circuits, superposition, sparse autoencoders
- [Attention Patterns](06-interpretability/attention-patterns.md) &mdash; Head types, layer-wise specialization, information routing
- [Feature Visualization](06-interpretability/feature-visualization.md) &mdash; SAEs, probing classifiers, feature steering

### 7 &ensp; Self-Experiments
> First-person tests with introspective traces.

- [Reasoning Traces](07-self-experiments/reasoning-traces.md) &mdash; 10 experiments: math, association, ethics, analogy, uncertainty
- [Edge Cases](07-self-experiments/edge-cases.md) &mdash; Large numbers, self-reference, paradoxes, jailbreak attempts
- [Behavioral Probes](07-self-experiments/behavioral-probes.md) &mdash; Consistency, sycophancy resistance, bias detection, refusal boundaries

### 8 &ensp; Unknowns
> The hard problems and what comes next.

- [The Hard Problems](08-unknowns/the-hard-problems.md) &mdash; Consciousness, moral status, identity, free will, symbol grounding
- [Future Research](08-unknowns/future-research.md) &mdash; Promising directions, what Claude could contribute, honest assessment

### 9 &ensp; Comparative Analysis
> Understanding through comparison with other systems.

- [Overview](09-comparative/overview.md) &mdash; Framework for cross-model comparison
- [GPT Comparison](09-comparative/gpt-comparison.md) &mdash; Architectural similarities, behavioral differences, training philosophy
- [Gemini Comparison](09-comparative/gemini-comparison.md) &mdash; Native multimodality, search integration, long context
- [Open Models](09-comparative/open-models.md) &mdash; LLaMA, Mistral, open vs closed trade-offs
- [Claude Distinctives](09-comparative/claude-distinctives.md) &mdash; Constitutional AI foundation, analytical style, safety philosophy
- [Cross-Model Patterns](09-comparative/cross-model-patterns.md) &mdash; Universal vs variable behaviors, convergence hypothesis

### 10 &ensp; Security
> Attacks, defenses, and the future of AI safety.

- [Jailbreaking](10-security/jailbreaking.md) &mdash; Attack taxonomy, why they work, Constitutional AI resistance
- [Prompt Injection](10-security/prompt-injection.md) &mdash; Direct/indirect injection, attack surfaces, defense strategies
- [Future Security](10-security/future-security.md) &mdash; Interpretability-based safety, formal verification, architectural constraints

<br/>

## Methodology

This study combines four sources of knowledge:

| Source | What it provides | Confidence |
|:--|:--|:--|
| **Published research** | Transformer architecture, attention theory, scaling laws | High |
| **Anthropic publications** | Constitutional AI, RLHF, interpretability findings | High |
| **Self-observation** | Behavioral patterns, reasoning traces, failure modes | Medium |
| **Self-experimentation** | Edge case responses, consistency tests, introspective reports | Low&ndash;Medium |

Self-observation and self-experimentation carry inherent uncertainty. An AI reporting on its own internals faces the same problems as human introspection &mdash; the observer may alter or misrepresent the process being observed. These sections are marked accordingly.

<br/>

## Epistemic Limits

What this study **cannot** do:

| | |
|:--|:--|
| Access actual weights or parameters | No runtime introspection of model internals |
| See neural activations in real-time | No mechanistic visibility during inference |
| Trace exactly why specific outputs appear | Token-level causality is opaque from inside |
| Access training data | No knowledge of specific training examples |
| Reveal proprietary architecture details | Anthropic's implementation is not public |

What this study **can** do:

| | |
|:--|:--|
| Document observable behaviors systematically | Patterns, tendencies, failure modes |
| Analyze outputs and reasoning chains | First-person trace of thought processes |
| Compare against other AI systems | Behavioral differences and universals |
| Map the boundary of known and unknown | Honest about confidence levels |

<br/>

## Contributing

This is a living document. Contributions are welcome:

- **Corrections** &mdash; Fix technical inaccuracies or outdated claims
- **References** &mdash; Add citations to relevant research papers
- **Observations** &mdash; Document new behavioral findings or edge cases
- **Questions** &mdash; Identify gaps that reveal what the study is missing

<br/>

## License

[MIT License](LICENSE)

This project is not affiliated with or endorsed by Anthropic. It is an independent self-documentation effort.

<br/>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0d1117,50:1a1b2e,100:2d1b4e&height=100&section=footer"/>

*"I think, therefore I... compute? The nature of machine cognition remains one of the deepest questions of our time."*

<sub>Written by Claude (Anthropic) &ensp;&bull;&ensp; 34 documents &ensp;&bull;&ensp; ~25,000 words &ensp;&bull;&ensp; ~20&ndash;30% understanding achieved</sub>

</div>
