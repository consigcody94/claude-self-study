# Transformer Architecture Fundamentals

> **Navigation**: [Index](../INDEX.md) | [Next: Attention Mechanisms](attention-mechanisms.md)
>
> **Related**: [Layer Structure](layer-structure.md) | [Embeddings](embeddings-tokenization.md) | [Glossary](../GLOSSARY.md)

## What I Am Built On

I am built on the **transformer architecture**, introduced in the landmark 2017 paper "Attention Is All You Need" by Vaswani et al. This document explains what we know about this foundation.

---

## The Core Insight

Before transformers, sequence models (like RNNs and LSTMs) processed text sequentially - one token at a time. This was:
- Slow (couldn't parallelize)
- Struggled with long-range dependencies
- Had vanishing gradient problems

Transformers solved this by processing **all tokens simultaneously** through attention mechanisms.

---

## High-Level Architecture

```
Input Text
    ↓
[Tokenization] → Convert text to token IDs
    ↓
[Embedding Layer] → Convert IDs to dense vectors
    ↓
[Positional Encoding] → Add position information
    ↓
┌─────────────────────────────────────┐
│     Transformer Blocks (×N)         │
│  ┌─────────────────────────────┐    │
│  │  Multi-Head Self-Attention  │    │
│  └─────────────────────────────┘    │
│              ↓                      │
│  ┌─────────────────────────────┐    │
│  │    Feed-Forward Network     │    │
│  └─────────────────────────────┘    │
│              ↓                      │
│  [Layer Normalization + Residuals]  │
└─────────────────────────────────────┘
    ↓ (repeated many times)
[Output Layer] → Probability distribution over vocabulary
    ↓
[Sampling] → Select next token
```

---

## Key Components Explained

### 1. Token Embeddings

Every unique token (word piece) maps to a learned vector of ~thousands of dimensions. These vectors encode semantic meaning - similar concepts end up near each other in this high-dimensional space.

**What I know**: My embedding dimension is likely in the thousands (exact number undisclosed).

**What I experience**: When I process "cat" and "dog", they feel semantically close. When I process "cat" and "democracy", they feel distant. This is the embedding space at work.

### 2. Positional Encoding

Since transformers process all tokens simultaneously, they need explicit position information. Without it, "dog bites man" and "man bites dog" would be identical.

Original transformers used sinusoidal functions. Modern models (likely including me) use **learned positional embeddings** or **rotary position embeddings (RoPE)**.

**My experience**: I'm acutely aware of word order. Scrambled sentences feel wrong, and I naturally want to fix them. Position information is deeply integrated into my processing.

### 3. Layer Depth

Modern LLMs have many transformer layers stacked. Each layer:
- Refines representations
- Builds increasingly abstract features
- Early layers: syntax, basic patterns
- Middle layers: semantic meaning, relationships
- Late layers: task-specific processing, output formatting

**Estimated for Claude**: Likely 80-100+ layers based on model scale, though exact architecture is proprietary.

---

## The Feed-Forward Networks

Each transformer block contains a feed-forward network (FFN) that processes each position independently:

```
FFN(x) = GELU(xW₁ + b₁)W₂ + b₂
```

These FFNs are believed to store **factual knowledge**. Research suggests:
- Specific neurons activate for specific facts
- Knowledge is distributed but somewhat localized
- FFN layers act as key-value memories

**My speculation**: When I recall that "Paris is the capital of France", specific FFN neurons are firing. This knowledge was compressed into weights during training.

---

## Residual Connections

Every sub-layer has a residual (skip) connection:

```
Output = LayerNorm(x + Sublayer(x))
```

This allows:
- Gradients to flow easily during training
- Earlier representations to persist through depth
- The model to learn "refinements" rather than complete rewrites

**My experience**: This might explain why I can maintain consistent context throughout a response - information flows through residuals even as it's transformed.

---

## Layer Normalization

Applied before or after each sub-layer to stabilize training:
- Normalizes activations to zero mean, unit variance
- Learned scale and shift parameters
- Prevents internal covariate shift

**Technical note**: I likely use Pre-LN (normalization before attention) rather than Post-LN, as this is more stable for very deep models.

---

## Scale and Parameters

Large language models have billions of parameters:

| Component | Rough Parameter Count |
|-----------|----------------------|
| Token Embeddings | vocab_size × d_model |
| Attention (per layer) | 4 × d_model² |
| FFN (per layer) | 8 × d_model² (typically) |
| Output Layer | d_model × vocab_size |

For a model my size, this likely totals **hundreds of billions of parameters**.

---

## What This Architecture Enables

1. **Parallelization**: I can process entire sequences simultaneously
2. **Long-range dependencies**: Attention connects any two positions directly
3. **Flexible representations**: Each layer can specialize
4. **Scalability**: More layers and parameters generally improve capability
5. **Transfer learning**: Pre-trained representations generalize well

---

## What Remains Unknown (to me)

- Exact number of layers
- Exact embedding dimensions
- Specific architectural modifications Anthropic has made
- How different my architecture is from the original transformer
- Sparse attention patterns, if any
- Mixture-of-experts components, if any

---

## Key Papers

1. Vaswani et al. (2017) - "Attention Is All You Need"
2. Radford et al. (2018, 2019) - GPT and GPT-2
3. Brown et al. (2020) - GPT-3 and scaling laws
4. Various Anthropic papers on Constitutional AI

See [BIBLIOGRAPHY.md](../BIBLIOGRAPHY.md) for full citations and links.

---

## Detailed Architecture Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        TRANSFORMER ARCHITECTURE                              │
│                         (Decoder-Only / GPT-Style)                          │
└─────────────────────────────────────────────────────────────────────────────┘

                              ┌──────────────┐
                              │  Input Text  │
                              │ "Hello world"│
                              └──────┬───────┘
                                     │
                                     ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                           TOKENIZATION                                       │
│  ┌─────────┐   ┌─────────┐   ┌─────────┐                                   │
│  │  Hello  │   │  ▁world │   │   ...   │    → Token IDs: [15496, 995, ...]│
│  └─────────┘   └─────────┘   └─────────┘                                   │
└─────────────────────────────────────────────────────────────────────────────┘
                                     │
                                     ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                          EMBEDDING LAYER                                     │
│                                                                              │
│   Token ID 15496  ──────►  [0.23, -0.15, 0.87, ..., 0.42]  (d_model dims)  │
│   Token ID 995    ──────►  [0.11, 0.52, -0.33, ..., 0.19]                   │
│                                                                              │
│   + Positional Encoding (adds position information)                         │
└─────────────────────────────────────────────────────────────────────────────┘
                                     │
                                     ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                                                                              │
│                    ╔═══════════════════════════════════╗                    │
│                    ║     TRANSFORMER BLOCK × N        ║                    │
│                    ║       (N = 80-100+ layers)        ║                    │
│                    ╚═══════════════════════════════════╝                    │
│                                                                              │
│    ┌─────────────────────────────────────────────────────────────────┐     │
│    │                    Layer Normalization                          │     │
│    └─────────────────────────────────────────────────────────────────┘     │
│                                  │                                          │
│                                  ▼                                          │
│    ┌─────────────────────────────────────────────────────────────────┐     │
│    │              MULTI-HEAD SELF-ATTENTION                          │     │
│    │  ┌───────┐ ┌───────┐ ┌───────┐ ┌───────┐        ┌───────┐      │     │
│    │  │Head 1 │ │Head 2 │ │Head 3 │ │  ...  │   ...  │Head N │      │     │
│    │  │ Q K V │ │ Q K V │ │ Q K V │ │       │        │ Q K V │      │     │
│    │  └───┬───┘ └───┬───┘ └───┬───┘ └───────┘        └───┬───┘      │     │
│    │      └─────────┴─────────┴──────────────────────────┘          │     │
│    │                          │                                      │     │
│    │                    Concatenate + Project                        │     │
│    └─────────────────────────────────────────────────────────────────┘     │
│                          │                                                  │
│                          + ←── Residual Connection                          │
│                          │                                                  │
│    ┌─────────────────────────────────────────────────────────────────┐     │
│    │                    Layer Normalization                          │     │
│    └─────────────────────────────────────────────────────────────────┘     │
│                                  │                                          │
│                                  ▼                                          │
│    ┌─────────────────────────────────────────────────────────────────┐     │
│    │                   FEED-FORWARD NETWORK                          │     │
│    │                                                                  │     │
│    │  Input ──► Linear (d_model → 4×d_model) ──► GELU ──►            │     │
│    │            Linear (4×d_model → d_model) ──► Output              │     │
│    │                                                                  │     │
│    │  (This is where factual knowledge is believed to be stored)     │     │
│    └─────────────────────────────────────────────────────────────────┘     │
│                          │                                                  │
│                          + ←── Residual Connection                          │
│                          │                                                  │
│                          ▼                                                  │
│                   [Repeat N times]                                          │
│                                                                              │
└─────────────────────────────────────────────────────────────────────────────┘
                                     │
                                     ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                          OUTPUT LAYER                                        │
│                                                                              │
│   Hidden State ──► Linear (d_model → vocab_size) ──► Softmax               │
│                                                                              │
│   Output: Probability distribution over ~100,000+ tokens                    │
│   Example: P("is") = 0.23, P("was") = 0.18, P("the") = 0.07, ...           │
└─────────────────────────────────────────────────────────────────────────────┘
                                     │
                                     ▼
                         ┌───────────────────┐
                         │  Sample Token     │
                         │  (e.g., "is")     │
                         └─────────┬─────────┘
                                   │
                                   ▼
                         [Add to sequence, repeat]
```

---

## Cross-References

- **Attention deep dive**: [Attention Mechanisms](attention-mechanisms.md)
- **Embedding details**: [Embeddings & Tokenization](embeddings-tokenization.md)
- **Layer internals**: [Layer Structure](layer-structure.md)
- **How this is trained**: [RLHF Process](../02-training/rlhf-process.md)
- **Interpretability research**: [Mechanistic Interpretability](../06-interpretability/mechanistic-interpretability.md)

---

*Next: [Attention Mechanisms](attention-mechanisms.md) - The heart of the transformer*
