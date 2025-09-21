# AmPy - Antibiotic Resistance Prediction

**Rapidly predict antibiotic resistance from bacterial genomes, empowering physicians to choose effective treatments in seconds.**

## 🌐 Live Demo

**Try AmPy now:** [https://genome-based-antibiotic-recommendation.streamlit.app/](https://genome-based-antibiotic-recommendation.streamlit.app/)

*Upload bacterial genome data and get instant antibiotic resistance predictions with confidence scores and explanations.*

## 🧬 About the Project

### Inspiration

Antibiotic resistance is a growing global health threat, making rapid and accurate treatment decisions critical for patient outcomes. Traditional lab-based resistance testing is slow and resource-intensive. We were inspired to build a tool that leverages bacterial genome data and machine learning to instantly predict resistance profiles for multiple antibiotics, empowering clinicians to make informed choices in real time.

## 🎓 What We Learned

- **Bioinformatics:** We learned how to process and represent genome sequences using k-mer extraction, a technique that breaks DNA into short substrings for feature engineering.
- **Machine Learning:** We explored multi-label classification, model evaluation (AUC, AUPRC), and feature importance for interpretability.
- **Data Engineering:** We tackled large-scale data streaming, merging genome and phenotype data, and handling missing/imbalanced labels.
- **Model Deployment:** We experimented with user interfaces (Gradio) for real-world accessibility and deployed the final application using Streamlit.

## 🛠️ How We Built It

### Data Preparation
- Streamed bacterial genome data and resistance labels
- Sampled genomes and merged them for analysis
- Handled missing and imbalanced data

### Feature Extraction
- Used k-mer extraction to convert DNA sequences into features
- Applied TF-IDF vectorization to make sequences machine-readable
- Optimized feature selection for computational efficiency

### Model Training
- Trained XGBoost classifiers for each antibiotic
- Used stratified splits for robust validation
- Evaluated using AUC and AUPRC metrics

### Evaluation & Interpretability
- Summarized model performance across antibiotics
- Identified top-performing prediction targets
- Extracted most predictive k-mers for clinical insights

### Prediction & User Interface
- Built end-to-end prediction pipeline
- Deployed user-friendly web interface using Streamlit
- Included confidence scores and explanations for clinical decision support

## 🚧 Challenges We Overcame

- **Data Imbalance:** Many antibiotics had few resistant or susceptible samples, requiring careful selection of trainable targets
- **Computational Load:** Genome data is massive; we optimized by sampling, limiting k-mer features, and using efficient vectorization
- **Interpretability:** Making predictions explainable for clinicians was key, so we included feature importance and confidence scores
- **Integration:** Merging streaming genome data with static label files and handling missing data was non-trivial
- **Deployment:** Optimizing model performance and user experience for web deployment while maintaining prediction accuracy

## 📊 Math & Algorithms

### K-mer Extraction
For a DNA sequence $S$, k-mers are extracted as:
$$\text{k-mers} = \{ S_i = S[i:i+k] \mid 0 \leq i \leq |S| - k \}$$

### TF-IDF Vectorization
Term frequency-inverse document frequency:
$$\text{TF-IDF}(t, d) = \text{tf}(t, d) \times \log\left(\frac{N}{\text{df}(t)}\right)$$

Where:
- $t$ = k-mer term
- $d$ = genome document
- $N$ = total number of genomes
- $\text{df}(t)$ = number of genomes containing k-mer $t$

### Model Evaluation
Area Under the Curve (AUC):
$$AUC = \int_0^1 TPR(FPR^{-1}(x)) dx$$

Where $TPR$ is True Positive Rate and $FPR$ is False Positive Rate.

## 🚀 Getting Started

### Try the Live Application
Visit our deployed application: [https://genome-based-antibiotic-recommendation.streamlit.app/](https://genome-based-antibiotic-recommendation.streamlit.app/)

### Local Development

#### Prerequisites
- Python 3.8+
- Required packages (install via `pip install -r requirements.txt`):
  - `xgboost`
  - `scikit-learn`
  - `pandas`
  - `numpy`
  - `streamlit`
  - `biopython`

#### Installation

```bash
git clone https://github.com/yourusername/ampy.git
cd ampy
pip install -r requirements.txt
```

#### Run Locally

```bash
streamlit run app.py
```

## 🌍 Impact & Future Applications

AmPy represents a significant step forward in precision medicine for infectious diseases. By providing rapid, accurate resistance predictions, we can help:

- **Reduce treatment delays** from days to seconds
- **Improve patient outcomes** through targeted therapy
- **Combat antibiotic resistance** by optimizing drug selection
- **Support clinical decision-making** with interpretable AI

## 📋 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

We welcome contributions! Please feel free to submit a Pull Request or open an Issue for any bugs or feature requests.

## 📞 Contact

For questions, collaborations, or clinical partnerships, please reach out through our GitHub repository or visit our live application.
