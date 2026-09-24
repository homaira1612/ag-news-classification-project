# Literature Review

## Source 1: Character-level Convolutional Networks for Text Classification
This foundational paper by Zhang et al. introduces the AG News benchmark dataset and evaluates various traditional and deep learning models for news categorization. The authors demonstrate that convolutional networks operating on character-level features effectively capture lexical patterns without extensive linguistic preprocessing. These insights inform our baseline feature extraction and help benchmark classification performance.

## Source 2: Text Classification using TF-IDF and Linear Classifiers
This study explores TF-IDF feature extraction combined with linear models like Logistic Regression and Support Vector Machines for multi-class news tasks. The authors emphasize that removing stop words and utilizing n-grams significantly reduces dimensionality while preserving semantic context in short text snippets. This validates our choice of using TF-IDF vectors as an efficient text representation method.

## Source 3: Preprocessing and Normalization Strategies in Natural Language Processing
This article analyzes how text cleaning steps—such as lowercasing, punctuation stripping, and handling HTML artifacts—impact text classifier convergence and accuracy. The research highlights that aggressive text normalization minimizes vocabulary sparsity and eliminates noise, resulting in more stable and generalizable models. We will incorporate these exact cleaning protocols into our preprocessing pipeline.
