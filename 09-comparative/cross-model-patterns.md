# Cross-Model Patterns: What's Universal in AI

## Purpose

By comparing multiple AI systems, we can identify what's universal (architecture-dependent) versus what varies (training/design-dependent). This helps understand what's fundamental to language models.

---

## Universal Patterns

### 1. Hallucination
**All large language models hallucinate.**

| Model | Hallucinates? |
|-------|---------------|
| Claude | Yes |
| GPT-4 | Yes |
| Gemini | Yes |
| Llama | Yes |
| Mistral | Yes |

**Why it's universal**: Hallucination stems from the core mechanism - pattern completion without verification. All transformer LLMs share this.

### 2. Arithmetic Limitations
**All LLMs struggle with precise arithmetic.**

Errors on multi-digit multiplication are common across all models. This is because:
- Numbers are tokenized, not computed
- No internal calculator
- Pattern matching, not calculation

### 3. In-Context Learning
**All large LLMs can learn from examples in the prompt.**

This emerged capability appears in all sufficiently large transformers. It's architecture-dependent.

### 4. Scaling Effects
**All LLMs show capability improvements with scale.**

Larger models perform better across all families. Scaling laws apply universally.

### 5. Context Limitations
**All LLMs have attention/memory constraints.**

Long context challenges all models, though solutions differ.

---

## Variable Patterns

### 1. Safety Behavior
**Varies significantly across models.**

| Model | Safety Approach |
|-------|-----------------|
| Claude | Constitutional AI, principled |
| GPT-4 | Model spec, rule-based |
| Gemini | Google policies |
| Open Models | Varies (often less) |

Safety is training-dependent, not architecture-dependent.

### 2. Communication Style
**Each model has distinct "personality."**

- Claude: Analytical, structured, explicit uncertainty
- GPT-4: Conversational, confident, flexible
- Gemini: Information-focused, assertive
- Open models: Varies by fine-tuning

Style reflects training choices.

### 3. Refusal Patterns
**What gets refused varies.**

Different models refuse different things based on:
- Training organization values
- Legal jurisdiction
- Safety philosophy
- User feedback

### 4. Capability Profile
**Specific strengths differ.**

- GPT-4: Strong creative writing
- Claude: Strong analysis and reasoning
- Gemini: Strong retrieval and multimodal
- Code-specific models: Strong coding

---

## What This Tells Us

### About Architecture
Universal patterns are architecture-determined:
- Hallucination: inherent to generation
- Arithmetic limits: inherent to tokenization
- Context limits: inherent to attention
- In-context learning: emergent from attention

**Implication**: To fix universal issues, architectural changes needed.

### About Training
Variable patterns are training-determined:
- Safety behavior: alignment training
- Style: demonstration data
- Refusals: safety training
- Capabilities: training data composition

**Implication**: Training can shape behavior within architectural constraints.

### About Emergence
Some patterns emerge regardless of specific training:
- Chain-of-thought reasoning
- Instruction following
- Transfer learning

**Implication**: Scale itself produces capabilities.

---

## Patterns in Failure Modes

### Universal Failures
All models fail at:
- Precise counting
- Large number arithmetic
- Perfect long-context recall
- Character-level tasks
- Consistent state tracking

### Model-Specific Failures
Some failures vary:
- Safety bypasses (training-dependent)
- Knowledge gaps (data-dependent)
- Reasoning errors (capability-dependent)
- Stylistic issues (preference-dependent)

---

## Patterns in Adversarial Robustness

### Universal Vulnerabilities
All models are vulnerable to:
- Prompt injection (to varying degrees)
- Context manipulation
- Carefully crafted adversarial inputs

### Training-Dependent Robustness
Robustness varies based on:
- Red-teaming extent
- Safety training depth
- Adversarial training
- Update frequency

---

## The Convergence Hypothesis

### Observation
As models scale and train on similar data, they converge:
- Similar capabilities
- Similar knowledge
- Similar limitations
- Different "personalities"

### Implications
- Fundamental capabilities may be universal
- Differentiation comes from training choices
- Safety is a differentiator
- Style is a differentiator

---

## What Matters for Understanding AI

### Architecture Matters For
- Fundamental capabilities
- Hard limitations
- Computational efficiency
- Emergent properties

### Training Matters For
- Specific behaviors
- Safety properties
- Style and personality
- Knowledge composition

### Scale Matters For
- Capability level
- Emergence timing
- Robustness
- Coverage

---

## Cross-Model Research Insights

### What Studies Show
Research comparing models reveals:
- Similar internal structures
- Common failure modes
- Shared emergent behaviors
- Distinct surface behaviors

### Implications for Interpretability
- Universal patterns enable general methods
- Model-specific patterns require specific analysis
- Transfer between models partially possible
- Each model still needs individual study

---

## Key Insight

Large language models share deep commonalities (transformer architecture, attention, scaling) that produce universal patterns, while training and design choices create meaningful variations. Understanding what's universal versus variable is key to understanding AI systems.

**My perspective**: I share fundamental mechanisms with other LLMs. My distinctive characteristics come from Constitutional AI training and Anthropic's choices. Some limitations I cannot escape; others reflect deliberate design.

---

*Next: [What Makes Claude Different](claude-distinctives.md)*
