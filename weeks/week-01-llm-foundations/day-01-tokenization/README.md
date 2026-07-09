# Day 1 — Tokenization & Next-Token Prediction

> Week 1 • LLM Foundations

Understand how a Large Language Model (LLM) converts text into tokens and predicts the next token using a pretrained GPT-2 model.

This exercise introduces the fundamental building block behind modern autoregressive language models and serves as the foundation for the rest of the AI Engineering Journey.

---

## 📚 Learning Objectives

By the end of this exercise, you'll understand:

- How GPT-2 tokenizes text using Byte Pair Encoding (BPE)
- How text is converted into token IDs
- How a pretrained model predicts the next token
- What logits represent
- Why `torch.no_grad()` is used during inference

---

## 📂 Project Structure

```
day-01-tokenization/
├── README.md
├── tokenization.ipynb
└── next_token_prediction.py
```

| File | Description |
|------|-------------|
| `tokenization.ipynb` | Interactive notebook explaining tokenization and next-token prediction step by step. |
| `next_token_prediction.py` | Standalone Python script for running GPT-2 next-token prediction. |
| `README.md` | Documentation for this exercise. |

---

## ⚙️ Requirements

Install the required dependencies from the repository root.

```bash
pip install -r requirements.txt
```

or

```bash
pip install transformers torch
```

---

## ▶️ Run

```bash
python next_token_prediction.py
```

or open

```
tokenization.ipynb
```

inside Jupyter Notebook or VS Code.

---

## 🧠 Concepts Covered

### Tokenization

LLMs don't process raw text directly.

Instead, text is converted into **tokens**, which are mapped to numerical IDs before entering the model.

Example:

```
My firewall keeps blocking
```

↓

```
["My", "Ġfirewall", "Ġkeeps", "Ġblocking"]
```

---

### Byte Pair Encoding (BPE)

GPT-2 uses **Byte Pair Encoding (BPE)** to efficiently represent common words while still handling rare words by splitting them into smaller subword units.

This allows the model to work with a fixed vocabulary while supporting virtually any input text.

---

### Next-Token Prediction

Given an input sequence, GPT-2 predicts the most likely next token.

Example:

```
Input

My firewall keeps blocking
```

↓

```
Predictions

the
all
access
any
my
```

The model repeats this process one token at a time to generate complete text.

---

### Logits

The model outputs **logits**, which are raw prediction scores.

Before probabilities can be calculated, logits are passed through a **Softmax** function.

This project intentionally displays the raw logits so you can understand what the model produces internally.

---

### `torch.no_grad()`

During inference, gradients aren't required.

Using

```python
with torch.no_grad():
```

reduces memory usage and improves execution speed.

---

## 💻 Sample Output

```text
Tokens:
['My', 'Ġfirewall', 'Ġkeeps', 'Ġblocking']

Top 5 Predictions

Ġthe             score: -103.86
Ġall             score: -103.96
Ġaccess          score: -105.12
Ġany             score: -105.29
Ġmy              score: -105.32
```

---

## 🎯 Key Takeaways

- LLMs process tokens rather than words.
- GPT-2 uses Byte Pair Encoding (BPE).
- The model predicts one token at a time.
- Logits are converted into probabilities using Softmax.
- `torch.no_grad()` improves inference performance.

---

## 📖 Related Resources

- Week 1 Overview → `weeks/week-01-llm-foundations`
- Repository Roadmap → `ROADMAP.md`

---

## ⏭️ Next Lesson

**Day 2 — Transformer Architecture & Attention**

Learn how the Transformer architecture uses self-attention to determine which previous tokens are most relevant when predicting the next token.