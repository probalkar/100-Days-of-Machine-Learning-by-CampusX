## Maths behind SVM

Support Vector Machine (SVM) is a powerful supervised machine learning algorithm used for classification and regression tasks. SVM aims to find the optimal hyperplane that best separates the data points of different classes in a high-dimensional feature space. Here's a detailed explanation of the mathematics behind SVM:

### Linear SVM for Binary Classification:

#### 1. **Hyperplane Equation**:
   - In SVM, a hyperplane is a decision boundary that separates the data points into different classes. For a binary classification problem with two classes (+1 and -1), the equation of a hyperplane can be represented as:
     $$ \mathbf{w} \cdot \mathbf{x} + b = 0 $$
   - Here, $\mathbf{w}$ is the weight vector perpendicular to the hyperplane, $\mathbf{x}$ is the input feature vector, and $b$ is the bias term.

#### 2. **Margin**:
   - The margin is the distance between the hyperplane and the nearest data points (support vectors) of each class. In SVM, the goal is to maximize the margin, as it leads to better generalization.
   - The margin is given by:
     $$ \text{margin} = \frac{2}{\| \mathbf{w} \|} $$

#### 3. **Optimization Objective**:
   - SVM aims to find the hyperplane that maximizes the margin while minimizing the classification error.
   - Mathematically, the optimization objective of SVM can be formulated as:
     $$ \text{minimize} \quad \frac{1}{2} \| \mathbf{w} \|^2 $$
     subject to the constraints:
     $$ y_i (\mathbf{w} \cdot \mathbf{x}_i + b) \geq 1 $$
     for all training examples $ (\mathbf{x}_i, y_i) $, where $ y_i $ is the class label (+1 or -1).

#### 4. **Optimization Method**:
   - SVM solves the optimization problem using techniques such as quadratic programming or gradient descent to find the optimal values of $ \mathbf{w} $ and $ b $.

### Geometric Intuition:

- **Decision Boundary**:
  - In a two-dimensional feature space, the hyperplane is a straight line that separates the data points into two classes. In higher-dimensional spaces, it becomes a hyperplane.
  - The decision boundary is equidistant from the support vectors of each class and is positioned to maximize the margin.

- **Support Vectors**:
  - Support vectors are the data points that lie closest to the decision boundary.
  - These points determine the position and orientation of the hyperplane.

- **Margin Maximization**:
  - SVM selects the hyperplane that maximizes the margin between the classes.
  - By maximizing the margin, SVM achieves better generalization and is less sensitive to noise and outliers.

- **Kernel Trick**:
  - SVM can handle nonlinear decision boundaries by mapping the input features into a higher-dimensional space using a kernel function.
  - In the higher-dimensional space, the SVM finds a linear hyperplane that separates the data points.

### Kernel Trick:

- SVM uses kernel functions (e.g., linear, polynomial, Gaussian radial basis function) to implicitly map the input features into a higher-dimensional space without explicitly computing the transformation.
- The kernel trick allows SVM to find nonlinear decision boundaries in the original feature space.

### Conclusion:

Support Vector Machine is a versatile and powerful algorithm for classification and regression tasks. By maximizing the margin and finding the optimal hyperplane, SVM achieves robust performance and can handle both linear and nonlinear decision boundaries effectively. Understanding the mathematics behind SVM helps in interpreting its behavior and tuning the model for optimal performance.

### [YouTube Video](https://youtu.be/yCAlHPDgWtM?si=zvmLWSFooVQlrPiH)