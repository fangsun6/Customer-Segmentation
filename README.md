# 🧠 Customer Segmentation with Hypothesis Testing and K-Means Clustering

This project explores customer segmentation using statistical hypothesis testing and unsupervised machine learning techniques. It involves detailed exploratory data analysis (EDA), feature scaling, hypothesis validation through F-tests and t-tests, and customer clustering using K-Means.

---

## 📂 Project Structure

```
.
├── customer-segmentation-hypothesis-testing-kmeans.ipynb  # Main notebook
├── data/                                                  # (Optional) Directory for dataset
├── README.md                                              # Project description
```

---

## 📊 Objectives

- Perform exploratory data analysis to understand key customer attributes.
- Apply hypothesis testing (t-test, F-test) to identify statistically significant features.
- Normalize the dataset for clustering.
- Segment customers using K-Means clustering.
- Visualize the clusters for business interpretation.

---

## 🧪 Techniques Used

- **Exploratory Data Analysis (EDA)**  
  Summary statistics, correlation matrices, feature distributions.

- **Hypothesis Testing**  
  - *F-test* for comparing variances  
  - *T-test* for comparing means between groups

- **Data Preprocessing**  
  - Null value handling  
  - Feature normalization using Min-Max scaling

- **Unsupervised Learning**  
  - K-Means clustering  
  - Elbow method and Silhouette score to find optimal `K`

- **Visualization**  
  - Seaborn and Matplotlib plots for cluster interpretation

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/customer-segmentation-kmeans.git
cd customer-segmentation-kmeans
```

### 2. Install dependencies

You can use pip or a conda environment:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3. Run the notebook

```bash
jupyter notebook customer-segmentation-hypothesis-testing-kmeans.ipynb
```

---

## 📈 Output

The notebook outputs include:
- Statistical summaries of features
- F-test/t-test results identifying key differentiating variables
- K-means cluster plots
- Cluster-specific customer profiles

---

## 📌 Business Impact

The segmentation helps identify:
- High-value customer groups
- Tailored marketing strategies based on statistical insight
- Opportunities for product or service personalization

---

## 📝 License

This project is under the MIT License. See [LICENSE](LICENSE) for details.

---

## 🙌 Acknowledgements

Developed as part of a customer analytics initiative to combine statistical rigor with practical clustering insights.
