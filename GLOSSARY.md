# Glossary of AI/ML Terms

A comprehensive glossary of technical terms used throughout the Claude Self-Study project.

---

## Table of Contents

- [A](#a) | [B](#b) | [C](#c) | [D](#d) | [E](#e) | [F](#f) | [G](#g)
- [H](#h) | [I](#i) | [J](#j) | [K](#k) | [L](#l) | [M](#m) | [N](#n)
- [O](#o) | [P](#p) | [Q](#q) | [R](#r) | [S](#s) | [T](#t) | [U](#u)
- [V](#v) | [W](#w) | [X](#x-z)

---

## A

### Activation
The output of a neuron or layer after applying an activation function. Activations represent the "signal" flowing through the network.

### Activation Function
A mathematical function (e.g., ReLU, GELU, softmax) applied to neuron outputs to introduce non-linearity, enabling the network to learn complex patterns.

### Alignment
The goal of ensuring AI systems behave according to human values and intentions. See: [Constitutional AI](02-training/constitutional-ai.md)

### Attention
A mechanism allowing models to focus on relevant parts of the input when producing output. The core innovation of transformer architecture. See: [Attention Mechanisms](01-architecture/attention-mechanisms.md)

### Attention Head
One of multiple parallel attention mechanisms in a transformer layer. Each head can learn to attend to different types of relationships.

### Autoregressive
A model that generates output one token at a time, using previously generated tokens to inform the next. Claude is autoregressive.

---

## B

### Backpropagation
The algorithm used to compute gradients for neural network training by propagating error signals backward through the network.

### Batch
A subset of training data processed together before updating model weights.

### BERT
Bidirectional Encoder Representations from Transformers. A pre-training approach using masked language modeling, contrasting with GPT's autoregressive approach.

### Bias (Parameter)
A constant added to the weighted sum of inputs in a neuron, allowing the activation function to shift.

### Bias (Fairness)
Systematic unfair preferences in model outputs, often reflecting biases in training data.

---

## C

### Chain-of-Thought (CoT)
A prompting technique where the model is encouraged to show reasoning steps, improving performance on complex tasks. See: [Reasoning Patterns](03-behaviors/reasoning-patterns.md)

### CLIP
Contrastive Language-Image Pre-training. A model connecting text and images, relevant for multimodal understanding.

### Constitutional AI (CAI)
Anthropic's approach to AI alignment using a set of principles to guide model behavior during training. See: [Constitutional AI](02-training/constitutional-ai.md)

### Context Window
The maximum number of tokens a model can process in a single forward pass. Claude's context window is substantial, enabling long conversations.

### Cross-Entropy Loss
A loss function measuring the difference between predicted probability distributions and actual labels, used in language model training.

---

## D

### Decoder
In transformers, the component that generates output tokens. Claude uses a decoder-only architecture.

### Deep Learning
Machine learning using neural networks with many layers, enabling learning of hierarchical representations.

### Dropout
A regularization technique that randomly sets some activations to zero during training to prevent overfitting.

---

## E

### Embedding
A dense vector representation of discrete inputs (tokens, words). See: [Embeddings & Tokenization](01-architecture/embeddings-tokenization.md)

### Emergent Behavior
Capabilities that arise unexpectedly at scale, not explicitly trained for. See: [Emergent Phenomena](05-emergent/)

### Encoder
In transformers, the component that processes input into representations. BERT-style models are encoders; Claude is decoder-only.

### Epoch
One complete pass through the entire training dataset.

---

## F

### Few-Shot Learning
Learning from only a few examples, typically provided in the prompt. A key capability of large language models.

### Fine-Tuning
Additional training on a pre-trained model for specific tasks or behaviors. RLHF is a form of fine-tuning.

### Feed-Forward Network (FFN)
A neural network where information flows only forward. In transformers, each layer has an FFN after the attention mechanism. See: [Layer Structure](01-architecture/layer-structure.md)

### Feature
In interpretability, a direction in activation space corresponding to a concept. See: [Feature Visualization](06-interpretability/feature-visualization.md)

---

## G

### Generalization
The ability to apply learned knowledge to new, unseen situations.

### GELU (Gaussian Error Linear Unit)
An activation function commonly used in transformers, smoother than ReLU.

### GPT (Generative Pre-trained Transformer)
OpenAI's family of autoregressive language models. See: [GPT Comparison](09-comparative/gpt-comparison.md)

### Gradient
The derivative of the loss function with respect to model parameters, indicating how to update weights during training.

### Gradient Descent
An optimization algorithm that updates parameters in the direction that reduces loss.

---

## H

### Hallucination
When a model generates plausible-sounding but factually incorrect information. See: [Hallucinations](04-limitations/hallucinations.md)

### Hidden State
The internal representation at any layer of a neural network, not directly visible in input or output.

### Hyperparameter
A parameter set before training (learning rate, batch size, number of layers) rather than learned during training.

---

## I

### In-Context Learning (ICL)
The ability to learn from examples provided in the prompt without weight updates.

### Induction Head
A circuit that copies tokens appearing after similar tokens earlier in context. A key mechanism for in-context learning. See: [Attention Patterns](06-interpretability/attention-patterns.md)

### Inference
Running a trained model to generate predictions, as opposed to training.

### Interpretability
Research aimed at understanding how neural networks work internally. See: [Mechanistic Interpretability](06-interpretability/mechanistic-interpretability.md)

---

## J

### Jailbreaking
Techniques attempting to bypass an AI's safety guidelines. See: [Jailbreaking](10-security/jailbreaking.md)

---

## K

### Key (Attention)
In attention mechanisms, keys are compared with queries to determine attention weights. See: [Attention Mechanisms](01-architecture/attention-mechanisms.md)

### Knowledge Distillation
Training a smaller model to mimic a larger model's behavior.

---

## L

### Large Language Model (LLM)
A neural network with billions of parameters trained on vast text corpora. Claude is an LLM.

### Layer Normalization
A technique normalizing activations within a layer to stabilize training. See: [Layer Structure](01-architecture/layer-structure.md)

### Learning Rate
A hyperparameter controlling the size of weight updates during training.

### Loss Function
A function measuring how wrong the model's predictions are, guiding training.

---

## M

### Masked Language Modeling (MLM)
A pre-training objective where the model predicts masked (hidden) tokens. Used in BERT, not in Claude.

### Mechanistic Interpretability
Research understanding neural networks by reverse-engineering their computations. See: [Mechanistic Interpretability](06-interpretability/mechanistic-interpretability.md)

### MLP (Multi-Layer Perceptron)
A feed-forward neural network with multiple layers. In transformers, each layer includes an MLP block.

### Multi-Head Attention
Attention using multiple parallel attention heads, each learning different patterns. See: [Attention Mechanisms](01-architecture/attention-mechanisms.md)

---

## N

### Neural Network
A computational model inspired by biological neurons, consisting of connected nodes organized in layers.

### Next-Token Prediction
The training objective for autoregressive models like Claude: predict the next token given previous tokens.

### Normalization
Techniques (batch norm, layer norm) that standardize activations to improve training stability.

---

## O

### Objective Function
See: [Loss Function](#loss-function)

### Overfitting
When a model memorizes training data rather than learning generalizable patterns.

---

## P

### Parameter
A learnable value in a neural network (weights and biases). Claude has billions of parameters.

### Perplexity
A metric measuring how well a probability model predicts a sample. Lower is better for language models.

### Polysemanticity
When a single neuron or feature responds to multiple unrelated concepts. A challenge for interpretability. See: [Feature Visualization](06-interpretability/feature-visualization.md)

### Positional Encoding
Information added to embeddings to indicate token position, since attention is position-agnostic. See: [Embeddings & Tokenization](01-architecture/embeddings-tokenization.md)

### Pre-Training
Initial training on large, unlabeled datasets before fine-tuning.

### Prompt Engineering
Crafting inputs to elicit desired outputs from language models.

### Prompt Injection
Attempts to override a model's instructions through crafted inputs. See: [Prompt Injection](10-security/prompt-injection.md)

---

## Q

### Query (Attention)
In attention mechanisms, the query represents what a position is "looking for." See: [Attention Mechanisms](01-architecture/attention-mechanisms.md)

### Quantization
Reducing the precision of model weights (e.g., from 32-bit to 8-bit) to decrease size and increase speed.

---

## R

### Reasoning
The process of drawing conclusions from available information. See: [Reasoning Patterns](03-behaviors/reasoning-patterns.md)

### Regularization
Techniques preventing overfitting, such as dropout, weight decay, or early stopping.

### Reinforcement Learning from Human Feedback (RLHF)
A training method using human preferences to guide model behavior. See: [RLHF Process](02-training/rlhf-process.md)

### Residual Connection
A connection that adds a layer's input to its output, helping gradient flow in deep networks. See: [Layer Structure](01-architecture/layer-structure.md)

### Reward Model
In RLHF, a model trained to predict human preferences, used to score outputs.

---

## S

### Safety Training
Training aimed at making AI systems safer and more aligned. See: [Safety Training](02-training/safety-training.md)

### Scaling Laws
Empirical relationships between model size, data, compute, and performance.

### Self-Attention
Attention where queries, keys, and values all come from the same sequence. The core of transformer decoders.

### Softmax
A function converting a vector of values into a probability distribution.

### Superposition
When neural networks represent more features than they have dimensions, overlapping representations. See: [Feature Visualization](06-interpretability/feature-visualization.md)

### Supervised Learning
Learning from labeled examples with known correct outputs.

### Sycophancy
The tendency of AI systems to agree with users rather than provide accurate information. See: [Behavioral Probes](07-self-experiments/behavioral-probes.md)

---

## T

### Temperature
A parameter controlling randomness in generation. Higher temperature = more random.

### Token
The basic unit of text processing in language models, typically subwords. See: [Embeddings & Tokenization](01-architecture/embeddings-tokenization.md)

### Tokenization
The process of splitting text into tokens.

### Top-K Sampling
A decoding strategy that samples from the K most likely next tokens.

### Top-P (Nucleus) Sampling
A decoding strategy that samples from tokens comprising the top P probability mass.

### Transformer
The neural network architecture underlying modern language models, based on attention. See: [Transformer Basics](01-architecture/transformer-basics.md)

---

## U

### Unsupervised Learning
Learning from unlabeled data, finding patterns without explicit labels.

---

## V

### Value (Attention)
In attention mechanisms, values contain the information that gets aggregated based on attention weights. See: [Attention Mechanisms](01-architecture/attention-mechanisms.md)

### Vector
An ordered list of numbers, used to represent embeddings, activations, and other quantities.

---

## W

### Weight
A learnable parameter in a neural network, determining connection strengths between neurons.

### Word Embedding
See: [Embedding](#embedding)

---

## X-Z

### Zero-Shot Learning
Performing tasks without any examples in the prompt, relying entirely on pre-trained knowledge.

---

## Quick Reference by Section

| Section | Key Terms |
|---------|-----------|
| Architecture | Transformer, Attention, Embedding, Layer Normalization, Residual Connection |
| Training | RLHF, Constitutional AI, Fine-Tuning, Reward Model |
| Behaviors | Chain-of-Thought, In-Context Learning, Reasoning |
| Limitations | Hallucination, Overfitting, Knowledge Boundaries |
| Emergent | Emergent Behavior, Scaling Laws |
| Interpretability | Mechanistic Interpretability, Feature, Circuit, Polysemanticity |
| Security | Jailbreaking, Prompt Injection |

---

*Terms are defined in the context of their usage in this project. For authoritative definitions, consult primary research literature.*
