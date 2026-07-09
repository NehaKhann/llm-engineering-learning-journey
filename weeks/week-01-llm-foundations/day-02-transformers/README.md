# Day 2 — Understanding Attention in Transformers

> Week 1 • LLM Foundations

Explore how the Attention mechanism enables Transformers to understand relationships between words by determining which tokens are most relevant when processing a sequence.

Attention is the core innovation behind modern Transformer-based models such as GPT, Llama, Claude, and Qwen.

---

## 📚 Learning Objectives

By the end of this exercise, you'll understand:

- How self-attention works inside a Transformer
- How GPT-2 assigns attention weights to tokens
- The roles of Query, Key, and Value vectors
- Why multiple attention heads are used
- How attention helps models capture context and relationships

---

## 📂 Project Structure

```text
day-02-transformers/
├── README.md
├── attention_analysis.ipynb
└── attention_analysis.py
```

| File | Description |
|--------|-------------|
| `attention_analysis.ipynb` | Interactive notebook for exploring GPT-2 attention patterns. |
| `attention_analysis.py` | Loads GPT-2, extracts attention weights, and analyzes token relationships. |
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
python attention_analysis.py
```

or open

```text
attention_analysis.ipynb
```

inside Jupyter Notebook or VS Code.

---

## 📦 Model Download

On the first run, Hugging Face downloads the pretrained GPT-2 model (approximately **548 MB**).

This only happens once.

Afterward, the model is loaded from the local cache, so future runs start almost instantly.

---

## 🔧 Experiment

Modify these variables in the script to analyze different words.

```python
text = "The firewall blocked the traffic because it was suspicious"

target_word = "it"
```

Try changing both the sentence and the target word to observe how attention patterns change.

Examples:

```python
target_word = "firewall"
target_word = "blocked"
target_word = "traffic"
```

Observe how the model's attention shifts depending on the token being analyzed.

---

## 🧠 Concepts Covered

### Self-Attention

Unlike traditional sequence models, Transformers can directly examine relationships between all tokens in a sequence.

This allows the model to determine which words are most relevant when processing each token.

Example:

```text
The firewall blocked the traffic because it was suspicious
```

When processing:

```text
it
```

the model may pay attention to:

```text
firewall
```

because they are contextually related.

---

### Query, Key, and Value

Every token is transformed into three vectors:

- **Query** → What information am I looking for?
- **Key** → What information does this token contain?
- **Value** → What information should be passed forward?

The model compares Queries against Keys to determine which Values receive attention.

---

### Multi-Head Attention

Transformers use multiple attention heads instead of a single attention pattern.

Different heads can learn different types of relationships simultaneously.

For example:

- One head may focus on grammar
- One may focus on subject-object relationships
- One may capture long-range context

---

### Attention Visualization

This project extracts attention scores from GPT-2 and displays which tokens receive the highest attention from a selected target token.

This provides an intuitive view into how the model processes context.

---

### Layer Depth Matters

Earlier Transformer layers generally learn simpler patterns.

Later layers capture richer semantic relationships and contextual understanding.

This is why attention maps from deeper layers often appear more meaningful.

---

## 💻 Sample Output

```text
Attention from 'Ġit' (position 7) to previous tokens:

The            → 0.6787
Ġfirewall      → 0.0700
Ġblocked       → 0.0568
Ġbecause       → 0.0601
Ġit            → 0.0551
```

---

## 🎯 Key Takeaways

- Self-attention allows Transformers to connect related words.
- Query, Key, and Value vectors drive the attention mechanism.
- Multiple attention heads learn different relationships simultaneously.
- Attention scores help explain how models use context.
- Later Transformer layers generally capture richer contextual information.

---

## 📖 Related Resources

- Day 1 → Tokenization & Next-Token Prediction
- Week 1 Overview → `weeks/week-01-llm-foundations`
- Repository Roadmap → `ROADMAP.md`

---

## ⏭️ Next Lesson

**Day 3 — PyTorch Fundamentals**

Learn the PyTorch concepts that power modern deep learning systems:

- Tensors
- `nn.Module`
- Forward Pass
- Automatic Differentiation (`autograd`)
- Building Simple Neural Networks

These concepts form the foundation for understanding how Transformers are implemented under the hood.