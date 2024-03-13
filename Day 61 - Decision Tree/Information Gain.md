## Information Gain

Information gain is a measure used in decision trees to determine the effectiveness of a feature in classifying or splitting the dataset. It quantifies the reduction in entropy (or increase in homogeneity) achieved by splitting the dataset based on a particular feature.

### Calculation of Information Gain:

1. **Calculate Entropy before Split (Entropy(S))**: 
   - Compute the entropy of the dataset before splitting based on the class labels.

2. **Calculate Entropy after Split (Weighted Entropy(S, Feature))**: 
   - For each possible value of the feature, calculate the entropy of the dataset after splitting based on that feature.
   - Weight each entropy value by the proportion of data points in that subset.

3. **Calculate Information Gain**:
   - Subtract the weighted entropy of the subsets from the entropy of the original dataset.
  
The formula to calculate information gain in decision trees is:

$ \text{Information Gain} = \text{Entropy before split} - \text{Weighted Entropy after split} $

Where:
- **Entropy before split** ($ H(S) $) is the entropy of the dataset before splitting based on the class labels.
- **Weighted Entropy after split** ($ \sum_{i=1}^{n} \frac{N_i}{N} \cdot H(S_i) $) is the weighted average of the entropies of the subsets after splitting, where $ N_i $ is the number of data points in the $ i^{th} $ subset and $ N $ is the total number of data points in the dataset.
- $ H(S_i) $ is the entropy of the $ i^{th} $ subset after splitting.

The entropy formula is:

$ H(S) = - \sum_{i=1}^{K} p_i \log_2(p_i) $

Where:
- $ p_i $ is the proportion of data points in class $ i $ (i.e., $ \frac{\text{number of data points in class } i}{N} $).
- The summation runs over all classes present in the dataset.

So, the complete formula to calculate information gain can be written as:

$ \text{Information Gain} = H(S) - \sum_{i=1}^{n} \frac{N_i}{N} \cdot H(S_i) $

Where:
- $ H(S) $ is the entropy of the entire dataset.
- $ N_i $ is the number of data points in the $ i^{th} $ subset after splitting.
- $ H(S_i) $ is the entropy of the $ i^{th} $ subset after splitting.

### Steps to Calculate Information Gain:

Let's go through an example to illustrate the steps for calculating information gain:

#### Example:
Consider a dataset with 100 data points and a binary classification task (class labels A and B). We want to split the dataset based on a feature (Feature X) that can take on three values: X1, X2, and X3.

- Before Split:
  - Class A: 70 data points
  - Class B: 30 data points
  - Entropy before split (Entropy(S)) = Calculate entropy of the entire dataset using the formula $ H(S) = -p_A \log_2(p_A) - p_B \log_2(p_B) $, where $ p_A $ and $ p_B $ are the proportions of class A and class B, respectively.

- After Split (based on Feature X):
  - Subset 1 (Feature X = X1): 
    - Class A: 40 data points
    - Class B: 10 data points
  - Subset 2 (Feature X = X2): 
    - Class A: 20 data points
    - Class B: 15 data points
  - Subset 3 (Feature X = X3): 
    - Class A: 10 data points
    - Class B: 5 data points

- Calculate Weighted Entropy (Weighted Entropy(S, Feature)) for each subset:
  - For each subset, calculate entropy using the same formula as above, weighted by the proportion of data points in that subset.

- Calculate Information Gain:
  - Subtract the weighted entropies of the subsets from the entropy of the original dataset.

The feature with the highest information gain is chosen as the splitting criterion at each node of the decision tree.

### Summary:
Information gain is a crucial concept in decision trees, guiding the selection of features for splitting the dataset. It helps to identify the most informative features that lead to the greatest reduction in entropy, resulting in more effective and efficient decision trees.