# Unit 1

## Intro
- Machine learning is defined as the subset of computer science, that aims to build and train models based on previous data/sample data to forecast or predict and decide without any functionality of explicit programming to do so

## Stages of Model Development in Ml
![](../../statics/Pasted%20image%2020241204104925.png)

- Problem Identification:- At this stage, a well thought questionnaire is prepared to understand the problem to be solved
- Data collection:- All the primary and secondary data sources of data collection are identified. The primary sources involve the processes of collecting data directly from the participants. On other hand, secondary data sources are the previously published datasets that may be re-utilized to train models for specific purposes.
- Data Cleaning and Preparation: The raw data collected in the previous stage may not be suitable for the training purposes. It may contain noise, null-values, outliers, etc. The data cleaning is done to handle such issues
- Data Visualization: Sometimes plotting the data into graph or representing it into the tabular format gives more useful insights
- Model Training: The model is trained with the previous dataset. The dataset consists of feature set and associated values
- Model Testing: After training of the model, the trained model is being tested for its performance in terms accuracy, standard error, mean square error, etc.
- Model Deployment: The model deployment relates to the actual implementation of the model for application purpose.

## Types of ML

### Supervised learning
- involves training a machine learning model using labeled data, which means the **data is already associated with correct answer**. 
  Eg: predicting house prices based on features like size and location, using a dataset where prices are known, allows the model to learn and make accurate predictions on new, unseen data.

#### Classification and Regression

The Supervised Machine Learning is categorized as: Classification and Regression.

##### Classification
- Classification is the supervised machine learning technique that targets to identify the correct category of the upcoming or new instance. It tries to set the possible accurate boundaries to maximize the difference between the available categories in the dataset. It includes classifiers such as decision trees, naïve bayes, rule-based classifiers, case-based reasoning, support vector machines etc.
- The classification algorithms are categorized into two categories namely: Lazy Learner and Eager Learners. 
	- The lazy learner holds the training data until test data appears. When it appears; it begins the classification process based on most related stored data. 
	- On other hand Eager Learners build the classification model based on the stored training data. Eager learners spend more time in training the model while lazy learners spend more time on prediction.
![](../../statics/Pasted%20image%2020241205114732.png)
- k-nearest neighbor:- it computes the 𝑘-nearest neighbors i.e., most similar instances from the training dataset. Each of the 𝑘 neighbors have a class label defined in the dataset. The label of test dataset will be predicted on the basis of the majority of labels among 𝑘- nearest neighbors. The similarity between new instance and training instances is calculated by computing the distance between them.
- ![](../../statics/Pasted%20image%2020241205121034.png)
 
##### Regression
- Regression means to comprehend the relationship between dependent and independent variables among the datasets. The most common use of regression is to generate prediction that gives the estimates, such as for a company's sales revenue, where the independent variable may be price of the product and company’s sales revenue will be dependent variable 


- Simple vs Multivariate regression
    - When the relationship is computed between one dependent and one independent variable; it is simple regression; when the relationship is computed between one dependent and multiple independent variable; for such cases it is multi-variate regression. For example, when happiness index is calculated in terms of income only; it is simple regression.if happiness index is calculated in terms of income, time-spent-with-family, health-status, etc., it is multi-variate regression.

**Linear vs Non-linear regression**

if the relationship between dependent and independent variable is either positive or negative i.e., a straight-line relation; it is referred to as linear regression as in. If the curve between dependent and independent variable is not a straight line, then it is non-linear regression as in.For prediction and forecasting, generally, linear regression model is used.

![](../../statics/Pasted%20image%2020241204115427.png)
![](../../statics/Pasted%20image%2020241204115438.png)

The simple linear equation is represented by the equation where 𝑎 and 𝑏 are regression coefficients that establishes the relationship between dependent variable 𝑦 and independent variable 𝑥.
    `y = a + bx`

Where,
y: The output label i.e., the category label.
𝑋: The feature set.
𝑎 and 𝑏: Regression coefficients. 𝑏 defines the slope that infers about the relative change in the dependent variable value with respect to independent variables’ value. b is known as intercept; it represents the value of dependent variable in the absence of independent variables.
Since, the data gathered may have clerical errors, noise or incorrect values etc. This may affect the accuracy of the regression estimate. Therefore, can be re-written with ɛ, the permissible error of the estimate (random error component).
𝑦 = 𝑏𝑋 + 𝑎 + ɛ

- Methods used too formulate regression equation.
    - Ordinary Least Square Method: This is an estimator method that computes the values of regression coefficients such that sum of squared residuals i.e., error in prediction is minimum. The sum of squared residuals is the difference between the observed dependent variable value and predicted dependent variable value.
    - Logistic Regression: This method builds a probabilistic regression model that computes the probability to predict that an instance belongs to a specific category. The linear regression assumes that data follows the linear function while logistic regression uses the sigmoid function given in equation.![](../../statics/Pasted%20image%2020241204120427.png)
    - Lasso and Ridge regression techniques are used to regularize the linear regression model to prevent the problem of over- fitting. The lasso and ridge regression aim to shrink the coefficients to reduce the model complexity and multi-collinearity

#### Regression vs classification
Here’s a detailed **10-point difference** between **Regression** and **Classification**:

| **Aspect**                   | **Regression**                                                    | **Classification**                                                                       |
| ---------------------------- | ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| **1. Output Type**           | Continuous numerical values (e.g., 12.5, 78.0).                   | Discrete class labels (e.g., "Cat", "Dog").                                              |
| **2. Objective**             | Predict a continuous quantity or value.                           | Predict the class or category of an object.                                              |
| **3. Example Problem**       | Predicting house prices, stock prices, temperature.               | Email classification (Spam/Not Spam), disease diagnosis (Healthy/Sick).                  |
| **4. Algorithms Used**       | Linear Regression, Polynomial Regression, SVR, etc.               | Logistic Regression, SVM, Decision Trees, k-NN, Naive Bayes.                             |
| **5. Evaluation Metrics**    | MAE (Mean Absolute Error), MSE (Mean Squared Error), R², RMSE.    | Accuracy, Precision, Recall, F1-Score, AUC-ROC.                                          |
| **6. Output Format**         | A real number or continuous output.                               | A class label (categorical value).                                                       |
| **7. Output Interpretation** | The output represents a real value on a continuous scale.         | The output represents membership in a specific class or category.                        |
| **8. Data Nature**           | Data used is continuous (e.g., temperature, height, weight).      | Data used is categorical (e.g., types of animals, disease state).                        |
| **9. Model Complexity**      | Tends to work with more complex relationships in data.            | Often focuses on boundaries or separations between classes.                              |
| **10. Use Case**             | Predicting quantities for business forecasting, price prediction. | Classifying items, detecting patterns, and decisions for action (e.g., fraud detection). |
#### Steps in Supervised learning
- input and output pairing:- each input is paired with its correct label.
- training:- model learns by compairing its prediction with actual label and adjusting itself to improve accuracy.
- error correction:- if model predicts incorrectly it adjusts its internal parameters to reduce error.
- outcome:- model eventually learn to map input to correct output.

**Examples**:
- **Classification**: Email spam detection, sentiment analysis, image classification.
- **Regression**: Predicting house prices, stock market forecasting, temperature prediction.

**Key Algorithms**:
- Linear Regression
- Logistic Regression
    - Decision Trees
- Support Vector Machines (SVM)
    - Neural Networks

### Unsupervised learning
- Unsupervised learning is the process of training a model to use the structure of a dataset to make decisions successfully without using labels. For example, if the same problem of house prediction is considered for the unsupervised learning, the dataset will not contain the furnishing status in the training data. Unsupervised learning with unlabelled is used to build a model that is fully input-based. When there is an increase in disproportionally rising disorganized unlabelled data, unsupervised learning is used in addition to labelled data.
- Eg: Imagine placing a mix of different coins on a table and asking to sort them. without explaining any criteria , the child might start grouping by size,color etc.
#### Clustering
- Clustering is an unsupervised form of machine learning that tends to find the clusters among the datasets. These clusters are the collections of similar data instances. The similarity is calculated on the basis of distance measures. The clustering algorithms may form clusters by partitioning approach or tree-based approach.
- ![](../../statics/Pasted%20image%2020241205122311.png)
#### K mean clustering
- 𝑘-means is a partitioning clustering technique that divides the dataset into 𝑘 clusters. The 𝑘 −means algorithm proceeds as follows:
- Step I. The clustering begins with randomly selecting 𝑘 centroids. Each centroid is represented by the feature vector. The centroid is assumed to be the centre of cluster.
- Step II. The distance is computed between each centroid and each data point in the dataset. The selected distance measure is applied on each attribute feature of the feature vector.
- Step III. The data points are grouped with the nearest centroids forming 𝑘 clusters.
![](../../statics/Pasted%20image%2020241205122543.png)

#### SOM(Self organising map)
- Self-organizing Feature Map is an unsupervised machine learning technique that creates a low- dimensional (usually two-dimensional) representation of a higher-dimensional data collection while maintaining the topological structure of the data. It helps to easily visualize higher dimensional data.
- 
**Key Algorithms**:
- K-Means Clustering
    - Hierarchical Clustering
- Principal Component Analysis (PCA)

#### Steps 
- input without labels:- the model receives data without any explicit instructions on what to do with it.
- pattern recognition:- model analyze data and tries to find any natural grouping or patterns.
- self-organisation:- model organise data into different categories based on the patterns it receives.
- outcome:- model creates its own system of categorization without external guidance.

### Semi-supervised learning
- Semi-supervised learning is a branch of machine learning that focuses on using both labelled and unlabelled data to implement particular learning algorithms. Conceptually positioned halfway within unsupervised and supervised learning, this permits the usage of the considerable amounts of unlabelled data present from several use cases in addition to the more prevalent smaller clusters of annotated data. When there is a lack of labelled data, semi-supervised classification approaches are quite helpful.

### **Reinforcement Learning**
- Reinforcement learning means learning from experiences. It is concerned with intelligent agents and their actions in the environment to maximize collective reward . It is widely used in self-driving car, fraud detection, etc.

![](../../statics/Pasted%20image%2020241204111329.png)

**Examples**:
- **Game Playing**: Training AI to play games like chess, Go, or video games.
- **Robotics**: Teaching robots to navigate environments or perform tasks.
- **Recommendation Systems**: Adaptive recommendation systems that improve over time based on user interactions.

**Key Algorithms**:
- Q-Learning

## SOM
https://www.youtube.com/watch?v=DsYm4Tlr1rw&t=153s

### **Definition**
- **Self-Organizing Maps (SOM)** are unsupervised learning algorithms used for dimensionality reduction and data visualization.
- SOM organizes high-dimensional data into a 2D grid while preserving the topological structure of the data.

### **Key Characteristics**

1. **Unsupervised Learning**:
    
    - Does not require labeled data.
    - Identifies patterns and relationships in the data based on similarity.
2. **Topology Preservation**:
    
    - Nearby nodes on the SOM grid represent data points that are similar in the input space.
3. **Dimensionality Reduction**:
    
    - Converts high-dimensional input data into a simpler, interpretable 2D map.

### **Components**

1. **Input Layer**:
    
    - Accepts the high-dimensional input vector.
2. **Output Layer**:
    
    - A 2D grid of neurons (nodes) where each node has a weight vector of the same dimension as the input vector.
3. **Weights**:
    
    - Each neuron in the grid is associated with a weight vector that adapts during training.

### **How SOM Works**

1. **Initialization**:
    
    - Weight vectors of neurons are initialized (randomly or heuristically).
2. **Input Matching**:
    
    - For each input, the **Best Matching Unit (BMU)** is identified as the neuron whose weight vector is closest to the input vector.
3. **Weight Update**:
    
    - The BMU and its neighboring neurons adjust their weights to resemble the input vector.
    - Adjustment strength decreases with time and distance from the BMU.
4. **Iteration**:
    
    - Steps are repeated for all input data until convergence.

### **Applications**

1. **Data Clustering**:
    
    - Grouping similar data points (e.g., customer segmentation).
2. **Data Visualization**:
    
    - Reducing dimensions to visualize clusters and patterns in datasets.
3. **Feature Extraction**:
    
    - Identifying key features in high-dimensional data.
4. **Anomaly Detection**:
    
    - Identifying outliers by analyzing distant BMUs.
5. **Biological and Medical Data Analysis**:
    
    - Analyzing gene expression data or MRI scans.

### **Advantages**

1. No need for labeled data.
2. Maintains relationships between data points.
3. Suitable for high-dimensional data.
4. Can detect clusters and patterns.


### **Disadvantages**

1. Requires careful tuning of hyperparameters (e.g., learning rate, neighborhood function).
2. Computationally intensive for large datasets.
3. Limited scalability for very high-dimensional data.

## PCA

## Dimension reduction
It involves reducing the number of features (dimensions) in the data while retaining essential patterns, relationships, and structures that are important for the learning process.

### Why Dimensionality Reduction is Important in Machine Learning

1. **Curse of Dimensionality**: As the number of dimensions increases, the volume of the feature space grows exponentially, making the data sparse and harder for algorithms to generalize.
2. **Improved Model Performance**: Reducing irrelevant or redundant features can prevent overfitting and lead to more accurate models.
3. **Computational Efficiency**: Fewer dimensions mean faster training and inference times.
4. **Visualization**: Dimensionality reduction allows complex, high-dimensional data to be visualized in 2D or 3D, aiding in insights and exploratory analysis.

### Techniques in Machine Learning

#### 1. **Feature Selection**

Selects a subset of the original features without altering them. It retains the most important features based on specific criteria.

- **Filter Methods**: Use statistical techniques like correlation or mutual information.
- **Wrapper Methods**: Iteratively evaluate feature subsets using the model's performance (e.g., Recursive Feature Elimination).
- **Embedded Methods**: Perform feature selection as part of the model training (e.g., Lasso Regression for regularization).

#### 2. **Feature Extraction**

Transforms data into a lower-dimensional space, creating new features that capture the most critical information.

- **Linear Techniques**:
    - **Principal Component Analysis (PCA)**: Projects data onto a lower-dimensional subspace that maximizes variance.
    - **Singular Value Decomposition (SVD)**: Factorizes data into matrices for dimensionality reduction.
    - **Linear Discriminant Analysis (LDA)**: Finds linear combinations of features that separate classes.
- **Non-Linear Techniques**:
    - **t-SNE (t-Distributed Stochastic Neighbor Embedding)**: Reduces dimensions while preserving local data structure, suitable for visualization.
    - **UMAP (Uniform Manifold Approximation and Projection)**: Similar to t-SNE but faster and preserves more global structure.
    - **Autoencoders**: Neural networks designed to learn efficient representations of data.

### Applications in Machine Learning

1. **Data Preprocessing**: Simplifies datasets before training machine learning models.
2. **Clustering**: Improves the quality of clustering algorithms like k-means or DBSCAN by reducing noise and redundant features.
3. **Classification/Regression**: Helps build better predictive models by focusing on meaningful features.
4. **Anomaly Detection**: Identifies unusual patterns in a reduced feature space.

### Challenges

- **Choosing the Right Technique**: The effectiveness of a method depends on the data and the problem.
- **Trade-off Between Dimensionality and Information**: Reducing dimensions too much can lead to loss of critical information.
- **Interpretability**: Transformed features in techniques like PCA or autoencoders may not have intuitive meanings.

Dimensionality reduction helps create efficient, interpretable, and high-performing machine learning models.


## Performance measure of learning
1. Generality:- refers to ML model's ability to perform well accross various datasets and environment, not just one it was trained on.
2. Efficiency:- How quickly a model can learn from data. A spam detection algorithm that quickly adapts to new type of spam emails
3. Robustness:- ability of a model to handle errors, noise and unexcpected data without failing. A voice recognition system able to recognize voice in a noisy room.
4. Efficacy:- overall effectiveness of a ML model in performing its intended tasks.
5. Ease of implementation:- how straightforward is it to develop and deploy a ML model.



## Application of ML

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

## Advantages of Machine Learning

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

## Disadvantages of Machine Learning

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

## Learning Association
- Associations refer to the relationship between different variables or features that define the data. Learning of these associations is done via rule-based machine learning algorithms and data mining techniques. The process of finding significant relationship among attributes is known as association learning. This involves evaluating degree of similarity, identification of hidden relationships in the databases.

### Methods of learning association
- Apriori Algorithm: The algorithm works better on the transaction-based data. It produces the association rules by leveraging the common datasets. This approach effectively calculates the frequent item sets taken together by using a breadth-first search or a hash tree-based approach. 
- Eclat algorithm: Eclat stands for the Equivalence Class Transformation. This algorithm uses the Depth-First Search (DFS) to search a transaction database for frequent item-sets
- F-P Growth Algorithm: F-P growth algorithm organizes the database as a common pattern or tree. This frequent tree is used to identify the most frequent patterns

### Regression
- statistical technique used to analyze the relationship between dependent variable and one or more indepenent variable. it is widely used in areas like finance, economics , and more , to predict outcomes and undergoing variable interaction.
![](../../statics/Pasted%20image%2020240902232142.png)
![](../../statics/Pasted%20image%2020240902232307.png)

### K mean clustering

#### problems
- needs K: K-means requires the user to specify the number of clusters (K) in advance. This can be a drawback because the "correct" number of clusters is often not known beforehand. Choosing an inappropriate K can lead to poor clustering results. For example, if K is too low, distinct groups might be merged, while if K is too high, the algorithm might create clusters that are not meaningful. 
- outlier sensitive: K-means is sensitive to outliers because it uses the mean to calculate the center of a cluster. Outliers, which are data points that are significantly different from others, can skew the mean and, consequently, the position of the cluster center. This can result in poorly defined clusters, where some clusters may be heavily influenced by outliers rather than representing the true underlying structure of the data.
- hard clustering: K-means performs hard clustering, meaning each data point is assigned to exactly one cluster. This can be limiting when data points naturally belong to more than one cluster or when the boundaries between clusters are not clear. Hard clustering forces a strict division, which might not accurately reflect the data's true structure, especially in cases where clusters overlap.

#### 1. Key Concepts
- Clusters: Groups of similar data points.
- Centroid: The center of a cluster. Each centroid is the mean of all points in that cluster.
- Distance Measure: Typically, Euclidean distance is used to measure how close a data point is to a centroid.
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
### Intro
A decision tree is the simplest and extremely understandable categorization or classification
approach. It is a powerful supervised machine learning algorithm that has a hierarchy based-tree like structure, whose leaf nodes contains the class labels; root node and internal node represents the attribute test or split test. The results of attribute test i.e., decisions are represented by the branches, therefore it referred to as decision tree.

![](../../statics/Pasted%20image%2020241207103537.png)
### Steps 
1. Start by identifying the feature or attribute that will best distinguish between the classes using the complete dataset. Metrics like computing information gain or the Gini index are used to identify the finest trait.
2. After identifying the finest characteristic, split the data collection into two (or more) parts of the attribute value based on split test results.
3. If a part of the dataset only contains labels for a class, the process stops here and designate it as the leaf node i.e., class label. 
4. This procedure is repeated until we have all leaf nodes, that contain information from the same class. The finalize decision tree algorithm’s model is shown in a flowchart.

### Benefits of Decision Trees in Machine Learning

1. **Interpretability**: Decision trees are easy to understand and interpret, even for non-technical stakeholders. They visually represent decisions, making them intuitive.
2. **Feature Selection**: Decision trees inherently perform feature selection by splitting the data based on the most significant attributes at each node.
3. **Non-linear Relationships**: They can model non-linear relationships effectively without requiring transformations of input data.
4. **Versatility**: Decision trees can handle both numerical and categorical data, making them flexible for a wide range of applications.
5. **No Need for Scaling**: They don’t require feature scaling or normalization, simplifying data preprocessing.
### Limitations of Decision Trees in Machine Learning

1. **Overfitting**: Decision trees can easily overfit the training data, especially when they grow too deep.
2. **Instability**: Small changes in the data can lead to entirely different splits, making the model unstable.
3. **Bias towards Dominant Features**: They can be biased when certain features dominate due to imbalanced data.
4. **Poor Performance on Large Datasets**: Single decision trees might not perform well on large and complex datasets compared to ensemble methods like random forests.
5. **Limited Predictive Power**: Alone, decision trees often yield lower predictive accuracy compared to more sophisticated models like gradient boosting or neural networks.

### Appropriate problem for decision tree algo
Decision tree has wide scope capabilities to solve the problems defines with following characteristics.

1. **Instances have attribute-value pairs**:  
   Each example is described by some properties (like "Temperature") and their values (like "Hot" or "Cold"). Decision trees work well when these values are distinct, but they can also handle numbers (e.g., 30°C) if needed.

2. **The output is usually a fixed set of categories**:  
   Decision trees are good for problems where the result falls into specific groups (like "Yes" or "No"). They can also work with more groups (like "Low," "Medium," "High") or even numbers, but that’s less common.

3. **They handle "OR" conditions**:  
   Decision trees can naturally describe situations where something happens under one condition **OR** another (e.g., "It's a good day if it's sunny **OR** warm").

4. **They can handle errors in data**:  
   Even if the data has mistakes (like a wrong label or value), decision trees can still figure out the right patterns most of the time.

5. **They can deal with missing information**:  
   If some examples are missing a value (like "Humidity" not recorded for some days), decision trees can still work and make decisions based on the available data.

### Entropy Measure
![](../../statics/Pasted%20image%2020241206124449.png)


![](../../statics/Pasted%20image%2020240907083712.png)
![](../../statics/Pasted%20image%2020240907084243.png)

## Regression
### some typical applications for machine learning regression models
- Forecasting a continuous result, such as stock prices, sales, or property values.
- Estimating the success of future retail or marketing initiatives in order to ensure that resources are used efficiently.
- Predict user or customer behaviour on webpages that sell goods or offer streaming services, etc.
- Evaluating data sets to discover the connections between factors and outcomes.
- Calculating interest rates or stocks value based on a diversity of factors.
- Data visualisation for time series.
### Multiregression
- To predict the outcome of a parameter according to the values of two or more additional components, a statistical technique called multiple linear regression is utilised.
![](../../statics/Pasted%20image%2020241206120126.png)


# UNIT 3
## ANN

### Intro / Neural network representation
- An **Artificial Neural Network (ANN)** is a computational model inspired by the structure and functioning of biological neural networks in the human brain. It is composed of interconnected units called **neurons** or **nodes**, which process data by simulating the way neurons signal each other in biological systems.
![](../../statics/Pasted%20image%2020241207100213.png)

An effective neural network has three key layers:
1. Input layer: This layer accepts all inputs from the programmer, as the name would imply.
2. Hidden Layers: These are located between the input layer & the output layer. This is the layer where the computations that produce the output are done.
3. Output Layer: The output is finally supplied via this layer after the inputs undergo a number of changes via the hidden layer
#### Activation function
- it apply a non-linear transformation and decide whether a neuron should be activated or not.
- ![](../../statics/Pasted%20image%2020241207101538.png)
- ![](../../statics/Pasted%20image%2020241207101601.png)
- ![](../../statics/Pasted%20image%2020241207101749.png)
- ![](../../statics/Pasted%20image%2020241207101805.png)

#### Cost function
A **cost function** is a mathematical function that measures the **error** between the predicted values of a machine learning model and the actual target values. It quantifies how well or poorly the model performs.
##### **Purpose of the Cost Function**
- To guide the **optimization process** by providing a scalar value representing the model's performance.
- The goal of training is to **minimize the cost function** by adjusting the model parameters (weights and biases).
##### **types of Cost Functions**

![](../../statics/Pasted%20image%2020241207104309.png)


---


## Appropriate problem for Neural network

1. **Real-Valued Output**:
    
    - The target function (the concept to be learned) can be represented as a real-valued function.
    - Data used for training and predictions involve real numbers, which can include Boolean values (e.g., true/false mapped to +1/-1), integers, or vectors.
2. **Time-Intensive Training**:
    
    - ANNs require longer training times compared to simpler models like decision trees.
    - Training time depends on factors like the number of examples, learning rate, and network complexity.
    - Training duration can vary from minutes to hours.
3. **Opaque Decision-Making**:
    
    - ANNs act like "black boxes," making it hard to interpret how they perform categorizations.
    - Human understanding of the internal computations is not necessary for many tasks.
4. **Fast Evaluation After Training**:
    
    - Once trained, ANNs can quickly evaluate inputs for their intended purpose.
    - For example, an ANN trained to classify objects (e.g., bus, car, tank) can make quick decisions, which is vital in time-critical scenarios like avoiding collisions.


## Perceptron
- A **perceptron** is one of the simplest types of artificial neural networks, designed to simulate how neurons in the human brain process information. It is a foundational concept in machine learning and artificial intelligence.
- A perceptron takes several **inputs**, processes them through **weighted connections**, and produces a **binary output** (e.g., 0 or 1).
- It acts like a simple **binary classifier**.

### Types
- Single layer: Single layer perceptron can only learn a single label pattern.
- Multilayer: Multilayer perceptrons have the ability to process information from two or more layers and comprehend it. The Perceptron approach determines a linear decision boundary by learning the weights for the input signals. 

![](../../statics/Pasted%20image%2020241207111417.png)
Single layer 


![](../../statics/Pasted%20image%2020241207110241.png)

### Characteristics of perceptron model
1) It's an algorithm for machine learning that makes use of binary classifiers that are learned under supervision.
2) The weighted coefficient is automatically learnt in a perceptron.
3) Weights are first compounded by input features before choosing whether to activate a neuron or not.
4) To establish if a function is more significant than zero, the activation function employs a step rule.
5) In order to distinguish between two linearly separable classes, +1 and -1, linear decision boundaries are drawn.
6) They must have output signals if the total of all input values is greater than the threshold value; otherwise, no outputs will be displayed.
### Advantages
Advantages:
- Multi-layered perceptron models are capable of resolving complex nonlinear problems.
- For both little and large input data, it functions well.
- After training, help us in making quick predictions.
- Enables the achievement of a comparable accuracy ratio for both large and small data.

### Disadvantages:
- The computations of multi-layered perceptron models are difficult and time-consuming.
- It is challenging to predict the extent to which each independent variable is influenced by the dependent variable.
- The effectiveness of the model depends on how well it was trained.
### Perceptron rule (video)
## Gradient descent , difference threshold remaining

![](../../statics/Pasted%20image%2020241217162532.png)
![](../../statics/Pasted%20image%2020241217162608.png)
![](../../statics/Pasted%20image%2020241217163210.png)
![](../../statics/Pasted%20image%2020241217163242.png)
![](../../statics/Pasted%20image%2020241217163304.png)
![](../../statics/Pasted%20image%2020241217163321.png)
![](../../statics/Pasted%20image%2020241217163431.png)
![](../../statics/Pasted%20image%2020241217163453.png)
![](../../statics/Pasted%20image%2020241217163534.png)

#### Differentiable threshold unit

A **Differentiable Threshold Unit (DTU)** is an alternative to traditional activation functions or threshold-based functions in machine learning that allows gradients to flow through during backpropagation. It is particularly useful when dealing with thresholding operations that are non-differentiable, like **step functions**, which block gradient flow.

 **1. Background and Motivation**

- In machine learning, threshold functions like the Heaviside step function output discrete values (0 or 1) based on an input threshold.
- These functions are **non-differentiable**, which makes them incompatible with gradient-based optimization techniques like backpropagation used in deep learning.
- A Differentiable Threshold Unit (DTU) approximates the behavior of a threshold while being smooth and differentiable.

 **2. Core Idea**

- The DTU introduces a smooth, differentiable approximation of a **hard threshold function**.
- It replaces the abrupt change with a **smooth transition** using a continuous function (e.g., sigmoid, tanh, or a custom soft-thresholding function).
- This allows for gradient computations and enables optimization via **gradient descent**.

 **3. Examples of Differentiable Threshold Functions**

Below are common differentiable approximations of threshold functions:
![](../../statics/Pasted%20image%2020241217164009.png)
 
 **4. Applications**

- **Binary Classification**: DTUs can approximate the decision boundary for binary output tasks.
- **Sparse Learning**: In sparse coding, soft thresholding is used for shrinkage to encourage sparsity.
- **Neural Networks**: Used as activation functions to model threshold-like behavior without losing differentiability.

 **5. Key Properties**

- **Smoothness**: The DTU is smooth and differentiable, enabling gradient flow.
- **Sharpness**: By tuning parameters (like kk in sigmoid/tanh), the approximation can closely mimic hard thresholds.
- **Gradient Flow**: DTUs allow gradients to propagate backward through threshold operations.

 **6. Challenges**

- **Sharpness vs. Smoothness Tradeoff**: Making the threshold sharper (higher kk) can lead to numerical instability.
- **Approximation Error**: There is always a tradeoff between fidelity to the true hard threshold and smoothness.


# UNIT 4
## Bayesian learning

### Conditional probability

Conditional probability is the probability of an event occurring given that another event has already occurred. It quantifies how the probability of an event changes when we have additional information.

#### Formula

The conditional probability of event AA given event BB is denoted as P(A∣B)P(A|B), and is defined as:

![](../../statics/Pasted%20image%2020241209094028.png)


![](../../statics/Pasted%20image%2020241209094059.png)
![](../../statics/Pasted%20image%2020241209094127.png)![](../../statics/Pasted%20image%2020241209094127%201.png)

#### Examples

![](../../statics/Pasted%20image%2020241209094209.png)

### Bayes’ Theorem in Machine Learning

Bayes' Theorem is a fundamental concept in probability theory that provides a way to update the probability of a hypothesis based on new evidence. It forms the backbone of several machine learning algorithms, especially in probabilistic models.

#### Formula
![](../../statics/Pasted%20image%2020241209094532.png)

#### Steps in Bayes' Theorem

1. **Start with Prior**: Define initial belief P(H) about the hypothesis.
2. **Incorporate Likelihood**: Determine how likely the observed evidence (P(E∣H) is under the hypothesis.
3. **Normalize**: Adjust probabilities based on all possible hypotheses P(E).

#### Applications in Machine Learning

1. **Naive Bayes Classifier**:
    - Assumes feature independence.
    - Used in text classification, spam detection, sentiment analysis.
    - Computes posterior probabilities for class labels and chooses the one with the highest value.
2. **Bayesian Networks**:
    - Graphical models representing probabilistic relationships among variables.
    - Used in decision-making and reasoning under uncertainty.
3. **Bayesian Inference**:
    - Updates model parameters as new data becomes available.
    - Common in probabilistic programming and hierarchical models.
4. **Generative Models**:
    - Utilizes P(E∣H) to generate new samples from learned distributions.


### Naive Bayes Classifier (Pending)

The **Naive Bayes** classifier is a probabilistic machine learning model based on **Bayes' Theorem**, used for classification tasks. It is called _naive_ because it makes a simplifying assumption that the features (or attributes) used to predict the class are **conditionally independent** given the class label. Despite its simplicity and the assumption of independence, it often performs surprisingly well in many real-world applications, such as text classification, spam detection, and sentiment analysis.

#### Key Concepts

1. **Bayes' Theorem**
2. **Independence Assumption**: The _naive_ assumption is that all features are independent given the class. 
3. **Class Prediction**: The goal of the Naive Bayes classifier is to predict the class label C for a given feature vector X. The class with the highest posterior probability is selected:

#### Types of Naive Bayes Classifiers

1. **Gaussian Naive Bayes**:
    
    - Assumes that the features are normally distributed (Gaussian distribution) for each class.
    - Useful when features are continuous and have a bell-shaped distribution
2. **Multinomial Naive Bayes**:
    
    - Typically used for discrete features, like word counts in text classification problems (e.g., spam detection).
    
3. **Bernoulli Naive Bayes**:
    
    - Similar to multinomial Naive Bayes, but assumes binary/boolean features (e.g., the presence or absence of a feature).

    This is often used in binary classification or when features are binary.
    

#### Advantages of Naive Bayes

1. **Simple and Fast**:
    
    - The classifier is easy to implement and computationally efficient, especially for large datasets.
    - It requires only a small amount of training data to estimate the parameters (priors and likelihoods).
2. **Works Well with High-Dimensional Data**:
    
    - Naive Bayes performs particularly well in high-dimensional spaces, such as text classification tasks where the number of features (words) can be large.
3. **Handles Missing Data**:
    
    - Since it independently considers each feature, it can handle missing data by ignoring those features during classification.
4. **Effective for Categorical and Continuous Data**:
    
    - Naive Bayes can handle both types of data by using the appropriate model (Gaussian, multinomial, or Bernoulli).

#### Disadvantages of Naive Bayes

1. **Independence Assumption**:
    
    - The assumption of conditional independence of features is often unrealistic in many real-world datasets, which can lead to suboptimal performance when features are correlated.
2. **Sensitive to Imbalanced Data**:
    
    - If the class distribution is highly imbalanced, Naive Bayes may be biased toward the majority class.
3. **Limited Flexibility**:
    
    - Naive Bayes does not model complex relationships between features, which can limit its ability to handle more complex decision boundaries.

#### Applications

1. **Text Classification**:
    
    - Spam detection, sentiment analysis, and document classification are common uses, especially with the multinomial or Bernoulli Naive Bayes model.
2. **Medical Diagnosis**:
    
    - Classifying diseases based on symptoms or medical test results.
3. **Recommendation Systems**:
    
    - Used in systems that recommend products or services based on user preferences.
4. **Real-Time Prediction**:
    
    - Due to its simplicity and speed, Naive Bayes is often used in applications requiring real-time predictions.

### Key Takeaways

- **Naive Bayes** is a fast and efficient classification algorithm based on Bayes' Theorem and the assumption of feature independence.
- It is particularly useful for large, high-dimensional datasets and applications like text classification.
- Despite its "naive" independence assumption, Naive Bayes can perform well in many practical scenarios, especially when the independence assumption holds reasonably true.


![](../../statics/Pasted%20image%2020241209095724.png)


