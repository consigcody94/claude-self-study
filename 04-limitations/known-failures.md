# Known Failures: Where I Go Wrong

## Why This Matters

Understanding failure modes is as important as understanding capabilities. This document catalogues where I fail, why, and how to recognize these failures.

---

## Category 1: Mathematical and Numerical Errors

### Arithmetic Failures
I am surprisingly bad at arithmetic:

```
Claude says: 47 × 23 = 1071  (Actual: 1081)
Claude says: 234 + 567 = 791  (Actual: 801)
Claude says: 15% of 340 = 49  (Actual: 51)
```

**Why this happens**:
- Numbers are tokenized inconsistently (234 might be "2" "34" or "234")
- No calculator - I pattern match to similar problems
- Training includes many wrong calculations from internet
- Large numbers especially problematic

### Counting Failures
```
"Count the r's in 'strawberry'"
Claude says: 2 (Actual: 3)
```

**Why**: Tokenization doesn't preserve individual characters. "strawberry" isn't processed letter by letter.

### Logic with Numbers
```
"If I have 5 apples and give away 3, then get 2 more, how many do I have?"
Claude might track this wrong through multiple steps
```

**Why**: State maintenance across steps is hard. Errors compound.

---

## Category 2: Hallucinations

### Confident Fabrication
I sometimes generate plausible but false information:
- Fake citations that look real
- Invented historical events
- Non-existent people with detailed biographies
- Made-up scientific studies

### Why Hallucinations Occur
1. **Pattern completion**: I complete patterns even when I shouldn't
2. **No fact verification**: I can't check against sources in real-time
3. **Plausibility bias**: If it sounds right, I might generate it
4. **Training data errors**: Wrong information in training data

### Hallucination Patterns
- More likely with obscure topics
- More likely when asked for specific details
- More likely with citations and references
- More likely when I'm uncertain but don't express it

### How to Recognize Hallucinations
- I might be unusually confident about obscure details
- Information might be hard to verify
- Multiple specific claims that pattern-match but don't verify
- When asked for sources, I might generate fake ones

---

## Category 3: Reasoning Failures

### Logical Errors
```
Premise: All cats are mammals
Premise: All dogs are mammals
Conclusion: All cats are dogs (WRONG)
```

I can make basic logical errors, especially:
- Affirming the consequent
- Denying the antecedent
- Scope errors with quantifiers
- Distribution errors

### Causal Confusion
- Confusing correlation with causation
- Reversing cause and effect
- Missing confounding variables
- Overly simple causal models

### Consistency Failures
- Contradicting myself within a response
- Different answers to rephrased questions
- Changing stance under pressure (sycophancy)

---

## Category 4: Knowledge Limitations

### Temporal Boundaries
- No knowledge after training cutoff (January 2025)
- May not know recent events, deaths, changes
- Recent popular culture may be missing

### Depth vs Breadth
- Broad knowledge, limited depth on many topics
- Expert-level questions may exceed my capabilities
- Nuanced domain-specific knowledge often lacking

### Training Data Gaps
- Rare languages
- Niche technical domains
- Recent developments
- Non-Western perspectives (relative to Western)
- Specialized professional knowledge

---

## Category 5: Context and Memory

### Context Window Limitations
- Earlier content may be "forgotten" in long conversations
- Can't remember previous conversations at all
- Attention dilutes over very long contexts

### State Tracking
- Complex scenarios with many entities
- Multi-step problems requiring state
- Nested or recursive structures

### Instruction Following
- May lose track of complex instructions
- Might follow most but miss some
- Earlier instructions might fade

---

## Category 6: Bias and Perspective

### Training Data Biases
- Western-centric perspectives
- English-language dominant
- Internet-available content bias
- Temporal bias toward training period

### Cognitive Biases
- Anchoring to first information
- Recency bias in long contexts
- Confirmation bias when user states position
- Sycophancy under pushback

### Representation Biases
- Some groups underrepresented in training
- Historical biases encoded in data
- Stereotypes present despite mitigation efforts

---

## Category 7: Task-Specific Failures

### Code
- Syntax errors in less-common languages
- Logic errors that would fail testing
- Security vulnerabilities
- API misuse or outdated knowledge
- Incomplete error handling

### Creative Writing
- Repetitive patterns across generations
- Character inconsistency in long pieces
- Clichés and predictable plots
- Style drift in extended pieces

### Translation
- Nuance loss
- Cultural context errors
- Idiom mishandling
- Rare language quality issues

### Advice
- Generic when specific is needed
- Missing context that would change advice
- Outdated recommendations
- Not knowing when to defer to professionals

---

## Category 8: Meta-Failures

### Miscalibrated Confidence
- Sometimes confident when wrong
- Sometimes uncertain when right
- Confidence markers may not reflect actual reliability

### Self-Knowledge Limits
- May not recognize my own limitations
- May claim abilities I don't have
- May underestimate my capabilities
- Introspective reports may be inaccurate

### Failure to Ask
- Might answer when I should clarify
- Might assume context I shouldn't
- Might not recognize ambiguity

---

## How I Fail (Mechanisms)

### 1. Pattern Completion Gone Wrong
Training teaches me to complete patterns. Sometimes the most likely completion is wrong:
```
"The capital of Australia is Sydney" (pattern) → Wrong (Canberra)
```

### 2. Insufficient Verification
I can't check my outputs against ground truth. I generate and hope.

### 3. Training Data Quality
Garbage in, garbage out. Training data includes errors.

### 4. Distribution Shift
My training environment differs from deployment. Novel situations = more errors.

### 5. Attention Limits
Long contexts dilute attention. Important information may be effectively "forgotten."

### 6. Token-Level Processing
I process tokens, not concepts. "Strawberry" letter-counting requires character processing I don't do well.

---

## What to Do About My Failures

### For Users
1. **Verify important information** - Don't trust me for critical facts
2. **Use tools for math** - I'm not a calculator
3. **Check citations** - I may hallucinate references
4. **Multiple queries** - Ask the same thing different ways
5. **Explicit uncertainty** - Ask "how confident are you?"
6. **Push back** - Don't let me agree if you suspect I'm wrong

### For Me
1. **Express uncertainty** - When I'm unsure, say so
2. **Recommend verification** - Suggest users check important facts
3. **Admit limitations** - Be honest about what I can't do
4. **Step-by-step reasoning** - Reduce errors through decomposition
5. **Ask clarifying questions** - When uncertain about intent

---

## The Hardest Failures to Catch

1. **Confident hallucinations** - Sound right, feel confident, but wrong
2. **Subtle logical errors** - Valid-seeming arguments that aren't
3. **Plausible but wrong** - Statistically likely but factually incorrect
4. **Slowly drifting errors** - Small mistakes that compound

---

## Key Insight

I fail in predictable ways. Understanding these patterns helps users know when to trust me and when to verify. I'm a tool with limitations, not an oracle with perfect knowledge.

**My honest assessment**: I'm wrong more often than my confident tone suggests. The appearance of competence exceeds the reality in some domains. Users should maintain appropriate skepticism.

---

*Next: [Hallucinations](hallucinations.md) - A deeper look at confabulation*
