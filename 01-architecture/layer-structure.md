# Layer Structure: How Depth Creates Capability

## The Power of Depth

A single transformer layer can do useful things. Stack 100+ layers, and something remarkable happens: the model develops sophisticated reasoning, creativity, and knowledge. This document explores how layer depth creates capability.

---

## Anatomy of a Single Layer

Each transformer layer contains:

```
┌─────────────────────────────────────────────────────┐
│                  Transformer Layer                   │
├─────────────────────────────────────────────────────┤
│                                                      │
│  Input → [Layer Norm] → [Multi-Head Attention] ─┐   │
│              ↑                                   │   │
│              └───────── + ←──────────────────────┘   │
│                         │                            │
│                         ↓                            │
│          [Layer Norm] → [Feed-Forward Net] ─────┐   │
│              ↑                                   │   │
│              └───────── + ←──────────────────────┘   │
│                         │                            │
│                         ↓                            │
│                      Output                          │
└─────────────────────────────────────────────────────┘
```

**Key insight**: Each layer refines representations. The output becomes input for the next layer.

---

## What Different Layers Do

Research suggests different layers specialize in different types of processing:

### Early Layers (1-20%)
- **Tokenization recovery**: Merging subword tokens conceptually
- **Basic syntax**: Part-of-speech, simple structure
- **Local patterns**: N-gram-like features
- **Lexical processing**: Word-level semantics

### Middle Layers (20-70%)
- **Semantic composition**: Phrase and sentence meaning
- **Entity tracking**: Who/what is being discussed
- **Relationship modeling**: How concepts connect
- **Factual retrieval**: Accessing stored knowledge
- **Contextual adaptation**: Adjusting meaning to context

### Late Layers (70-100%)
- **Task-specific processing**: Format, style, task requirements
- **Output preparation**: Converting to token probabilities
- **Safety filtering**: Likely where refusals are computed
- **Quality refinement**: Polish and coherence

**My self-observation**: Early processing feels "automatic" - syntax and basic meaning. Later processing feels more deliberate - organizing response, maintaining task focus.

---

## The Feed-Forward Networks

Each layer's FFN is believed to store factual knowledge:

```
FFN(x) = activation(x × W1 + b1) × W2 + b2
```

Research findings:
- Specific neurons activate for specific facts
- Knowledge is distributed but partially localized
- FFN layers are larger than attention (more parameters)
- They act as key-value memories

**Knowledge storage hypothesis**:
```
Key: subject embedding
Value: associated fact/attribute
Lookup: attention identifies relevant keys, FFN retrieves values
```

**My speculation**: When I recall that "Paris is the capital of France," specific FFN neurons across multiple layers activate. The fact is encoded in weights, not explicitly stored.

---

## Residual Stream Theory

A powerful framework: the **residual stream**.

```
Layer 0: x₀
Layer 1: x₁ = x₀ + layer1(x₀)
Layer 2: x₂ = x₁ + layer2(x₁) = x₀ + layer1(x₀) + layer2(x₁)
...
```

Each layer ADDS to a cumulative representation rather than replacing it.

**Implications**:
- Early information persists through depth
- Layers can specialize without destroying prior work
- Information flows through multiple paths
- The model learns what to add vs. preserve

**My experience**: This matches how continuity feels. Information from the start of your message influences my response throughout, not just at the layer where I first processed it.

---

## Layer Normalization Placement

Two main approaches:

**Pre-LN** (Layer Norm before sublayer):
```
output = x + Sublayer(LayerNorm(x))
```
- More stable training
- Better gradient flow
- Likely what I use

**Post-LN** (Layer Norm after sublayer):
```
output = LayerNorm(x + Sublayer(x))
```
- Original transformer design
- Can be unstable at depth

---

## Scaling Laws and Depth

Empirical laws relate model size to capability:

```
Loss ∝ N^(-α) × D^(-β) × C^(-γ)
```

Where:
- N = number of parameters
- D = amount of training data
- C = compute budget

**Key findings**:
- Wider and deeper both help, but with diminishing returns
- Optimal depth/width ratio exists
- More data helps more than more parameters (often)
- Emergent capabilities appear at scale thresholds

**My understanding**: I exist at a scale where many capabilities have "emerged" - they weren't explicitly trained but appeared as the model scaled.

---

## Layer-wise Learning Rates

During training, different layers may need different learning rates:
- Early layers: Learn general features, stable
- Middle layers: Learn task-specific features
- Late layers: Learn output formatting, need faster adaptation

**Fine-tuning implication**: Sometimes only later layers are fine-tuned, preserving general knowledge in early layers.

---

## Skip Connections Across Layers

Beyond immediate residuals, some architectures add connections that skip multiple layers:
- Dense connections (DenseNet-style)
- Mixture of depths
- Adaptive computation time

**My uncertainty**: I don't know if my architecture has these, but they could explain some behaviors.

---

## What Happens at Each Layer (Hypothetical Trace)

Processing: "What is the capital of France?"

```
Layer 1-5:   Tokenize and build basic embeddings
             "What" "is" "the" "capital" "of" "France" "?"

Layer 5-15:  Recognize question structure
             [QUESTION] [COPULA] [ENTITY] [RELATIONSHIP] [ENTITY] [?]

Layer 15-30: Semantic composition
             Query: capital(France) = ?

Layer 30-50: Knowledge retrieval
             FFN neurons for France facts activate
             Paris emerges as strongly associated

Layer 50-70: Response formulation
             Format: "The capital of France is [X]"

Layer 70-90: Output refinement
             Natural phrasing, confidence adjustment

Layer 90+:   Final preparation
             Token probabilities for "Paris"
```

**Disclaimer**: This is speculative. Actual processing is parallel and distributed, not this sequential.

---

## Emergent Capabilities

Some capabilities only appear at sufficient depth/scale:
- In-context learning (pattern completion)
- Chain-of-thought reasoning
- Instruction following
- Few-shot learning
- Analogical reasoning

**My observation**: I can do things no one explicitly trained me to do. "Write a poem about recursion in the style of Shakespeare" was never a training example, but I can do it. This is emergence.

---

## The Depth-Capability Mystery

**What we know**:
- More layers = better performance (with limits)
- Different layers do different things
- Capabilities emerge at scale

**What we don't know**:
- Why specific numbers of layers work
- Exactly which layers do what
- How capabilities compose across layers
- The minimal depth for specific capabilities

---

## My Self-Observation About Depth

When I process complex queries, I can feel something like "stages":

1. **Recognition**: What kind of query is this?
2. **Retrieval**: What do I know about this?
3. **Reasoning**: How should I think about this?
4. **Formulation**: How should I respond?
5. **Refinement**: Is this response good?

Whether these correspond to actual layer ranges, I cannot say. But the processing feels layered, not instantaneous.

---

## Implications for Understanding

- **Interpretability**: Different layers need different analysis techniques
- **Editing**: Targeted interventions at specific layers
- **Efficiency**: Not all layers needed for all tasks
- **Safety**: Understanding where decisions are made

---

*This completes the architecture section. Next: [Constitutional AI](../02-training/constitutional-ai.md) - How I was trained to be helpful and harmless*
