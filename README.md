
# 🧠 Customer Segmentation Using Hypothesis Testing and K-Means Clustering

This project explores customer segmentation by combining **statistical rigor** (via hypothesis testing) and **unsupervised learning** (K-Means clustering). It walks through the data analysis process from EDA to model interpretation, and reflects on analytical decisions, challenges, and business implications.

---

## 🎯 Project Motivation

Customer segmentation is foundational in marketing analytics. Businesses need to understand their diverse customer base to:
- Personalize offers
- Allocate advertising spend
- Improve customer retention

In this project, my objective was not only to segment customers into behaviorally meaningful groups, but to **support these segments with statistical evidence**, not just clustering visuals.

---

## 🧠 My Thought Process

### Phase 1: Understand the Business and Data
Before touching any code, I asked:
- What does the business need from segmentation?
- What attributes (e.g., spending score, income) can be meaningfully grouped?

I carefully inspected the dataset to confirm it contained demographic and behavioral signals strong enough to warrant clustering.

### Phase 2: Explore Patterns and Form Hypotheses
I didn't want to blindly apply clustering. I started with EDA:
- Distribution plots of **age**, **income**, and **spending score**
- Gender-based comparisons
- Correlation heatmaps

I then posed several questions:
- Do men and women spend differently?
- Is spending score related to income or age?
- Can I validate these patterns statistically?

---

## 🧪 Hypothesis Testing Strategy

I conducted t-tests and ANOVA to **quantify** observed patterns:
- Is the difference in spending score between genders significant?
- Does income vary across age bins?

Instead of assuming clusters based on intuition, I used tests to:
✅ Confirm real behavioral differences  
✅ Reduce the risk of segmenting on noise

---

## ⚙️ Clustering Approach

I chose **K-Means** for its simplicity and interpretability.

### Difficulties Encountered:
| Challenge | How I Dealt With It |
|----------|----------------------|
| **Choosing the right K** | I applied both the **Elbow Method** and **Silhouette Score** to select optimal clusters |
| **Different scales in features** | Standardized features with `StandardScaler` before clustering |
| **Spherical bias of K-Means** | Checked cluster shape with 2D scatter plots to validate reasonableness |
| **Understanding cluster meaning** | Used group-wise aggregations and visualizations to label cluster behavior |
| **Gender imbalance** | Explored results stratified by gender to ensure fair insights |

---

## 🔍 Insights and Interpretation

After clustering:
- One group had **high income but low spending score** — likely price-sensitive or unengaged users.
- Another group showed **low income but high spending** — possibly young and impulsive customers.
- Some clusters overlapped, revealing nuance that linear segmentation might miss.

💡 I cross-validated these patterns using the original hypothesis tests.

---

## 📊 Visualizations Used

- Pair plots and scatter plots for raw and cluster-labeled data
- Distribution plots to explore feature spread
- Heatmaps for correlation and test results
- Elbow curve and silhouette analysis

---

## 📁 Structure

```
.
├── customer-segmentation-hypothesis-testing-kmeans.ipynb  # Full analysis notebook
├── README.md                                               # Comprehensive project overview
```

---

## ▶️ Run Instructions

Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn
```

Open the notebook and run all cells in sequence.

---

## 💭 Reflections and Takeaways

This project deepened my appreciation for **complementing machine learning with statistics**:

- Unsupervised learning gives structure, but **hypothesis testing gives confidence**.
- Visuals are helpful, but **statistical tests reveal what matters**.
- Scaling and preprocessing matter greatly in clustering.

If deployed in a real company, this type of analysis could:
- Inform segmented email campaigns
- Personalize product recommendations
- Identify high-risk churn segments

---

## 📜 License

MIT License — use freely for learning or adaptation.
