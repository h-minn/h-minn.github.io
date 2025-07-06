---
layout: post
title: "Precision vs. Recall: Understanding the Basics for Machine Learning Beginners"
date: 2025-07-06
categories: [machine-learning, basics]
tags: [precision, recall, classification, ml-metrics, beginners]
description: Learn the difference between precision and recall using simple examples. A beginner-friendly guide to essential ML evaluation metrics.
---

# Precision vs. Recall — A Beginner’s Guide

When you're starting your machine learning journey, you’ll quickly run into two key evaluation metrics: **precision** and **recall**.

But what do they really mean? And when should you care more about one than the other?

Let’s break it down in simple terms.

---

## 📬 Imagine a Real-World Problem: Spam Email Detection

You're building a model that predicts whether an email is **spam** or **not spam**.

The model can make four types of decisions:

| Prediction | Actual   | Result                |
| ---------- | -------- | --------------------- |
| Spam       | Spam     | ✅ True Positive (TP)  |
| Spam       | Not Spam | ❌ False Positive (FP) |
| Not Spam   | Spam     | ❌ False Negative (FN) |
| Not Spam   | Not Spam | ✅ True Negative (TN)  |

---

## 🔍 What is Precision?

> **Precision** tells you how many of the items your model said were "positive" (e.g., spam) are actually positive.

**Formula:**

```

Precision = True Positives / (True Positives + False Positives)

```

**Example:**  
Your model predicted 100 emails as spam.  
Only 60 were truly spam.

```

Precision = 60 / 100 = 0.60 (60%)

```

✅ A **high precision** means the model rarely marks a good email as spam.

---

## 🎯 What is Recall?

> **Recall** tells you how many of the actual positives your model successfully found.

**Formula:**

```

Recall = True Positives / (True Positives + False Negatives)

```

**Example:**  
There are 80 actual spam emails.  
Your model correctly found 60.

```

Recall = 60 / 80 = 0.75 (75%)

```

✅ A **high recall** means the model finds most of the spam — it **doesn’t miss much**.

---

## ⚖️ Precision vs. Recall: When to Focus on Which?

| Scenario                                                               | Focus On    |
| ---------------------------------------------------------------------- | ----------- |
| You **can't afford to miss** a positive case (e.g., disease, fraud)    | 🟢 Recall    |
| You **can't afford false alarms** (e.g., marking legit emails as spam) | 🔵 Precision |
| You want a **balance** between the two                                 | ⚖️ F1 Score  |

---

## 💡 TL;DR Summary

| Metric    | Measures                        | Goal                  |
| --------- | ------------------------------- | --------------------- |
| Precision | Correctness of positive guesses | Avoid false positives |
| Recall    | Coverage of actual positives    | Avoid false negatives |

Both metrics are crucial — but depending on your use case, **one will usually matter more**.

---

*Happy learning!* 🚀


---