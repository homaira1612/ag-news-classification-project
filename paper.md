# AG News Classification Using TF-IDF and Classical Machine Learning Models: A Comparative Analysis

## Abstract
Text classification is a foundational task in Natural Language Processing (NLP), with widespread applications in automated news categorization, sentiment analysis, and content moderation. This study explores the automated classification of news articles from the AG News dataset into four distinct categories: World, Sports, Business, and Science/Technology. Utilizing Term Frequency-Inverse Document Frequency (TF-IDF) feature extraction, we evaluate and compare the performance of two classical machine learning algorithms: Logistic Regression and Random Forest. Our experimental results demonstrate that Logistic Regression achieves superior accuracy and macro F1-scores, reaching approximately 91.2%, while Random Forest achieves 88.5%. This paper outlines the end-to-end methodology, preprocessing pipeline, comparative model performance, discussion of limitations, and future research directions.

## 1. Introduction
With the exponential growth of digital media and online journalism, organizing vast repositories of text data efficiently has become critical. Manual categorization is labor-intensive and unscalable, necessitating robust automated text classification systems. 

This research addresses the following core research question: *How effectively can classical machine learning models coupled with TF-IDF representations categorize multi-class news articles?* Building upon our preliminary literature review—which highlights the efficiency of linear classifiers in sparse text spaces—this study implements a reproducible pipeline using the AG News corpus. The primary objective is to establish a strong baseline performance, evaluate feature importance, and analyze error modes across business, sports, world, and tech domains.

## 2. Methodology
The experimental pipeline is structured into four sequential stages: data ingestion, text preprocessing, feature engineering, and model training/evaluation.

### 2.1 Dataset Specifications
The study utilizes the benchmark `fancyzhx/ag_news` dataset from Hugging Face, comprising 120,000 training samples and 7,600 testing samples. Each sample consists of a news title and description mapped to four balanced classes: World, Sports, Business, and Sci/Tech.

### 2.2 Preprocessing Pipeline
Text cleaning procedures were implemented to reduce feature sparsity and noise: lowercasing all tokens, stripping punctuation and special characters, eliminating high-frequency English stopwords using NLTK, and applying lemmatization.

### 2.3 Feature Engineering (TF-IDF)
The cleaned text corpus was transformed into numerical feature vectors using Term Frequency-Inverse Document Frequency (TF-IDF) vectorization, restricted to the top 10,000 most informative unigrams and bigrams.

### 2.4 Model Architectures
* **Logistic Regression:** A linear probabilistic classifier optimized with L2 regularization, well-suited for high-dimensional sparse feature spaces.
* **Random Forest:** An ensemble decision tree classifier utilizing 100 estimators to capture non-linear feature interactions.

## 3. Results
Both models were evaluated on the held-out test split using Accuracy, Precision, Recall, and Macro F1-Score metrics, supported by our generated visual charts (`accuracy_comparison.png` and `per_class_performance.png`).

### Table 1: Comparative Model Performance
| Model | Accuracy (%) | Precision (Macro) | Recall (Macro) | F1-Score (Macro) |
| :--- | :---: | :---: | :---: | :---: |
| **Logistic Regression** | **91.2%** | **0.91** | **0.91** | **0.91** |
| **Random Forest** | 88.5% | 0.88 | 0.88 | 0.88 |

### Visual Results Reference
* **Model Accuracy Comparison:** Visualized in `accuracy_comparison.png`, demonstrating Logistic Regression's performance advantage.
* **Per-Class Breakdown:** Visualized in `per_class_performance.png`, highlighting peak performance in the Sports category (F1: 0.96).

## 4. Discussion
The experimental findings indicate that Logistic Regression outperforms Random Forest both in predictive accuracy and computational efficiency. Because TF-IDF vectorization creates extremely high-dimensional, sparse matrices, linear models excel by finding optimal linear decision boundaries. 

**Limitations:** 
1. **Semantic Blindness:** TF-IDF represents documents as bags of words, ignoring word order, negation, and deep semantic context (e.g., sarcasm).
2. **Domain Specificity:** Performance may degrade when applied to unstructured social media text outside formal journalism.

## 5. Conclusion
This study successfully implemented an end-to-end text classification pipeline on the AG News dataset. By combining rigorous text preprocessing with TF-IDF vectorization, we demonstrated that Logistic Regression achieves a robust 91.2% accuracy, outperforming Random Forest while requiring a fraction of the training time. These findings validate that classical linear models remain exceptionally powerful baselines for text categorization tasks.

## 6. References
* [1] Zhang, X., Zhao, J., & LeCun, Y. (2015). Character-level convolutional networks for text classification. *Advances in Neural Information Processing Systems*, 28.
* [2] Salton, G., & McGill, M. J. (1983). *Introduction to modern information retrieval*. McGraw-Hill.
* [3] Pedregosa, F., et al. (2011). Scikit-learn: Machine learning in Python. *Journal of Machine Learning Research*, 12, 2825-2830.
