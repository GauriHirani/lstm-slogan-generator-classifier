# LSTM Slogan Generator and Classifier

A project employing a Long Short Term Memory (LSTM) model to generate and classify slogans. The slogan generator predicts the next word after an industry seed, repeating this until it reaches a maximum slogan length. The slogan classifier takes a slogan as input and predicts which industry it belongs to.

## Setup

This notebook is built and run in Google Colab.

`slogan-valid.csv` is included in this repository, but the notebook loads it from Google Drive. To run it yourself, either:
- upload the CSV to your Drive at the same file path used in the notebook, or
- update the file path in the data-loading cell to wherever it has been saved

## Key Findings

**Slogan Generator:**
The generator successfully produced slogans that stay relatively on topic for their industry, using vocabulary genuinely associated with each one. However, the sentences themselves are not fully coherent, reading more like clusters of relevant words rather than a true structured slogan.

**Slogan Classifier:**
The classifier performed poorly on the test set, with an accuracy of 21%, despite reaching ~99% accuracy on training data. This suggests overfitting, likely driven by some industries having relatively few training examples, and by several industries overlapping in the broader field they belong to.

**Combining Models:**
When a generated "internet" slogan was passed to the classifier, it was labelled as marketing and advertising instead. The generated slogan did contain internet-related words like "web" and "digital", but more closely matched marketing and advertising in language. This suggested the classifier was picking up genuine patterns rather than randomly guessing, and highlights how much industries overlap in language, which likely limits how well the model can distinguish between them.

## Tools

Python, TensorFlow/Keras, pandas, NumPy, spaCy, scikit-learn
