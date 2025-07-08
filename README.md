
# 👥 Customer Segmentation Using K-Means Clustering & Hypothesis Testing

This project applies unsupervised machine learning and statistical hypothesis testing to perform **customer segmentation** using transactional and demographic data. The goal is to extract meaningful customer clusters that support tailored business decisions and marketing strategies.

---

## 🎯 Project Motivation

Customer segmentation allows businesses to:
- Understand user behavior
- Optimize product targeting and pricing
- Prioritize high-value clients
- Design personalized marketing campaigns

In this notebook, we use **EDA**, **hypothesis testing**, and **K-Means clustering** to explore patterns in the dataset and group customers into actionable cohorts.

---

## 📁 Project Structure

```
.
├── customer-segmentation-hypothesis-testing-kmeans.ipynb
├── README.md
└── dataset.csv
```

---

## 🧠 Methodology & Thought Process

### 1. Domain Understanding
Before any modeling, we analyzed:
- Demographic structure: age, gender, income
- Spending behavior: annual expenditure, product affinity
- Lifestyle indicators: membership tenure, segmentation markers

This helped form hypotheses about likely clusters (e.g., young high-spenders vs. older frugal shoppers).

---

### 2. Exploratory Data Analysis (EDA)
Used `pandas`, `seaborn`, and `matplotlib` to:
- Visualize distributions (age, income, spending)
- Identify correlations (e.g., age vs. annual spend)
- Detect outliers and missing values

### Key Insights:
- Spending scores were not linearly related to income
- Some age groups showed bimodal purchase behavior
- Gender differences in spending were statistically significant

---

### 3. Statistical Hypothesis Testing

**Tests Used**:
| Test | Purpose |
|------|---------|
| t-test / Mann-Whitney | Compare spending between genders or age groups |
| ANOVA | Test if multiple age groups have different average income |
| Chi-Square | Test independence between categorical variables |

### Decisions Made:
- Converted skewed variables to log scale before testing
- Used Welch’s t-test where variance was unequal
- Validated assumptions with Shapiro-Wilk and Levene’s tests

---

### 4. Clustering with K-Means

Why K-Means?
- Simple and interpretable
- Performs well when clusters are spherical in feature space
- Easy to tune via Elbow Method

**Steps**:
1. Feature selection: chose `Annual Income`, `Spending Score`, `Age`
2. Feature scaling with `StandardScaler`
3. Used `Elbow Method` and `Silhouette Score` to choose `k=5`
4. Fit `KMeans` and visualized clusters in 2D/3D

---

## 🔍 Challenge-Resolution Table

| Challenge | Resolution |
|----------|------------|
| Choosing optimal number of clusters | Used Elbow plot and silhouette analysis |
| Outliers affecting centroids | Used robust scaler, visually identified and optionally removed |
| Features with different scales | Applied `StandardScaler` before clustering |
| Cluster overlap | Tried PCA for dimension reduction; found raw features better preserved interpretability |
| Categorical variables | Encoded when necessary, excluded when inconsistent |

---

## 📊 Cluster Interpretation

| Cluster | Traits |
|--------|--------|
| C1 | High income, low spending — potential for luxury upsell |
| C2 | Young and high-spending — active buyers |
| C3 | Elderly with moderate income — conservative shoppers |
| C4 | Low income and low spend — price sensitive |
| C5 | High income, high spend — loyalty focus group |

---

## 🔁 Next Steps

- Apply DBSCAN and Agglomerative Clustering to compare cluster quality
- Use UMAP or t-SNE for nonlinear visualization
- Include more lifestyle and behavior variables
- Build personas based on cluster centroids
- Feed segmented data into supervised models for churn prediction

---

## ▶️ How to Run

1. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

2. Launch the notebook:
```bash
jupyter notebook customer-segmentation-hypothesis-testing-kmeans.ipynb
```

---

## 📜 License

MIT License — for research, analysis, and educational reuse.



---

## 🧠 Deep Thinking Flow: Why These Methods, and What We Learned

### 🔍 Why Use K-Means Instead of Other Clustering Algorithms?

**Context**: We needed a model that was fast, interpretable, and suitable for numeric behavioral features like income and spending.

**Alternatives Considered**:
- **DBSCAN**: good for noise detection, but struggles with variable-density clusters
- **Agglomerative Clustering**: hierarchical but slow on large datasets and sensitive to distance metric
- **Gaussian Mixture Models (GMM)**: probabilistic but less intuitive for business explanation
- **Spectral Clustering**: computationally expensive and hard to explain

**Why K-Means?**:
- Excellent performance on dense, rounded clusters
- Centroids are easy to interpret for persona generation
- Easily tunable via inertia or silhouette scores
- Fast and scalable, which is valuable for larger datasets

**How we validated it**:
- Elbow curve: Looked for point where inertia stopped dropping steeply
- Silhouette score: Quantified how well points fit within their cluster
- Cluster separation visualization using 2D plots and PCA (optional)

---

### 🧪 Why Include Hypothesis Testing Before Clustering?

Often, data scientists jump straight into clustering — but we asked: **Do certain features differ meaningfully across demographic groups?**

**Hypothesis Testing Let Us**:
- Validate assumptions (e.g., males spend more? not always)
- Justify which variables to cluster on — confirmed that age, income, and spending score had statistically significant relationships
- Enhance EDA: Visuals plus p-values tell a more complete story

This statistical validation made our clustering decisions **data-driven, not intuition-based**.

---

### ⚠️ Dealing With Real-World Data Challenges

| Problem | Why it Matters | Solution |
|--------|----------------|----------|
| Skewed features (income, spending) | K-Means uses Euclidean distance, which is sensitive to magnitude | Applied `StandardScaler` |
| Non-normal distributions | Affects t-test validity | Used Mann-Whitney U as non-parametric alternative |
| Multiple features measured on different scales | Clustering will be biased toward larger-scale variables | Performed feature scaling before clustering |
| Categorical variables | K-Means can't use them natively | Excluded from clustering but included in post-hoc analysis |
| Outliers | Can distort centroids | Visual inspection + optional outlier removal using IQR |

---

### 🎯 Interpretability First

Unlike black-box clustering pipelines, we prioritized **explainable cluster formation**. Each cluster centroid was used to construct:

- Customer personas: e.g., “Cautious Conservative”, “Luxury Enthusiast”
- Marketing targets: High-value clients (C5) vs. price-sensitive (C4)
- Product bundles: E.g., C2 could be offered trend-based subscriptions

Clarity in explanation → better business buy-in.

---

### 💡 Reflection: What Makes a “Good” Cluster?

We defined good clusters based on:
- **Compactness**: Members are similar within the group
- **Separation**: Clusters are distinct from each other
- **Business actionability**: Insights that can drive strategy
- **Statistical support**: Evidence of meaningful feature variance

K-Means gave us control and flexibility to tune for all four.

---

## 🧭 Future Explorations

To evolve this project:
- Add **dimensionality reduction** (UMAP/t-SNE) to improve cluster visualization
- Use **autoencoders** for learned representations before clustering
- Feed clusters into supervised models to predict outcomes like **churn** or **LTV**
- Compare with **non-Euclidean methods** like HDBSCAN for robustness

---

## ✍️ Final Takeaways

- Hypothesis testing grounds your clustering in statistical reality
- K-Means works well with scaled, numerical features if assumptions are checked
- Segmentation is not just clustering — it’s translating data into **actionable personas**
- Explainability is more important than raw algorithmic complexity

