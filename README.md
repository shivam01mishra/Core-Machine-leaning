# Active Learning & Submodularity

Selecting an informative, sensitivity-weighted subset of training data instead of using the full dataset, and measuring how much classifier accuracy is retained.

### What's here

`Active_learning_and_Submodularity.ipynb` — on the scikit-learn digits dataset (1,797 samples, 64 features):

1. Scores each data point by sensitivity/informativeness and selects a smaller, representative subset.
2. Trains four classifiers — KNN, Logistic Regression, SVM, and Random Forest — on both the full dataset and the selected subset.
3. Compares test accuracy between the two.

### Result

| Model | Full data | Subset |
|---|---|---|
| KNN | 98.9% | 97.5–98.6% |
| Logistic Regression | 97.2% | 95.6% |
| SVM | 97.8% | 97.8% (no loss) |
| Random Forest | 95.3% | 91.1% |

Training on the selected subset comes close to (and for SVM, matches) full-dataset accuracy, which is the point of submodularity-based active learning: get near-full performance while training on a fraction of the data.

Related: [differential-Privacy-using-coreset](https://github.com/shivam01mishra/differential-Privacy-using-coreset) applies the same "smart subset instead of full data" idea to clustering.
