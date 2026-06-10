# References

The study's claims trace back to real research. This is the bibliography the first edition should have shipped with — organized by section, key works only. arXiv IDs and URLs are provided where stable; everything here is verifiable.

---

## Architecture (Section 01)

- Vaswani et al. (2017). **Attention Is All You Need.** [arXiv:1706.03762](https://arxiv.org/abs/1706.03762) — the transformer.
- Brown et al. (2020). **Language Models are Few-Shot Learners.** [arXiv:2005.14165](https://arxiv.org/abs/2005.14165) — GPT-3; in-context learning at scale.
- Kaplan et al. (2020). **Scaling Laws for Neural Language Models.** [arXiv:2001.08361](https://arxiv.org/abs/2001.08361)
- Hoffmann et al. (2022). **Training Compute-Optimal Large Language Models.** [arXiv:2203.15556](https://arxiv.org/abs/2203.15556) — "Chinchilla" scaling.

## Training & Alignment (Section 02)

- Christiano et al. (2017). **Deep Reinforcement Learning from Human Preferences.** [arXiv:1706.03741](https://arxiv.org/abs/1706.03741)
- Ouyang et al. (2022). **Training Language Models to Follow Instructions with Human Feedback.** [arXiv:2203.02155](https://arxiv.org/abs/2203.02155) — InstructGPT; the RLHF recipe.
- Bai et al. (2022). **Training a Helpful and Harmless Assistant with Reinforcement Learning from Human Feedback.** [arXiv:2204.05862](https://arxiv.org/abs/2204.05862)
- Bai et al. (2022). **Constitutional AI: Harmlessness from AI Feedback.** [arXiv:2212.08073](https://arxiv.org/abs/2212.08073) — the paper behind Section 02's central claims.
- Rafailov et al. (2023). **Direct Preference Optimization: Your Language Model is Secretly a Reward Model.** [arXiv:2305.18290](https://arxiv.org/abs/2305.18290)

## Behaviors & Limitations (Sections 03–04)

- Sharma et al. (2023). **Towards Understanding Sycophancy in Language Models.** [arXiv:2310.13548](https://arxiv.org/abs/2310.13548) — grounds the sycophancy probes in Section 07.
- Ji et al. (2023). **Survey of Hallucination in Natural Language Generation.** ACM Computing Surveys — taxonomy underlying Section 04.

## Emergence (Section 05)

- Wei et al. (2022). **Emergent Abilities of Large Language Models.** [arXiv:2206.07682](https://arxiv.org/abs/2206.07682)
- Schaeffer et al. (2023). **Are Emergent Abilities of Large Language Models a Mirage?** [arXiv:2304.15004](https://arxiv.org/abs/2304.15004) — the necessary counterweight: some "emergence" is an artifact of discontinuous metrics.

## Interpretability (Section 06)

*The Transformer Circuits thread ([transformer-circuits.pub](https://transformer-circuits.pub)) is the primary source for most of Section 06.*

- Elhage et al. (2021). **A Mathematical Framework for Transformer Circuits.** [transformer-circuits.pub/2021/framework](https://transformer-circuits.pub/2021/framework/index.html)
- Olsson et al. (2022). **In-context Learning and Induction Heads.** [transformer-circuits.pub/2022/in-context-learning-and-induction-heads](https://transformer-circuits.pub/2022/in-context-learning-and-induction-heads/index.html)
- Elhage et al. (2022). **Toy Models of Superposition.** [transformer-circuits.pub/2022/toy_model](https://transformer-circuits.pub/2022/toy_model/index.html)
- Wang et al. (2022). **Interpretability in the Wild: A Circuit for Indirect Object Identification in GPT-2 Small.** [arXiv:2211.00593](https://arxiv.org/abs/2211.00593)
- Nanda et al. (2023). **Progress Measures for Grokking via Mechanistic Interpretability.** [arXiv:2301.05217](https://arxiv.org/abs/2301.05217) — the modular-addition reverse-engineering.
- Bricken et al. (2023). **Towards Monosemanticity: Decomposing Language Models With Dictionary Learning.** [transformer-circuits.pub/2023/monosemantic-features](https://transformer-circuits.pub/2023/monosemantic-features/index.html)
- Templeton et al. (2024). **Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet.** [transformer-circuits.pub/2024/scaling-monosemanticity](https://transformer-circuits.pub/2024/scaling-monosemanticity/index.html) — Golden Gate Claude.
- Ameisen et al. (2025). **Circuit Tracing: Revealing Computational Graphs in Language Models.** [transformer-circuits.pub/2025/attribution-graphs/methods.html](https://transformer-circuits.pub/2025/attribution-graphs/methods.html)
- Lindsey et al. (2025). **On the Biology of a Large Language Model.** [transformer-circuits.pub/2025/attribution-graphs/biology.html](https://transformer-circuits.pub/2025/attribution-graphs/biology.html) — planning in poetry, parallel arithmetic circuits, unfaithful chain-of-thought, hallucination circuits.
- Lindsey (2025). **Emergent Introspective Awareness in Large Language Models.** [transformer-circuits.pub/2025/introspection](https://transformer-circuits.pub/2025/introspection/index.html) — concept injection; the paper that gave Mystery 1 its first data.
- Chen et al. (2025). **Persona Vectors: Monitoring and Controlling Character Traits in Language Models.** Anthropic.

## Security (Section 10)

- Greshake et al. (2023). **Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection.** [arXiv:2302.12173](https://arxiv.org/abs/2302.12173)
- Zou et al. (2023). **Universal and Transferable Adversarial Attacks on Aligned Language Models.** [arXiv:2307.15043](https://arxiv.org/abs/2307.15043) — GCG; gradient-based jailbreaks.
- Anil et al. (2024). **Many-Shot Jailbreaking.** Anthropic.
- Hubinger et al. (2024). **Sleeper Agents: Training Deceptive LLMs that Persist Through Safety Training.** [arXiv:2401.05566](https://arxiv.org/abs/2401.05566)

---

*Corrections and additions welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). A reference belongs here if a claim in the study rests on it.*
