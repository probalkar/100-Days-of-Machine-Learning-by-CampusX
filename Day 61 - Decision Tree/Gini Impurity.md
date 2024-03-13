## Gini Impurity

Gini impurity is another measure used in decision trees to quantify the impurity or randomness of a dataset. It measures the probability of incorrectly classifying a randomly chosen element if it were randomly labeled according to the distribution of class labels in the dataset. A low Gini impurity indicates that a dataset is pure (i.e., contains mostly instances of a single class), while a high Gini impurity indicates that the dataset is impure (i.e., contains a mix of different classes).

### Gini Impurity Formula:

The Gini impurity ($ Gini(S) $) for a dataset $ S $ with $ N $ data points and $ K $ classes is calculated as follows:

$ Gini(S) = 1 - \sum_{i=1}^{K} (p_i)^2 $

Where:
- $ p_i $ is the proportion of data points in class $ i $ (i.e., $ \frac{\text{number of data points in class } i}{N} $).
- The summation runs over all classes present in the dataset.

### Using Gini Impurity to Calculate Gini Gain:

Similar to information gain, Gini gain is calculated to determine the effectiveness of a feature in classifying or splitting the dataset. It quantifies the reduction in Gini impurity achieved by splitting the dataset based on a particular feature.

The formula for Gini gain is:

$ \text{Gini Gain} = \text{Gini before split} - \text{Weighted Gini after split} $

Where:
- **Gini before split** ($ Gini(S) $) is the Gini impurity of the dataset before splitting based on the class labels.
- **Weighted Gini after split** ($ \sum_{i=1}^{n} \frac{N_i}{N} \cdot Gini(S_i) $) is the weighted average of the Gini impurities of the subsets after splitting, where $ N_i $ is the number of data points in the $ i^{th} $ subset and $ N $ is the total number of data points in the dataset.
- $ Gini(S_i) $ is the Gini impurity of the $ i^{th} $ subset after splitting.

### Steps to Calculate Gini Gain:

1. **Calculate Gini Impurity before Split (Gini(S))**: Compute the Gini impurity of the dataset before splitting based on the class labels.

2. **Calculate Gini Impurity after Split for Each Subset**: For each possible value of the feature, calculate the Gini impurity of the dataset after splitting based on that feature.

3. **Calculate Weighted Gini after Split**: Compute the weighted average of the Gini impurities of the subsets after splitting, weighted by the proportion of data points in each subset.

4. **Calculate Gini Gain**: Subtract the weighted Gini impurities of the subsets from the Gini impurity of the original dataset.

The feature with the highest Gini gain is chosen as the splitting criterion at each node of the decision tree.

### Gini Impurity vs Entropy

| Criterion       | Formula                                           | Range       | Interpretation                                     | 
|-----------------|---------------------------------------------------|-------------|----------------------------------------------------|
| Gini Impurity   | $ Gini(S) = 1 - \sum_{i=1}^{K} (p_i)^2 $      | $[0, 0.5]$ | Measures the probability of incorrectly classifying a randomly chosen element based on the distribution of class labels in the dataset. Lower values indicate less impurity (more homogeneity). |
| Entropy         | $ H(S) = - \sum_{i=1}^{K} p_i \log_2(p_i) $    | $[0, 1]$   | Measures the uncertainty or randomness in the distribution of class labels in the dataset. Lower values indicate less uncertainty (more homogeneity).   |

### Gini Impurity vs. Probability Graph:

The Gini impurity vs. probability graph illustrates the relationship between Gini impurity and the probability of different outcomes. Typically, as the probability of a particular outcome increases, the Gini impurity decreases. This is because a higher probability of a single outcome leads to less impurity or randomness.

Here's how the graph typically looks:

- When the probability of an outcome is 0 or 1, the Gini impurity is 0 because there is no impurity (or randomness).
- As the probability becomes more evenly distributed among different outcomes, the Gini impurity increases, reaching a maximum when the probabilities are uniformly distributed.
- The Gini impurity is minimized when one outcome has a probability of 1 and all other outcomes have probabilities of 0.

The Gini impurity vs. probability graph provides a visual representation of the relationship between impurity and the distribution of outcomes, highlighting the role of Gini impurity in quantifying impurity or randomness in decision-making scenarios.

![Gini Impurity and Entropy vs Probability](https://media.geeksforgeeks.org/wp-content/uploads/20200620180439/Gini-Impurity-vs-Entropy.png)