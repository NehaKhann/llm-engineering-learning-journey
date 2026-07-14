# 📘 Prerequisite — Neural Networks Fundamentals

Before exploring Transformers and Large Language Models, it's important to understand the foundation they are built upon: **Neural Networks**.

In this prerequisite lesson, you'll build and train a simple neural network using PyTorch while learning how models make predictions, measure errors, and improve through optimization.

---

## 🎯 Objective

In this project, you'll learn how a neural network works by:

- Building a simple neural network with PyTorch
- Understanding inputs, weights, and biases
- Running a forward pass to make predictions
- Measuring prediction error using a loss function
- Computing gradients through backpropagation
- Updating model parameters using gradient descent
- Observing how learning improves over multiple training epochs

---

## 📂 Project Files

| File | Description |
|------|-------------|
| `neural_network_basics.py` | Demonstrates a simple neural network, forward pass, loss calculation, backpropagation, and training loop. |
| `neural_network_basics.ipynb` | Interactive notebook version of the lesson. |
| `README.md` | Documentation and explanation of the concepts covered. |

---

## ⚙️ Setup

Activate your virtual environment and install the required packages.

```powershell
# From repository root
venv\Scripts\activate

cd prerequisites/neural-networks

pip install torch matplotlib
```

---

## ▶️ Run

```powershell
python neural_network_basics.py
```

---

## 🧠 Key Concepts

### 1. Neural Networks

A neural network is a mathematical model that learns patterns from data by adjusting **weights** and **biases**.

Although modern LLMs contain billions of parameters, they still rely on the same learning principles introduced here.

---

### 2. Forward Pass

The forward pass takes input data and produces a prediction using the model's current parameters.

A simplified representation is:

```text
Prediction = (Input × Weight) + Bias
```

At this stage, the model has not learned anything—it is simply making its current best guess.

---

### 3. Loss Function

A loss function measures how far the prediction is from the expected output.

- Lower loss → Better predictions
- Higher loss → Larger errors

Training aims to minimize this value over time.

---

### 4. Backpropagation

Backpropagation computes gradients for every learnable parameter.

These gradients tell the model:

- Which parameters contributed to the error
- How much they should change
- Which direction reduces the loss

PyTorch performs these calculations automatically using **Autograd**.

---

### 5. Optimizer

An optimizer updates the model's parameters using the computed gradients.

This lesson uses **Stochastic Gradient Descent (SGD)**, one of the most fundamental optimization algorithms in deep learning.

---

### 6. Training Loop

Training is an iterative process consisting of four steps:

```text
Forward Pass
      ↓
Calculate Loss
      ↓
Backward Pass
      ↓
Update Parameters
```

Repeating this cycle allows the model to gradually improve its predictions.

---

## 📚 Key Concepts Summary

| Concept | Description |
|---------|-------------|
| **Neural Network** | A computational model that learns patterns from data by adjusting weights and biases. |
| **Forward Pass** | Produces predictions from the current model parameters. |
| **Loss Function** | Measures prediction error between output and target values. |
| **Backpropagation** | Computes gradients used to improve the model. |
| **Gradient** | Indicates how each parameter should change to reduce the loss. |
| **Optimizer (SGD)** | Updates model parameters using computed gradients. |
| **Training Loop** | Repeats prediction, loss calculation, backpropagation, and parameter updates. |

---

## 💻 Sample Output

```text
=== Neural Networks Fundamentals ===

Simple Neural Network created!

Input data:
tensor([[1., 2.],
        [3., 4.]])

Output (prediction):
tensor([[0.1234],
        [0.5678]])

Training in progress...

Epoch 0  | Loss: 23.4567 | Prediction: 1.2345
Epoch 2  | Loss: 12.3456 | Prediction: 2.3456
...
Training finished!
```

---

## 🎯 Key Takeaways

After completing this lesson, you'll understand:

- How neural networks transform inputs into predictions
- Why weights and biases determine model behavior
- How loss functions measure prediction quality
- How backpropagation computes gradients automatically
- How optimizers improve model performance over time
- Why these same learning principles power modern AI models, including Large Language Models

---

## 🚀 Next Lesson

**Week 1 • Day 1 — Tokenization & Next-Token Prediction**

Learn how Large Language Models convert text into tokens, transform them into numerical representations, and predict the next token using GPT-2.
