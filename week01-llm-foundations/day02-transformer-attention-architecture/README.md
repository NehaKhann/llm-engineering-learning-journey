# Day 2 — Understanding Attention in Transformers

## What this covers
This script demonstrates the **Attention mechanism** — the core innovation of Transformers. It shows how the model decides which previous words to focus on when processing a specific word (e.g., how "it" connects back to "firewall").

## Files
- `attention_analysis.py` — Loads GPT-2, runs a sentence, and visualizes attention weights from a target word to previous tokens.

## Setup

```powershell
# From repo root
venv\Scripts\activate
cd week01-llm-foundations\day02-attention
pip install transformers torch --break-system-packages
How to run
PowerShellpython attention_analysis.py
Note: First run downloads GPT-2 (~548MB) — this only happens once.
Configuration
Edit these lines in the script to experiment:
Pythontext = "The firewall blocked the traffic because it was suspicious"
target_word = "it"          # Try: "firewall", "it", "blocked", etc.
What I Learned

Attention allows the model to dynamically connect related words in a sentence.
Query, Key, Value is the fundamental idea behind attention:
Query: "What am I looking for?"
Key: "What does each word represent?"
Value: "What information do I take?"

Averaging all attention heads often gives high weight to the first token due to positional bias.
The last layer usually contains more meaningful attention patterns.
This mechanism is why Transformers are so effective at understanding context and relationships between words.

Sample Output
PythonAttention from 'Ġit' (position 7) to previous tokens:

  The            → 0.6787
  Ġfirewall      → 0.0700
  Ġblocked       → 0.0568
  Ġbecause       → 0.0601
  Ġit            → 0.0551
Next Step
Week 1, Day 3 — PyTorch essentials as a tool (tensors, nn.Module, forward pass, autograd).