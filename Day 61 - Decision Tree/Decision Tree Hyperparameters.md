## Decision Tree Hyperparameter

Scikit-learn provides several hyperparameters that can be tuned to control the behavior and performance of decision tree models. Here's a detailed description of the most commonly used decision tree hyperparameters in scikit-learn:

1. **Criterion**:
   - **Description**: Specifies the criterion used to measure the quality of a split.
   - **Options**: "gini" for Gini impurity or "entropy" for information gain.
   - **Default**: "gini".

2. **Splitter**:
   - **Description**: Specifies the strategy used to choose the split at each node.
   - **Options**: "best" to choose the best split or "random" to choose the best random split.
   - **Default**: "best".

3. **Max Depth**:
   - **Description**: Specifies the maximum depth of the tree.
   - **Options**: An integer or None.
   - **Default**: None (i.e., nodes are expanded until all leaves are pure or until all leaves contain less than min_samples_split samples).

4. **Min Samples Split**:
   - **Description**: The minimum number of samples required to split an internal node.
   - **Options**: An integer or a float representing a percentage of total samples.
   - **Default**: 2.

5. **Min Samples Leaf**:
   - **Description**: The minimum number of samples required to be at a leaf node.
   - **Options**: An integer or a float representing a percentage of total samples.
   - **Default**: 1.

6. **Min Weight Fraction Leaf**:
   - **Description**: The minimum weighted fraction of the sum total of weights (of all the input samples) required to be at a leaf node.
   - **Options**: A float between 0.0 and 0.5.
   - **Default**: 0.0.

7. **Max Features**:
   - **Description**: The number of features to consider when looking for the best split.
   - **Options**: An integer, float, "auto", "sqrt", "log2", None.
   - **Default**: None (i.e., all features are considered).

8. **Max Leaf Nodes**:
   - **Description**: The maximum number of leaf nodes in the tree.
   - **Options**: An integer.
   - **Default**: None.

9. **Min Impurity Decrease**:
   - **Description**: A node will be split if this split induces a decrease of the impurity greater than or equal to this value.
   - **Options**: A float.
   - **Default**: 0.0.

10. **Min Impurity Split**:
    - **Description**: Threshold for early stopping in tree growth. A node will split if its impurity is above the threshold, otherwise it is a leaf.
    - **Options**: A float.
    - **Default**: 1e-7.

11. **Presort**:
    - **Description**: Whether to presort the data to speed up the finding of best splits in fitting.
    - **Options**: True or False.
    - **Default**: Deprecated in version 0.24 and will be removed in version 1.1.

These hyperparameters control various aspects of the decision tree model, such as its depth, the number of samples required for splits and leaves, and the splitting criterion. Proper tuning of these hyperparameters can significantly impact the performance and generalization of the decision tree model.