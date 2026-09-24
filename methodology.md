# Methodology

## 1. Refined Research Question
To what extent can machine learning models accurately classify news articles from the AG News dataset into their respective categories (World, Sports, Business, Sci/Tech) based on textual descriptions, and how do feature representation methods impact classification efficiency?

## 2. Dataset Description
* **Source**: AG News dataset (available via Hugging Face or CSV datasets).
* **Size**: 120,000 training samples and 7,600 testing samples.
* **Target Variable**: Multi-class label representing four distinct news domains (0: World, 1: Sports, 2: Business, 3: Sci/Tech).
* **Features**: Text fields containing article titles and descriptions.
* **Limitations**: Short article descriptions may lack broader contextual depth, and historical publication biases could affect real-time generalization.

## 3. Data Cleaning Plan
* Convert all text strings to lowercase to ensure consistency across identical words.
* Remove HTML tags, punctuation, URLs, and special characters using regular expressions.
* Filter out standard English stop words to reduce vocabulary noise and dimensionality.

## 4. Feature Engineering Plan
* Apply **TF-IDF Vectorization** with unigrams and bigrams to convert raw text into weighted numerical matrices.
* Cap the maximum vocabulary size (e.g., top 10,000 features) to optimize computational efficiency and training time.

## 5. Model Selection & Rationale
* **Logistic Regression**: Selected as a robust, highly interpretable baseline model that excels with high-dimensional sparse TF-IDF feature spaces.
* **Random Forest Classifier**: Chosen to capture non-linear feature interactions and handle multi-class text boundaries effectively.

## 6. Evaluation Metric(s) & Rationale
* **Accuracy**: Measures the overall percentage of correctly classified news articles across all categories.
* **Macro-Averaged F1-Score**: Evaluates precision and recall balance evenly across all four classes, ensuring reliable performance even if class distributions shift.
