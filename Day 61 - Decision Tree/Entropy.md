## Entropy in Decision Trees

Decision trees work by recursively splitting the dataset into subsets based on the values of input features, aiming to create regions that are as homogenous as possible with respect to the target variable (class label or regression value). Entropy is a measure used in decision trees to quantify the impurity or disorder of a dataset.

### Entropy:

Entropy measures the impurity or disorder of a set of data points. In the context of decision trees, it quantifies the uncertainty in the distribution of class labels within a dataset. A dataset with low entropy means it is highly ordered, with all data points belonging to the same class, while a dataset with high entropy means it is highly disordered, with an equal distribution of class labels.

### Calculating Entropy:

The entropy $ H(S) $ of a dataset $ S $ with $ N $ data points and $ K $ classes is calculated as follows:

$ H(S) = - \sum_{i=1}^{K} p_i \log_2(p_i) $

Where:
- $ p_i $ is the proportion of data points in class $ i $ (i.e., $ \frac{\text{number of data points in class } i}{N} $).
- The summation runs over all classes present in the dataset.

### Observations:

- More the uncertainty more is entropy
- For a 2 class problem the minimum entropy is 0 and maximum is 1
- For more than 2 classes the minimum entropy is 0 but maximum can be greater than 1
- Both $\log_2$ and $\log_e$ can be used to calculate entropy

### Entropy vs. Probability Graph:

The entropy vs. probability graph illustrates the relationship between entropy and the probability of different outcomes. Typically, as the probability of a particular outcome increases, the entropy decreases. This is because a higher probability of a single outcome leads to less uncertainty or disorder.

Here's how the graph typically looks:

- When the probability of an outcome is 0 or 1, the entropy is 0 because there is no uncertainty.
- As the probability becomes more evenly distributed among different outcomes, the entropy increases, reaching a maximum when the probabilities are uniformly distributed.
- The entropy is minimized when one outcome has a probability of 1 and all other outcomes have probabilities of 0.

The entropy vs. probability graph provides a visual representation of the relationship between uncertainty and the distribution of outcomes, highlighting the role of entropy in quantifying uncertainty in decision-making scenarios.

![Entropy vs Probability](https://miro.medium.com/v2/resize:fit:720/format:webp/1*M15RZMSk8nGEyOnD8haF-A.png)