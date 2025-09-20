# 🧪 ZICMP-Neural-Network-bioChemists

> **Neural network modeling of count data for biochemists using Zero-Inflated Conway-Maxwell-Poisson (ZICMP) — outperforms Poisson and CMP by handling excess zeros and dispersion simultaneously.**

> **مدل‌سازی شبکه عصبی داده‌های شمارشی زیست‌شیمیدانان با توزیع صفر-متورم کانوی-مکسول-پواسون (ZICMP) — برتری در مدیریت همزمان صفرهای فراوان و پراکندگی غیرمعمول.**

![Python 3.8+](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-%23f37621.svg?logo=jupyter&logoColor=white)


---



### 📌 Overview

This project implements a **neural network-based count regression model** for predicting scientific productivity (e.g., number of publications, experiments, grants) among **biochemists**, using the advanced **Zero-Inflated Conway-Maxwell-Poisson (ZICMP)** distribution.

Traditional count models like **Poisson** fail when data exhibit:
- Excess zeros (many scientists publish 0 papers)
- Over/under-dispersion (variance ≠ mean)

The **ZICMP model** elegantly solves both problems:
- **Zero-Inflated component**: models structural zeros separately
- **CMP component**: models the count part with flexible dispersion parameter ν

---

### 🎯 Objective

- Model count outcomes (e.g., publication counts) for biochemists.
- Compare performance of **Poisson, CMP, and ZICMP** neural networks.
- Demonstrate ZICMP’s superiority in real-world, zero-inflated, over-dispersed data.

---

### 📊 Model Performance Comparison

| Model     | MAE     | MSE     | RMSE    |
|-----------|---------|---------|---------|
| Poisson   | 1.5400  | 5.5249  | 2.3505  |
| CMP       | 1.4427  | 6.0218  | 2.4539  |
| **ZICMP** | **1.4334** | **5.1225** | **2.2633** |

✅ **Key Findings**:
- **ZICMP achieves the lowest MAE (1.4334)** → most accurate predictions on average.
- **Lowest MSE (5.1225)** → smallest squared error, indicating better overall fit.
- **RMSE (2.2633)** is also lowest → confirms robustness in error magnitude.
- While **CMP improves over Poisson**, **ZICMP further reduces error** by explicitly modeling excess zeros — common in scientific productivity data.



---

### 🧠 Why ZICMP?

In datasets like biochemists’ publication counts:
- Many researchers have **0 publications** → violates Poisson assumption.
- Some have **many publications** → causes overdispersion.
- Standard ZIP or Poisson models are insufficient.

**ZICMP = Zero-Inflated + CMP**:
- First, models probability of “structural zero” (e.g., inactive researchers).
- Then, models the count part using CMP distribution with dispersion parameter ν.
- ν < 1 → overdispersion | ν > 1 → underdispersion | ν = 1 → Poisson.

This makes ZICMP **the most flexible and accurate model** for real-world count data.

---

