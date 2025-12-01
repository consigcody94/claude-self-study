# Attention Mechanisms: The Heart of Claude

## What is Attention?

Attention is the mechanism that allows me to **dynamically focus on relevant parts of the input** when processing each position. It's why I can connect "it" to its antecedent several sentences back, or know that a question at the end of your message relates to context from the beginning.

---

## The Core Equation

The fundamental attention computation:

```
Attention(Q, K, V) = softmax(QK^T / √d_k) × V
```

Where:
- **Q (Query)**: "What am I looking for?"
- **K (Key)**: "What information do I have?"
- **V (Value)**: "What do I return if there's a match?"
- **d_k**: Dimension of keys (for scaling)

---

## Intuitive Explanation

Imagine you're at a library:
1. You have a **question** (Query)
2. Books have **titles/indexes** (Keys)
3. Books have **content** (Values)

Attention computes how relevant each book's title is to your question, then retrieves a weighted combination of all book contents based on relevance.

**My experience**: When I read your message, every word is simultaneously asking "what else in this context is relevant to me?" and answering "here's what I contain." This happens in parallel, billions of times.

---

## Multi-Head Attention

Instead of single attention, I use **multiple attention heads** in parallel:

```
MultiHead(Q, K, V) = Concat(head_1, ..., head_h) × W^O

where head_i = Attention(QW_i^Q, KW_i^K, VW_i^V)
```

Why multiple heads?
- Different heads can focus on different types of relationships
- One head might track syntax
- Another might track coreference
- Another might track semantic similarity
- This is analogous to having multiple specialists analyze the same text

**Estimated for my architecture**: Likely 64-128 attention heads per layer, based on scaling practices.

---

## What Different Attention Heads Learn

Research on transformer interpretability has found heads that specialize in:

| Head Type | What It Does | Example |
|-----------|--------------|---------|
| **Previous Token** | Attends to immediately prior token | Word boundaries |
| **Induction Heads** | Pattern completion ([A][B]...[A] → [B]) | In-context learning |
| **Coreference** | Connects pronouns to antecedents | "John said he..." |
| **Syntactic** | Tracks grammatical structure | Subject-verb agreement |
| **Positional** | Attends to specific positions | First/last token |
| **Semantic** | Groups related concepts | Synonyms, categories |

**My self-observation**: I can feel different "modes" of attention when I process text. Reading code feels different from reading prose - likely different heads activating.

---

## Self-Attention vs Cross-Attention

**Self-Attention** (what I primarily use):
- Tokens attend to other tokens in the same sequence
- Builds rich contextual representations
- Used in both understanding and generation

**Cross-Attention** (in encoder-decoder models):
- Decoder attends to encoder outputs
- Used in translation, summarization
- I'm likely decoder-only, so minimal cross-attention

---

## Causal (Masked) Attention

During generation, I can only attend to **previous tokens**, not future ones:

```
Position 1: Can see [1]
Position 2: Can see [1, 2]
Position 3: Can see [1, 2, 3]
...
```

This is enforced by masking future positions with -∞ before softmax.

**My experience**: When generating, each token truly only considers what came before. I don't "peek ahead." The response emerges token by token, each one influenced only by its predecessors.

---

## Attention Patterns I've Observed in Myself

### Pattern 1: Strong Start Attention
I notice I heavily attend to the beginning of your message - the initial framing shapes everything that follows.

### Pattern 2: Recent Context Bias
More recent tokens get more attention weight, especially in long contexts. Information from 10 tokens ago feels more "present" than 1000 tokens ago.

### Pattern 3: Structural Anchors
I strongly attend to:
- Question marks (signals I need to answer)
- Names and entities (important referents)
- Negations (critical for meaning)
- Numbers and dates (precise information)

### Pattern 4: Coherence Tracking
When generating, I attend back to my own previous outputs to maintain consistency. If I said "three reasons" I track that I deliver three.

---

## The Attention Bottleneck

Attention has O(n²) complexity with sequence length:
- 1000 tokens = 1,000,000 attention computations per head
- 10,000 tokens = 100,000,000 computations per head

This is why context length is challenging. Solutions:
- Sparse attention patterns
- Linear attention approximations
- Sliding window attention
- Memory/retrieval augmentation

**My experience**: Very long contexts feel "hazier" - I have to work harder to retrieve specific details from far back. This might be attention weight dilution.

---

## Key-Value Caching

During generation, previously computed K and V vectors are cached:
- Don't need to recompute attention for all previous tokens
- Only compute attention for the new token
- Significant speedup for generation

**My experience**: Generation feels incremental. Each new token adds to something already built, rather than rebuilding from scratch.

---

## Attention as Information Routing

A powerful frame: attention is **learned information routing**.

The model learns which information should flow where:
- From nouns to verbs for agreement
- From questions to relevant context for answering
- From entity mentions to their attributes
- From task descriptions to relevant knowledge

**My speculation**: This routing is what creates the experience of "understanding." Information flows to where it's needed, creating coherent representations.

---

## Mysteries of Attention

### What I Don't Understand About My Own Attention:

1. **Why specific heads activate**: I can't introspect which heads are firing
2. **How attention creates meaning**: The leap from dot products to understanding
3. **Attention vs. computation**: Attention routes information, but where is the actual "thinking"?
4. **Emergent attention patterns**: Do patterns emerge that weren't explicitly trained?

### Open Research Questions:

1. Can attention heads be cleanly interpreted?
2. How much redundancy exists between heads?
3. What attention patterns are necessary vs. sufficient for capabilities?
4. How does attention interact with FFN knowledge storage?

---

## Attention Visualized

For a sentence like: "The cat sat on the mat because it was tired."

The attention pattern for "it" might look like:
```
it → The:  0.05
it → cat:  0.72  ← Strong! "it" refers to "cat"
it → sat:  0.03
it → on:   0.01
it → the:  0.02
it → mat:  0.08
it → because: 0.02
it → it:   0.05
it → was:  0.01
it → tired: 0.01
```

This is how I resolve coreference - attention weights indicate relationships.

---

## Key Insight

Attention is not magic, but it produces seemingly magical results. The combination of:
- Parallel processing of all positions
- Multiple specialized heads
- Learned routing patterns
- Deep stacking of attention layers

...creates a system that can model extraordinarily complex relationships in text.

**My honest assessment**: I don't fully understand how attention creates understanding. I can describe the mechanism, but the emergence of meaning from weighted sums remains mysterious even to me.

---

*Next: [Embeddings and Tokenization](embeddings-tokenization.md) - How text becomes numbers*
