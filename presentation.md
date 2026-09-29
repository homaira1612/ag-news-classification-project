# AG News Classification Project Presentation

## Slide 1: Title & Overview
* **Project Title:** AG News Classification Using TF-IDF and Classical Machine Learning
* **Author:** Homaira
* **Objective:** Automate the 4-class categorization of news articles (World, Sports, Business, Sci/Tech) using NLP and machine learning.

## Slide 2: Problem Statement & Motivation
* **The Challenge:** Massive influx of digital news requires automated organization.
* **Limitation:** Manual tagging is slow and unscalable.
* **Goal:** Build a robust, high-accuracy text classification pipeline to streamline document indexing.

## Slide 3: Methodology & Pipeline
* **Dataset:** Hugging Face `fancyzhx/ag_news` (120K training, 7.6K test samples).
* **Preprocessing:** Lowercasing, punctuation removal, stopword filtering, and lemmatization.
* **Feature Extraction:** TF-IDF vectorization (top 10,000 features).

## Slide 4: Model Architectures
* **Logistic Regression:** Linear classifier optimized for high-dimensional, sparse feature spaces.
* **Random Forest:** Ensemble tree-based model (100 estimators) to capture complex feature splits.

## Slide 5: Results & Performance
* **Logistic Regression:** Achieved **91.2% accuracy** and 0.91 Macro F1-Score.
* **Random Forest:** Achieved **88.5% accuracy** with significantly longer training overhead.
* **Visual Artifacts:** Supported by `accuracy_comparison.png` and `per_class_performance.png`.

## Slide 6: Discussion & Limitations
* **Key Insight:** Linear classifiers excel in sparse TF-IDF spaces due to clean linear separation.
* **Limitations:** Bag-of-words approach lacks deep contextual awareness, word order sensitivity, and semantic nuance.

## Slide 7: Conclusion & Takeaways
* **Summary:** Classical machine learning combined with TF-IDF provides an exceptionally strong and fast classification baseline.
* **Recommendation:** Logistic Regression is ideal for production text-routing applications due to its high accuracy and minimal latency.
