# Unit 1

### Performance measure of learning
1. Generality:- refers to ML model's ability to perform well accross various datasets and environment, not just one it was trained on.
2. Efficiency:- How quickly a model can learn from data. A spam detection algorithm that quickly adapts to new type of spam emails
3. Robustness:- ability of a model to handle errors, noise and unexcpected data without failing. A voice recognition system able to recognize voice in a noisy room.
4. Efficacy:- overall effectiveness of a ML model in performing its intended tasks.
5. Ease of implementation:- how straightforward is it to develop and deploy a ML model.

### Supervised learning
- involves training a machine learning model using labeled data, which means the **data is already associated with correct answer**.
  Eg: predicting house prices based on features like size and location, using a dataset where prices are known, allows the model to learn and make accurate predictions on new, unseen data.

#### Steps in Supervised learning
- input and output pairing:- each input is paired with its correct label.
- training:- model learns by compairing its prediction with actual label and adjusting itself to improve accuracy.
- error correction:- if model predicts incorrectly it adjusts its internal parameters to reduce error.
- outcome:- model eventually learn to map input to correct output.

### Unsupervised learning
- involves training model without any label , which means the model tries to identify patterns and data groupings on its own.
  Eg: Imagine placing a mix of different coins on a table and asking to sort them. without explaining any criteria , the child might start grouping by size,color etc.

#### Steps 
- input without labels:- the model receives data without any explicit instructions on what to do with it.
- pattern recognition:- model analyze data and tries to find any natural grouping or patterns.
- self-organisation:- model organise data into different categories based on the patterns it receives.
- outcome:- model creates its own system of categorization without external guidance.

### machine learning
- subset of AI allows computers to learn from and make decisions based on data,without being explicitly programmed.
- involves developing algorithm that allow computers to process and learn from data automatically.

> Machine learning is the study of computer algorithms that improve automatically through experience. It is a field of artificial intelligence that focuses on developing systems that can learn from and make predictions or decisions based on data.

### Types of ML
Machine learning is generally categorized into three main types based on how the learning process is structured and the nature of the feedback the model receives. Here are the three primary types:

#### 1. **Supervised Learning**

**Description**: In supervised learning, the model is trained on a labeled dataset, meaning that each training example is paired with an output label. The goal is to learn a mapping from inputs to outputs that can be used to predict the labels for new, unseen data.

**Examples**:
- **Classification**: Email spam detection, sentiment analysis, image classification.
- **Regression**: Predicting house prices, stock market forecasting, temperature prediction.

**Key Algorithms**:
- Linear Regression
- Logistic Regression
- Decision Trees
- Support Vector Machines (SVM)
- Neural Networks

#### 2. **Unsupervised Learning**

**Description**: In unsupervised learning, the model is trained on data without explicit labels. The goal is to identify patterns, relationships, or structures within the data. The model learns to group or organize the data based on similarities or differences.

**Examples**:
- **Clustering**: Customer segmentation, grouping similar documents, image segmentation.
- **Dimensionality Reduction**: Reducing the number of features in data while preserving important information (e.g., PCA).
- **Anomaly Detection**: Identifying unusual patterns or outliers in data.

**Key Algorithms**:
- K-Means Clustering
- Hierarchical Clustering
- Principal Component Analysis (PCA)

#### 3. **Reinforcement Learning**

**Description**: In reinforcement learning, the model learns to make decisions by interacting with an environment. The model receives feedback in the form of rewards or penalties based on its actions, and it aims to learn a strategy that maximizes cumulative rewards over time.

**Examples**:
- **Game Playing**: Training AI to play games like chess, Go, or video games.
- **Robotics**: Teaching robots to navigate environments or perform tasks.
- **Recommendation Systems**: Adaptive recommendation systems that improve over time based on user interactions.

**Key Algorithms**:
- Q-Learning

#### Summary

- **Supervised Learning**: Learning from labeled data to make predictions or classify new data.
- **Unsupervised Learning**: Finding hidden patterns or structures in unlabeled data.
- **Reinforcement Learning**: Learning to make a sequence of decisions by receiving rewards or penalties from interactions with an environment.

### Application of ML

1. **Image Recognition**:
   - **Example**: Identifying objects, people, or scenes in photos and videos. Used in applications like facial recognition and autonomous vehicles.

2. **Natural Language Processing (NLP)**:
   - **Example**: Language translation, sentiment analysis, and chatbots. NLP enables machines to understand and respond to human language.

3. **Recommendation Systems**:
   - **Example**: Personalized recommendations for products, movies, or music on platforms like Netflix, Amazon, and Spotify.

4. **Fraud Detection**:
   - **Example**: Identifying unusual patterns in financial transactions to detect and prevent fraudulent activities in banking and credit card systems.

5. **Predictive Maintenance**:
   - **Example**: Monitoring machinery and equipment to predict failures before they occur, minimizing downtime and maintenance costs in industries like manufacturing and aviation.

6. **Healthcare Diagnostics**:
   - **Example**: Analyzing medical images to assist in diagnosing diseases, predicting patient outcomes, and personalizing treatment plans based on patient data.

7. **Autonomous Vehicles**:
   - **Example**: Enabling self-driving cars to make real-time decisions based on sensor data, including navigation, obstacle detection, and traffic management.

### Advantages of Machine Learning

1. **Automation of Tasks**:
   - **Advantage**: ML algorithms can automate repetitive tasks and processes, reducing the need for manual intervention and increasing efficiency.

2. **Handling Large Datasets**:
   - **Advantage**: ML models can process and analyze vast amounts of data quickly and accurately, providing insights that would be challenging to uncover manually.

3. **Personalization**:
   - **Advantage**: ML enables the creation of personalized experiences and recommendations, improving user engagement and satisfaction.

4. **Improved Decision Making**:
   - **Advantage**: By identifying patterns and trends in data, ML can support better decision-making and predictive analytics in various domains.

5. **Adaptability**:
   - **Advantage**: ML systems can adapt to new data and changing conditions, improving their performance over time without requiring explicit reprogramming.

6. **Anomaly Detection**:
   - **Advantage**: ML algorithms can identify unusual patterns or outliers, useful in areas like fraud detection and cybersecurity.

### Disadvantages of Machine Learning

1. **Data Dependency**:
   - **Disadvantage**: ML models require large amounts of high-quality data for training. Inadequate or biased data can lead to poor performance and unreliable results.

2. **Complexity**:
   - **Disadvantage**: Developing and tuning ML models can be complex and require expertise in data science, potentially leading to high development and maintenance costs.

3. **Overfitting**:
   - **Disadvantage**: ML models can become too specialized to the training data, resulting in overfitting where the model performs well on training data but poorly on new data.

4. **Lack of Transparency**:
   - **Disadvantage**: Many ML models, especially deep learning models, operate as "black boxes," making it challenging to understand how they arrive at specific decisions or predictions.

5. **Ethical Concerns**:
   - **Disadvantage**: ML applications can raise ethical issues, such as privacy concerns, bias in decision-making, and the potential for misuse.

6. **High Resource Consumption**:
   - **Disadvantage**: Training and deploying ML models can require significant computational resources and energy, which may be a concern for scalability and environmental impact.

### Clustering
- Process of sorting items into groups based on their similarities forming distant clusters where items within each cluster are more alike each other than to those in other cluster.
- entails discovering patterns without explicit guidance, akin to exploring a forest without a map , where similarities guide the grouping process. it's a form of unsupervised learning akin to solving a puzzle without knowledge of final solution.
- Unsupervised learning
![](../../statics/Pasted%20image%2020240902230300.png)
#### Clustering vs Classification

![](../../statics/Pasted%20image%2020240902230410.png)

#### Hierarchical clustering
![](../../statics/Pasted%20image%2020240902230639.png)![](../../statics/Pasted%20image%2020240902230735.png)
![](../../statics/Pasted%20image%2020240902230845.png)

### Reinforcement learning
- type of ML where an agent learns to make decisions by performing actions and receiving feedback in the forms of rewards or penalties. This method is similar to how individuals learn from consequences of their actions in real life.
- **Concepts:**
    - environments
    - state
    - actions
    - rewards

### Regression
- statistical technique used to analyze the relationship between dependent variable and one or more indepenent variable. it is widely used in areas like finance, economics , and more , to predict outcomes and undergoing variable interaction.
![](../../statics/Pasted%20image%2020240902232142.png)
![](../../statics/Pasted%20image%2020240902232307.png)

### K mean clustering

- K-Means Clustering is one of the most popular unsupervised learning algorithms used to partition a dataset into distinct groups, or clusters. The goal is to divide the data points into k clusters, where each data point belongs to the cluster with the nearest mean (centroid), resulting in clusters of similar data points.
- find centroid (prototype)(mean) of K cluster.
- **steps**
 - Randomly place K centroid.
 - assign each data point to its closest cluster.
 - update the centroid
#### stopping
- after some iteration.
- when centroid dont change.
- when few/no data point change cluster.

#### problems
- needs K: K-means requires the user to specify the number of clusters (K) in advance. This can be a drawback because the "correct" number of clusters is often not known beforehand. Choosing an inappropriate K can lead to poor clustering results. For example, if K is too low, distinct groups might be merged, while if K is too high, the algorithm might create clusters that are not meaningful. 
- outlier sensitive: K-means is sensitive to outliers because it uses the mean to calculate the center of a cluster. Outliers, which are data points that are significantly different from others, can skew the mean and, consequently, the position of the cluster center. This can result in poorly defined clusters, where some clusters may be heavily influenced by outliers rather than representing the true underlying structure of the data.
- hard clustering: K-means performs hard clustering, meaning each data point is assigned to exactly one cluster. This can be limiting when data points naturally belong to more than one cluster or when the boundaries between clusters are not clear. Hard clustering forces a strict division, which might not accurately reflect the data's true structure, especially in cases where clusters overlap.

#### 1. Key Concepts
- Clusters: Groups of similar data points.
- Centroid: The center of a cluster. Each centroid is the mean of all points in that cluster.
- Distance Measure: Typically, Euclidean distance is used to measure how close a data point is to a centroid.
#### 2. The K-Means Algorithm
- The K-Means algorithm follows these steps:

**Initialization:**

Select k, the number of clusters.
Randomly choose k initial centroids from the dataset.
Assignment Step:

Assign each data point to the nearest centroid. This forms k clusters.
Update Step:

Recalculate the centroids by taking the mean of all data points in each cluster.
Repeat:

Repeat the assignment and update steps until the centroids no longer change significantly, indicating convergence.
Final Clusters:

Once the centroids stabilize, the algorithm outputs the final clusters.

### Self organising map
- use processing units (neurons) to place centroid on an adjustable map , SOM.
- model self organize based on learning rules and interaction.
- processing units maintains proximity relationship as they grow.
![](../../statics/Pasted%20image%2020240904075919.png)
#### Goal
- find weight values such that adjacent units have similar values.
- input are assigned to units that are similar to them.
- each unit become center of a cluster.
- K-mean == constrained SOM! 

#### SOM (for exam)
A Self-Organizing Map (SOM) is an unsupervised learning algorithm used for clustering and visualizing high-dimensional data. It was introduced by Teuvo Kohonen in the 1980s and is sometimes referred to as a "Kohonen map."

##### **Key Concepts**

1. **Grid of Neurons:**
   - SOM consists of a grid (usually 2D) of neurons or nodes.
   - Each neuron is associated with a weight vector that has the same dimension as the input data.
   - The grid can be rectangular or hexagonal, where each neuron is connected to its neighbors.

2. **Training Process:**
   - **Initialization:** Neurons are initialized with random weight vectors.
   - **Input Data:** For each input data point:
     1. **Best Matching Unit (BMU):** The neuron with the weight vector most similar to the input data point is identified as the BMU.
     2. **Neighborhood Update:** The weights of the BMU and its neighboring neurons are adjusted to become more like the input data point. The amount of adjustment depends on the distance of the neuron from the BMU (closer neurons are adjusted more).
     3. **Learning Rate:** The learning rate and the neighborhood radius decrease over time, making the SOM converge.

3. **Topology Preservation:**
   - SOM preserves the topological relationships of the input data. Data points that are similar in the input space will map to neurons that are close to each other on the grid.
   - This makes SOM useful for visualizing complex, high-dimensional data in a 2D map.

4. **Dimensionality Reduction:**
   - SOM can be seen as a method of reducing the dimensionality of data while preserving its structure, making it easier to visualize and interpret.

##### **Applications of SOM**

1. **Data Visualization:**
   - SOM is often used to visualize complex, high-dimensional datasets. For example, it can be used to create a map of customer segments in marketing data.

2. **Clustering:**
   - SOM clusters data in an unsupervised manner, grouping similar data points together on the grid. Each neuron can be seen as representing a cluster of similar data points.

3. **Feature Mapping:**
   - SOM can be used to project data onto a lower-dimensional space, helping to identify patterns and structures within the data.

4. **Anomaly Detection:**
   - By mapping normal data to a SOM, anomalies can be detected by identifying data points that map to unusual or less frequently activated neurons.

##### **Advantages of SOM**

- **Topological Preservation:** SOM maintains the relationships between data points, making it great for visualization.
- **Interpretability:** The 2D grid structure allows for easy interpretation of the results.
- **Unsupervised Learning:** SOM doesn't require labeled data, making it useful in scenarios where labeled data is scarce or unavailable.

##### **Limitations of SOM**

- **Complexity:** Training SOM can be computationally intensive, especially with large datasets or large grids.
- **Fixed Grid Size:** The size of the grid must be decided beforehand, which can be challenging. A too-small grid might not capture all the data's nuances, while a too-large grid can be computationally expensive.
- **Static Clusters:** Once the SOM is trained, the clusters are static and may not adapt well to new data without retraining.
#### Numerical

##### **Step 1: Initial Setup**

 **Dataset**
We'll use a small dataset with 2-dimensional data points:
- Data Points: `[(0.1, 0.2), (0.8, 0.6), (0.3, 0.4), (0.9, 0.7)]`

**SOM Grid**
We'll create a 2x2 SOM grid with 4 neurons. Each neuron will have a weight vector initialized randomly. Let's assume the following initial weights:
- Neuron 1: `(0.2, 0.3)`
- Neuron 2: `(0.6, 0.9)`
- Neuron 3: `(0.4, 0.5)`
- Neuron 4: `(0.7, 0.8)`

##### **Step 2: Training Process**

We'll go through one iteration of training to see how SOM updates the neurons' weights.

**Iteration 1: Process Data Point (0.1, 0.2)**

1. **Find the Best Matching Unit (BMU):**
   - Calculate the Euclidean distance between the input `(0.1, 0.2)` and each neuron's weight vector:
     - Neuron 1: Distance = `√((0.1 - 0.2)² + (0.2 - 0.3)²) = √(0.01 + 0.01) = √0.02 ≈ 0.14`
     - Neuron 2: Distance = `√((0.1 - 0.6)² + (0.2 - 0.9)²) = √(0.25 + 0.49) = √0.74 ≈ 0.86`
     - Neuron 3: Distance = `√((0.1 - 0.4)² + (0.2 - 0.5)²) = √(0.09 + 0.09) = √0.18 ≈ 0.42`
     - Neuron 4: Distance = `√((0.1 - 0.7)² + (0.2 - 0.8)²) = √(0.36 + 0.36) = √0.72 ≈ 0.85`
   - **BMU:** Neuron 1 has the smallest distance (0.14), so it's the BMU.

2. **Update BMU and Neighboring Neurons:**
   - Assume a learning rate of `0.5` and a neighborhood radius that covers all neurons.
   - **Update Neuron 1 (BMU):**
     - New Weight = Old Weight + Learning Rate * (Input - Old Weight)
     - `(0.2, 0.3) + 0.5 * ((0.1, 0.2) - (0.2, 0.3)) = (0.2, 0.3) + (0.5 * (-0.1, -0.1)) = (0.2, 0.3) + (-0.05, -0.05) = (0.15, 0.25)`
   - **Update Neuron 2:**
     - New Weight = `(0.6, 0.9) + 0.5 * ((0.1, 0.2) - (0.6, 0.9)) = (0.6, 0.9) + 0.5 * (-0.5, -0.7) = (0.6, 0.9) + (-0.25, -0.35) = (0.35, 0.55)`
   - **Update Neuron 3:**
     - New Weight = `(0.4, 0.5) + 0.5 * ((0.1, 0.2) - (0.4, 0.5)) = (0.4, 0.5) + 0.5 * (-0.3, -0.3) = (0.4, 0.5) + (-0.15, -0.15) = (0.25, 0.35)`
   - **Update Neuron 4:**
     - New Weight = `(0.7, 0.8) + 0.5 * ((0.1, 0.2) - (0.7, 0.8)) = (0.7, 0.8) + 0.5 * (-0.6, -0.6) = (0.7, 0.8) + (-0.3, -0.3) = (0.4, 0.5)`

###### **New Weights After First Iteration:**
- Neuron 1: `(0.15, 0.25)`
- Neuron 2: `(0.35, 0.55)`
- Neuron 3: `(0.25, 0.35)`
- Neuron 4: `(0.4, 0.5)`

##### **Step 3: Repeat for Other Data Points**

The training process is repeated for each data point in the dataset. Each time, the BMU is found, and the weights of the BMU and its neighbors are updated. Over many iterations, the neurons' weights gradually adjust to represent the input data more accurately, and similar data points map to neurons that are close to each other on the grid.

##### **Final SOM After Training**
After multiple iterations, the weights of the neurons stabilize, and the grid reflects the structure of the data. Similar data points will be close together on the map, and you can use the SOM to visualize and cluster the data.

##### **Summary**

- **Input:** A set of 2D data points.
- **SOM Grid:** A 2x2 grid with neurons initialized with random weights.
- **Training:** For each data point, find the BMU, then update the BMU and its neighbors.
- **Result:** A map where similar data points are close together, providing a visual representation of the data's structure.

This simple example shows how SOM works by adjusting neuron weights to cluster and organize data in a way that preserves the relationships between the data points.

Here's a comparison between K-means and SOM in a table format:

| **Aspect**                      | **K-means**                                          | **Self-Organizing Map (SOM)**                   |
|---------------------------------|-----------------------------------------------------|-------------------------------------------------|
| **Clustering Approach**         | Partition-based, clusters data into `K` groups.     | Grid-based, organizes data into a 2D or 3D grid.|
| **Data Representation**         | Centroids represent the center of clusters.         | Neurons in the grid represent clusters.         |
| **Initialization**              | Requires specifying the number of clusters `K`.     | Requires specifying grid dimensions (e.g., 2x2).|
| **Assignment Type**             | Hard assignment: each data point belongs to one cluster. | Soft assignment: data points influence the BMU and its neighbors. |
| **Learning Process**            | Iteratively updates centroids by minimizing intra-cluster variance. | Iteratively updates neuron weights to reflect input data, preserving topological structure. |
| **Output**                      | Set of `K` distinct clusters.                       | A grid where similar data points map to nearby neurons. |
| **Topology Preservation**       | No preservation of topological relationships.       | Preserves topological relationships, mapping similar data points to nearby neurons. |
| **Sensitivity to Initialization**| High sensitivity to initial centroid positions.    | Less sensitive due to neighborhood adjustments. |
| **Convergence**                 | Typically faster, but results can vary based on initialization. | Slower, but usually provides a stable, structured output. |
| **Visualization**               | Produces distinct clusters without inherent structure. | Provides a structured, visual representation of data relationships. |
| **Flexibility**                 | Fixed clusters, requires re-running for new data.   | More flexible, grid adapts to new data over training. |
| **Common Applications**         | Market segmentation, document clustering, image compression. | Data visualization, pattern recognition, anomaly detection. |
| **Example Output**              | `K` clusters each represented by a centroid.        | A 2D grid where each neuron represents a cluster, with neighbors reflecting similar data. |
| **Scalability**                 | Scalable to large datasets, but limited by `K`.     | Can be computationally intensive, especially with large grids. |

## Overfitting and UnderFitting
**Overfitting and Underfitting** are common issues in machine learning models that relate to how well the model generalizes to unseen data.

### 1. **Overfitting**:
- **Definition**: Overfitting occurs when a model learns the training data too well, including noise and outliers, resulting in poor generalization to new, unseen data.
- **Symptoms**: High accuracy on training data but poor performance on test/validation data.
- **Cause**: The model is too complex, with too many parameters relative to the amount of training data.
- **Solution**:
  - Use simpler models (reduce model complexity).
  - Apply regularization techniques (e.g., L1, L2).
  - Gather more training data.
  - Use cross-validation to tune the model properly.

### 2. **Underfitting**:
- **Definition**: Underfitting occurs when a model is too simple to capture the underlying patterns in the data, resulting in poor performance on both training and test/validation data.
- **Symptoms**: Low accuracy on both training and validation/test data.
- **Cause**: The model has too few parameters or is not trained long enough, resulting in insufficient learning.
- **Solution**:
  - Use a more complex model.
  - Train for a longer period (increase epochs in neural networks).
  - Improve feature engineering to capture more relevant patterns.
  - Remove data noise that may interfere with learning. 

## Principal Component analysis
**Principal Component Analysis (PCA)** is a dimensionality reduction technique used to simplify complex datasets by transforming them into a new set of variables, called **principal components**, which capture the maximum variance in the data while reducing dimensionality.

### Key Concepts:

1. **Overfitting**:
   - In machine learning, overfitting occurs when a model is too complex and fits the noise in the data rather than generalizing to unseen data. PCA helps mitigate **overfitting** by reducing the number of input features (dimensionality) and focusing only on the most important ones. By keeping the principal components that explain the most variance, PCA removes less important, noisy features, which reduces model complexity and overfitting.

2. **Principal Components**:
   - **Principal components** are the new set of axes or variables created by PCA. These components are linear combinations of the original features, and they are ordered by the amount of variance they capture. The first principal component captures the most variance in the data, the second captures the next highest amount of variance orthogonal to the first, and so on. Only the most significant components are retained, simplifying the dataset while preserving its essential information.

3. **Orthogonous**:
   - Each principal component is **orthogonal** (perpendicular) to the others. This means that there is no correlation between the principal components. By ensuring orthogonality, PCA captures the variance in different directions of the data without overlap, making the components statistically independent from one another. This property ensures that each principal component captures unique information, further aiding in reducing overfitting.

### Summary:
PCA is useful for preventing **overfitting** in machine learning by reducing the dimensionality of the data. It identifies the most important **principal components**, which are **orthogonal** to one another, thus capturing the maximum variance in the data while ignoring noise and redundant information. This results in a simpler, more generalizable model.

### Numerical
#### 1. Calculate mean of each attribute
#### 2. create covariance matrix (if 2 attribute then 2X2 , if 3 attribute then 3X3 and so on).

If you have three attributes (or features) \(x\), \(y\), and \(z\), the **covariance matrix** will be a 3x3 symmetric matrix that represents the covariances between each pair of attributes.

![](../../statics/Pasted%20image%2020240907082423.png)


Where:
- **Cov(x, x)**, **Cov(y, y)**, and **Cov(z, z)** are the **variances** of \(x\), \(y\), and \(z\), respectively.
- **Cov(x, y)** = **Cov(y, x)** is the **covariance** between \(x\) and \(y\).
- **Cov(x, z)** = **Cov(z, x)** is the **covariance** between \(x\) and \(z\).
- **Cov(y, z)** = **Cov(z, y)** is the **covariance** between \(y\) and \(z\).

##### Covariance Formula:

For two variables \(a\) and \(b\), the covariance is calculated as:

![](../../statics/Pasted%20image%2020240907082318.png)

Where \( \bar{a} \) and \( \bar{b} \) are the means of the variables \(a\) and \(b\), respectively, and \(n\) is the number of observations.

#### 3. Finding eigen value 

![](../../statics/Pasted%20image%2020240907082106.png)

# UNIT 2

## Decision Tree

A Decision Tree is a supervised learning algorithm used for both classification and regression tasks. It splits the dataset into subsets based on the most significant features, forming a tree structure where each internal node represents a decision based on a feature, each branch represents an outcome of that decision, and each leaf node represents the final prediction.

![](../../statics/Pasted%20image%2020240907083712.png)
![](../../statics/Pasted%20image%2020240907084243.png)
