## AdaBoost Classifier

AdaBoost (Adaptive Boosting) is an ensemble learning technique that combines multiple weak learners to build a strong classifier. It sequentially trains a series of weak learners on weighted versions of the training data, where the weights are adjusted at each iteration to focus more on the misclassified samples. Here's a detailed explanation of how AdaBoost works mathematically:

### 1. Initialization:
- At the beginning, each sample in the training dataset is assigned an equal weight, denoted as $ w_i^{(1)} = \frac{1}{N} $, where $ N $ is the total number of samples.

### 2. Iterative Training:
- AdaBoost sequentially trains a series of weak learners (decision trees with max depth = 1; also called decision stumps) on the training data.
- At each iteration $ t $, a weak learner $ h_t(x) $ is trained on the weighted training dataset.
- The weak learner is selected based on its ability to minimize the weighted classification error.

### 3. Weighted Classification Error:
- The weighted error $ \epsilon_t $ of the weak learner $ h_t(x) $ is calculated as the sum of weights of misclassified samples:
   $ \epsilon_t = \sum_{i=1}^{N} w_i^{(t)} \cdot \mathbb{1} \{ h_t(x_i) \neq y_i \} $
  where $ \mathbb{1} $ is the indicator function.
  
### 4. Weak Learner Weight:
- The weight $ \alpha_t $ assigned to the weak learner $ h_t(x) $ is calculated based on its classification error:
   $ \alpha_t = \frac{1}{2} \ln \left( \frac{1 - \epsilon_t}{\epsilon_t} \right) $
  where the $ \frac{1}{2} \ln $ term ensures that the weight is positive regardless of the error rate.

### 5. Sample Weight Update:
- The weights of misclassified samples are increased, while the weights of correctly classified samples are decreased to focus more on the misclassified samples for the next iteration.
- For misclassified points : $ w_i^{new} = w_i^{old} \cdot e^{\alpha_t} $
- For correctly classified points : $ w_i^{new} = w_i^{old} \cdot e^{-\alpha_t} $
- The summation of all the new weights may or may not be equal to 1, so make sure to normalize those weights before reassigning them.

### 6. Final Prediction:
- The final prediction is obtained by combining the predictions of all weak learners weighted by their respective $\alpha$ values:
   $ H(x) = \text{sign} \left( \sum_{t=1}^{T} \alpha_t \cdot h_t(x) \right) $

### AdaBoost Algorithm Summary:

1. Initialize sample weights.
2. For $ t = 1, 2, \ldots, T $:
   - Train a weak learner $ h_t(x) $ on the weighted dataset.
   - Calculate weighted classification error $ \epsilon_t $ and weak learner weight $ \alpha_t $.
   - Update sample weights based on misclassifications.
3. Combine weak learners to form the final strong classifier $ H(x) $.

### Key Points:

- AdaBoost focuses more on misclassified samples at each iteration, making it resilient to noisy data and outliers.
- The final model is a weighted combination of weak learners, where each weak learner contributes to the final prediction based on its performance.
- The algorithm continues iterating until a predefined number of weak learners are trained or until a satisfactory performance is achieved.

### Mathematical Interpretation:

AdaBoost effectively adapts the weights of misclassified samples to iteratively correct the model's mistakes, resulting in a strong classifier that can handle complex decision boundaries and achieve high accuracy even with simple weak learners. The mathematical formulation ensures that more weight is given to difficult-to-classify samples, leading to a focused learning process that improves the overall performance of the ensemble model.

### [YouTube Video](https://youtu.be/RT0t9a3Xnfw?si=BOUSncnVpOY_pxtW&t=897)