# Project Proposal

## Research Question
Can a simple feedforward Artificial Neural Network (ANN), using only a news
article's headline and short description, reliably classify the article into
one of four categories (World, Sports, Business, Sci/Tech)? What is the
practical accuracy ceiling of a plain ANN (as opposed to a CNN/RNN/Transformer)
on this task, and which categories are hardest for it to separate?

## Dataset
- **Name:** AG News Classification Dataset
- **Source:** Kaggle — https://www.kaggle.com/datasets/amananandrai/ag-news-classification-dataset
- **Description:** 120,000 labeled news articles (30,000 per class), each with
  a `Title`, a short `Description`, and a `Class Index` (1–4) label. The
  dataset is balanced and requires no resampling.

## Two-Source Scan of Existing Work

1. **"Bag of Tricks for Efficient Text Classification" (Joulin et al., 2016 —
   fastText paper).** Shows that even simple linear/shallow models using
   word/n-gram features can reach strong accuracy on text classification
   tasks, competitive with much deeper architectures, provided the input
   features are chosen well. This supports testing a simple ANN before
   reaching for a more complex model.

2. **Keras/TensorFlow official text classification tutorials (TensorFlow.org).**
   Demonstrate the standard pipeline of `TextVectorization` → trainable
   `Embedding` layer → pooling → dense classification head for short-text
   classification tasks, which is the architecture pattern this project
   adopts, since it lets the network learn word representations directly
   from the training data rather than relying on fixed hand-crafted features.

## Planned Approach
1. Load and explore the AG News dataset (class balance, missing values).
2. Preprocess: combine `Title` + `Description`, clean text, tokenize with
   `TextVectorization`.
3. Build a simple ANN: `Embedding → GlobalAveragePooling1D → Dense → Softmax`.
4. Train with an 80/10/10 train/validation/test split and early stopping.
5. Evaluate with accuracy, a classification report, and a confusion matrix,
   then analyze which classes are most often confused and why.

## Success Criteria
The project will be considered successful if the trained ANN achieves at
least 85% test accuracy — comfortably above the 25% random-guess baseline
for four balanced classes — and if the analysis section can clearly explain
at least one systematic source of misclassification (e.g. class overlap in
vocabulary) rather than treating errors as unexplained noise.
