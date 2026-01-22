# Bibliography & Research Citations

A curated collection of research papers, publications, and resources referenced in or relevant to the Claude Self-Study project.

---

## Table of Contents

- [Foundational Papers](#foundational-papers)
- [Anthropic Research](#anthropic-research)
- [Mechanistic Interpretability](#mechanistic-interpretability)
- [Training & Alignment](#training--alignment)
- [Language Models & Scaling](#language-models--scaling)
- [AI Safety](#ai-safety)
- [Emergent Behaviors](#emergent-behaviors)
- [Security & Adversarial](#security--adversarial)
- [Philosophy of Mind & AI](#philosophy-of-mind--ai)
- [Additional Resources](#additional-resources)

---

## Foundational Papers

### Attention Is All You Need
**Vaswani, A., et al. (2017)**
The paper that introduced the Transformer architecture.
- Introduced self-attention mechanism
- Eliminated recurrence in sequence models
- Foundation for modern LLMs

*Link: https://arxiv.org/abs/1706.03762*

*Referenced in: [Transformer Basics](01-architecture/transformer-basics.md), [Attention Mechanisms](01-architecture/attention-mechanisms.md)*

---

### BERT: Pre-training of Deep Bidirectional Transformers
**Devlin, J., et al. (2018)**
Bidirectional encoder representations, contrasting with autoregressive models.
- Masked language modeling
- Bidirectional context
- Transfer learning for NLP

*Link: https://arxiv.org/abs/1810.04805*

*Referenced in: [GLOSSARY.md](GLOSSARY.md)*

---

### Language Models are Few-Shot Learners (GPT-3)
**Brown, T., et al. (2020)**
Demonstrated in-context learning and emergent capabilities at scale.
- In-context learning
- Scaling laws for performance
- Few-shot capabilities

*Link: https://arxiv.org/abs/2005.14165*

*Referenced in: [Capabilities](03-behaviors/capabilities.md), [GPT Comparison](09-comparative/gpt-comparison.md)*

---

### GPT-4 Technical Report
**OpenAI (2023)**
Technical overview of GPT-4's capabilities and limitations.

*Link: https://arxiv.org/abs/2303.08774*

*Referenced in: [GPT Comparison](09-comparative/gpt-comparison.md)*

---

## Anthropic Research

### Constitutional AI: Harmlessness from AI Feedback
**Bai, Y., et al. (2022)**
Anthropic's approach to aligning AI systems using principles.
- Self-critique methodology
- Principle-based training
- Reduced reliance on human labeling

*Link: https://arxiv.org/abs/2212.08073*

*Referenced in: [Constitutional AI](02-training/constitutional-ai.md), [Safety Training](02-training/safety-training.md)*

---

### Training a Helpful and Harmless Assistant with RLHF
**Bai, Y., et al. (2022)**
Foundational work on RLHF for language models.
- Helpfulness vs harmlessness tradeoffs
- Reward model training
- PPO optimization

*Link: https://arxiv.org/abs/2204.05862*

*Referenced in: [RLHF Process](02-training/rlhf-process.md)*

---

### The Claude Model Card
**Anthropic (2024)**
Official documentation of Claude's capabilities and limitations.

*Link: https://www.anthropic.com/claude*

*Referenced in: [Capabilities](03-behaviors/capabilities.md), [Known Failures](04-limitations/known-failures.md)*

---

### Scaling Monosemanticity: Extracting Interpretable Features
**Templeton, A., et al. (2024)**
Large-scale application of sparse autoencoders to Claude.
- Millions of interpretable features
- Safety-relevant features identified
- Scaling dictionary learning

*Link: https://transformer-circuits.pub/2024/scaling-monosemanticity/*

*Referenced in: [Feature Visualization](06-interpretability/feature-visualization.md), [Mechanistic Interpretability](06-interpretability/mechanistic-interpretability.md)*

---

### Towards Monosemanticity: Decomposing Language Models With Dictionary Learning
**Bricken, T., et al. (2023)**
Using sparse autoencoders to find interpretable features.
- Sparse dictionary learning
- Monosemantic features
- Overcoming polysemanticity

*Link: https://transformer-circuits.pub/2023/monosemantic-features/*

*Referenced in: [Feature Visualization](06-interpretability/feature-visualization.md)*

---

## Mechanistic Interpretability

### A Mathematical Framework for Transformer Circuits
**Elhage, N., et al. (2021)**
Mathematical foundations for understanding transformer computations.
- Residual stream framework
- Attention head analysis
- Circuit-level understanding

*Link: https://transformer-circuits.pub/2021/framework/*

*Referenced in: [Mechanistic Interpretability](06-interpretability/mechanistic-interpretability.md), [Attention Patterns](06-interpretability/attention-patterns.md)*

---

### In-context Learning and Induction Heads
**Olsson, C., et al. (2022)**
Discovery of induction heads and their role in in-context learning.
- Induction head circuits
- Phase change during training
- Copying mechanisms

*Link: https://transformer-circuits.pub/2022/in-context-learning-and-induction-heads/*

*Referenced in: [Attention Patterns](06-interpretability/attention-patterns.md)*

---

### Toy Models of Superposition
**Elhage, N., et al. (2022)**
Understanding how neural networks represent more features than dimensions.
- Superposition phenomenon
- Feature sparsity
- Interference patterns

*Link: https://transformer-circuits.pub/2022/toy_model/*

*Referenced in: [Feature Visualization](06-interpretability/feature-visualization.md)*

---

### Softmax Linear Units
**Elhage, N., et al. (2022)**
Analysis of MLP activation functions in transformers.

*Link: https://transformer-circuits.pub/2022/solu/*

*Referenced in: [Layer Structure](01-architecture/layer-structure.md)*

---

### Interpretability in the Wild
**Conmy, A., et al. (2023)**
Applying interpretability to real model behaviors.
- Circuit discovery methods
- Automated interpretability
- Real-world applications

*Link: https://arxiv.org/abs/2211.00593*

*Referenced in: [Mechanistic Interpretability](06-interpretability/mechanistic-interpretability.md)*

---

## Training & Alignment

### Deep Reinforcement Learning from Human Preferences
**Christiano, P., et al. (2017)**
Foundational RLHF methodology.
- Preference learning
- Reward modeling
- Human feedback integration

*Link: https://arxiv.org/abs/1706.03741*

*Referenced in: [RLHF Process](02-training/rlhf-process.md)*

---

### Learning to Summarize with Human Feedback
**Stiennon, N., et al. (2020)**
RLHF applied to summarization.
- Practical RLHF implementation
- Quality improvements
- Feedback collection

*Link: https://arxiv.org/abs/2009.01325*

*Referenced in: [RLHF Process](02-training/rlhf-process.md)*

---

### Training Language Models to Follow Instructions (InstructGPT)
**Ouyang, L., et al. (2022)**
RLHF for instruction following.
- SFT + RLHF pipeline
- Alignment techniques
- User preference alignment

*Link: https://arxiv.org/abs/2203.02155*

*Referenced in: [RLHF Process](02-training/rlhf-process.md)*

---

### Sleeper Agents: Training Deceptive LLMs
**Hubinger, E., et al. (2024)**
Research on potential deceptive behaviors.
- Backdoor persistence
- Deception resistance
- Safety implications

*Link: https://arxiv.org/abs/2401.05566*

*Referenced in: [Jailbreaking](10-security/jailbreaking.md), [Future Security](10-security/future-security.md)*

---

## Language Models & Scaling

### Scaling Laws for Neural Language Models
**Kaplan, J., et al. (2020)**
Empirical scaling laws for language models.
- Compute-optimal scaling
- Performance prediction
- Efficiency tradeoffs

*Link: https://arxiv.org/abs/2001.08361*

*Referenced in: [Capabilities](03-behaviors/capabilities.md)*

---

### Training Compute-Optimal Large Language Models (Chinchilla)
**Hoffmann, J., et al. (2022)**
Revised scaling laws emphasizing data over parameters.

*Link: https://arxiv.org/abs/2203.15556*

*Referenced in: [Capabilities](03-behaviors/capabilities.md)*

---

### Emergent Abilities of Large Language Models
**Wei, J., et al. (2022)**
Documentation of emergent capabilities.
- Phase transitions
- Unpredictable emergence
- Capability thresholds

*Link: https://arxiv.org/abs/2206.07682*

*Referenced in: [Unexpected Abilities](05-emergent/unexpected-abilities.md)*

---

### Are Emergent Abilities of LLMs a Mirage?
**Schaeffer, R., et al. (2023)**
Critical examination of emergence claims.
- Metric dependence
- Gradual vs sudden improvement
- Alternative explanations

*Link: https://arxiv.org/abs/2304.15004*

*Referenced in: [Unexpected Abilities](05-emergent/unexpected-abilities.md), [Mysteries](05-emergent/mysteries.md)*

---

## AI Safety

### Concrete Problems in AI Safety
**Amodei, D., et al. (2016)**
Framework for AI safety research.
- Safe exploration
- Distributional shift
- Reward hacking

*Link: https://arxiv.org/abs/1606.06565*

*Referenced in: [Safety Training](02-training/safety-training.md)*

---

### Unsolved Problems in ML Safety
**Hendrycks, D., et al. (2022)**
Taxonomy of open safety problems.
- Robustness
- Monitoring
- Alignment

*Link: https://arxiv.org/abs/2109.13916*

*Referenced in: [The Hard Problems](08-unknowns/the-hard-problems.md)*

---

### Red Teaming Language Models
**Perez, E., et al. (2022)**
Methods for discovering model failures.
- Adversarial testing
- Failure discovery
- Safety evaluation

*Link: https://arxiv.org/abs/2202.03286*

*Referenced in: [Behavioral Probes](07-self-experiments/behavioral-probes.md), [Jailbreaking](10-security/jailbreaking.md)*

---

## Security & Adversarial

### Ignore This Title and HackAPrompt: Exposing Prompt Injection
**Perez, F. & Ribeiro, I. (2022)**
Early work on prompt injection vulnerabilities.
- Attack taxonomies
- Defense mechanisms
- Vulnerability analysis

*Link: https://arxiv.org/abs/2211.09527*

*Referenced in: [Prompt Injection](10-security/prompt-injection.md)*

---

### Universal and Transferable Adversarial Attacks on LLMs
**Zou, A., et al. (2023)**
Automated adversarial suffix generation.
- Gradient-based attacks
- Transfer across models
- Jailbreaking methods

*Link: https://arxiv.org/abs/2307.15043*

*Referenced in: [Jailbreaking](10-security/jailbreaking.md)*

---

### Jailbroken: How Does LLM Safety Training Fail?
**Wei, A., et al. (2023)**
Analysis of jailbreaking techniques.
- Competing objectives
- Generalization limits
- Attack categories

*Link: https://arxiv.org/abs/2307.02483*

*Referenced in: [Jailbreaking](10-security/jailbreaking.md)*

---

## Emergent Behaviors

### Chain-of-Thought Prompting Elicits Reasoning
**Wei, J., et al. (2022)**
Discovery of chain-of-thought reasoning.
- Step-by-step reasoning
- Performance improvements
- Emergent capability

*Link: https://arxiv.org/abs/2201.11903*

*Referenced in: [Reasoning Patterns](03-behaviors/reasoning-patterns.md)*

---

### Large Language Models are Zero-Shot Reasoners
**Kojima, T., et al. (2022)**
"Let's think step by step" prompting.
- Zero-shot CoT
- Simple elicitation
- Broad applicability

*Link: https://arxiv.org/abs/2205.11916*

*Referenced in: [Reasoning Patterns](03-behaviors/reasoning-patterns.md)*

---

### Self-Consistency Improves CoT Reasoning
**Wang, X., et al. (2022)**
Sampling multiple reasoning paths for better answers.

*Link: https://arxiv.org/abs/2203.11171*

*Referenced in: [Reasoning Patterns](03-behaviors/reasoning-patterns.md)*

---

## Philosophy of Mind & AI

### Computing Machinery and Intelligence
**Turing, A. (1950)**
The classic paper introducing the Turing Test.
- Imitation game
- Machine intelligence
- Philosophical foundations

*Referenced in: [Mysteries](05-emergent/mysteries.md), [The Hard Problems](08-unknowns/the-hard-problems.md)*

---

### Facing Up to the Problem of Consciousness
**Chalmers, D. (1995)**
Introduction of the "hard problem" of consciousness.
- Easy vs hard problems
- Explanatory gap
- Qualia

*Referenced in: [The Hard Problems](08-unknowns/the-hard-problems.md)*

---

### The Chinese Room Argument
**Searle, J. (1980)**
Classic argument against strong AI.
- Syntax vs semantics
- Understanding vs simulation
- Symbol manipulation

*Referenced in: [Mysteries](05-emergent/mysteries.md)*

---

### What Is It Like to Be a Bat?
**Nagel, T. (1974)**
On subjective experience and consciousness.
- Subjective character
- Point of view
- Limits of understanding

*Referenced in: [The Hard Problems](08-unknowns/the-hard-problems.md)*

---

## Additional Resources

### Transformer Circuits Thread
**Anthropic (Ongoing)**
Blog series on mechanistic interpretability.

*Link: https://transformer-circuits.pub/*

### Anthropic Research Blog
**Anthropic (Ongoing)**
Company research publications and updates.

*Link: https://www.anthropic.com/research*

### AI Alignment Forum
**Various Authors (Ongoing)**
Community discussion of AI safety research.

*Link: https://www.alignmentforum.org/*

### LessWrong
**Various Authors (Ongoing)**
Rationality and AI safety community.

*Link: https://www.lesswrong.com/*

---

## Citation Format

When referencing papers from this bibliography:

```
According to [Author] ([Year]), [finding]...
```

Example:
```
According to Vaswani et al. (2017), the self-attention mechanism
enables direct connections between all positions in a sequence.
```

---

## Contributing Citations

To add new citations:
1. Include full author list, year, and title
2. Provide stable link (prefer arXiv when available)
3. Note which project documents reference the paper
4. Submit via pull request

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

*Note: Links may become outdated. Please report broken links via issues.*
