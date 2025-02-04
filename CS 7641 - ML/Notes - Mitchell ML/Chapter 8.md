# Chapter 8 - Instance-Based Learning

## 8.1 Introduction

Instance-based learning methods, such as nearest neighbor and locally weighted regression, approximate target functions by storing training data and retrieving similar instances when classifying new queries. Unlike other approaches, they construct localized approximations to the target function rather than a global model, making them well-suited for complex functions that can be broken into simpler local patterns.

Case-based learning extends this concept by using symbolic representations and has been applied in fields like legal reasoning, help desks, and scheduling. However, instance-based methods come with challenges, including high classification costs due to on-the-fly computation and inefficiencies when dealing with irrelevant attributes.

The chapter introduces k-Nearest Neighbor (k-NN) and its variants, followed by locally weighted regression, which generalizes k-NN by constructing local function approximations. Radial basis function networks serve as a bridge between instance-based and neural network methods. Case-based reasoning is also discussed, particularly its application in engineering design. Finally, the chapter contrasts lazy learning methods, which defer computation until classification, with eager learning methods that construct models in advance.

## 8.2 k-Nearest Neighbor Learning

The k-Nearest Neighbor (k-NN) algorithm is a fundamental instance-based learning method that classifies instances based on their proximity in an n-dimensional space, typically using Euclidean distance. The algorithm can be used for both discrete and continuous target functions.

For discrete-valued classification, k-NN assigns a new instance the most common class among its k nearest neighbors. When k=1, it simply takes the class of the closest training example. For larger k values, it determines the majority vote among the k nearest neighbors. The decision boundary formed by 1-NN consists of convex polyhedra around training instances, known as a Voronoi diagram.

For continuous-valued target functions, k-NN estimates the target value by averaging the values of the k nearest training examples rather than selecting the most common value.

The chapter introduces visual examples, demonstrating how different values of k influence classification results and decision boundaries.

### 8.2.1 Distance-Weighted k-Nearest Neighbor Algorithm

A refinement of the k-Nearest Neighbor (k-NN) algorithm involves weighting the influence of each neighbor based on its distance from the query point. Closer neighbors are given greater weight, typically using the inverse square of their distance. This adjustment enhances classification accuracy, particularly when neighbors vary significantly in distance from the query point.

For discrete-valued target functions, each neighbor's vote is weighted accordingly, ensuring that if the query point exactly matches a training instance, it takes on that instance's classification. In the case of real-valued target functions, a similar weighting scheme is applied, normalizing the contributions of different neighbors.

While standard k-NN considers only the k nearest neighbors, distance-weighted k-NN can be extended to include all training examples, as more distant points contribute minimally. This global approach, known as Shepard’s method, differs from the traditional local method that restricts influence to only k neighbors. The trade-off of the global method is increased computational cost.

### 8.2.2 Remarks on k-Nearest Neighbor Algorithm

The distance-weighted k-Nearest Neighbor (k-NN) algorithm is a powerful inductive inference method, robust to noisy data and effective with a large training set. By averaging the contributions of the k nearest neighbors, it smooths out the influence of isolated noisy instances.

The algorithm’s inductive bias assumes that the classification of a new instance is most similar to nearby instances in Euclidean distance. However, a key challenge in k-NN is its reliance on all instance attributes when computing distances. If many irrelevant attributes exist, they can dominate the similarity metric, leading to misleading results—this issue is known as the curse of dimensionality.

To address this, one approach is weighting attributes differently when calculating distances, effectively stretching or shrinking the axes in Euclidean space. The optimal weights can be determined using cross-validation, minimizing classification error. A more extreme solution is to eliminate irrelevant attributes altogether using methods like leave-one-out cross-validation.

Another practical concern is computational efficiency. Since k-NN classifies queries in real-time, identifying nearest neighbors can be expensive. Indexing methods like kd-trees improve efficiency by structuring training instances hierarchically, allowing faster neighbor searches at the cost of additional memory.

### 8.2.3: A Note on Terminology

In the study of nearest-neighbor methods and weighted local regression, several key terms from statistical pattern recognition are commonly used:

- **Regression** refers to the process of approximating a real-valued target function.
- **Residual** is the error between the predicted function \( f(x) \) and the true target function \( f^*(x) \).
- **Kernel function** is a function of distance that determines the weight assigned to each training example. It is denoted as \( K \), where \( w_i = K(d(x_i, x_q)) \), meaning that closer training examples have a higher influence on predictions.

## 8.3 Locally Weighted Regression

Locally weighted regression is an extension of nearest-neighbor approaches that constructs an explicit approximation of the target function \( f(x) \) over a local region around a query point \( x_q \). Unlike standard nearest-neighbor methods, which estimate \( f(x) \) at a single point, locally weighted regression builds a localized function using nearby or distance-weighted training examples.

The approach is termed:
- **Local** because it only considers data near the query point.
- **Weighted** since training examples are weighted based on their distance from the query point.
- **Regression** because it approximates real-valued functions.

A new function approximation \( \hat{f} \) is generated for each query instance and then discarded, as a new local model is created for each prediction.

### 8.3.1 Locally Weighted Linear Regression

In locally weighted linear regression, the target function \( f \) is approximated near a query point \( x_q \) using a linear function. The goal is to find coefficients for the linear function by minimizing the error for a local set of training examples, rather than a global set. Three criteria for minimizing error are presented:

1. **Minimize squared error over the k nearest neighbors.**
  ![image](https://github.com/user-attachments/assets/d40d7241-5d8c-46b6-8330-532a1b90ab9f)

3. **Minimize squared error over all training examples, weighted by distance from \( x_q \).**
  ![image](https://github.com/user-attachments/assets/80a1d36b-7e4a-4b81-b3f4-db2e8ee1e7d0)

5. **Combine the first two criteria, using a weighted approach over the k nearest neighbors, which reduces computational cost.**
![image](https://github.com/user-attachments/assets/181643cf-e156-43bb-8619-2c60cffbb2e6)

When applying the third criterion, the gradient descent rule is modified to include a distance penalty for each training example’s contribution. This method allows more efficient approximations using simpler methods than gradient descent.

### 8.3.2 Remarks on Locally Weighted Regression

Locally weighted regression uses simple functional forms like constant, linear, or quadratic functions to approximate the target function. More complex functions are generally avoided due to high computational costs, and because simpler functions can model the target function well over small regions of the instance space.

## 8.4 Radial Basis Functions (RBF)

Radial Basis Function (RBF) networks are a method of function approximation that is closely related to distance-weighted regression and artificial neural networks. The learned hypothesis in RBF is based on kernel functions that decrease with distance from a given point. The most common kernel function is the Gaussian function, centered at a point and with a specific variance.

RBF networks are typically trained in two stages:
1. **First stage**: The number of hidden units (kernel functions) is determined, and each unit is defined by choosing the center and variance for its kernel.
2. **Second stage**: The weights of the kernel functions are trained to fit the training data by minimizing the global error.

RBF networks can use different strategies for selecting kernel centers. One method allocates a Gaussian kernel for each training example, while another uses fewer kernel functions spaced uniformly or non-uniformly across the instance space. The use of unsupervised clustering methods, such as the EM algorithm, can help choose the kernel centers based on the distribution of instances.

Overall, RBF networks provide a global approximation to a target function by combining local kernel functions. Their key advantage lies in their efficient training process, as the input and output layers are trained separately.

## 8.5 Case-Based Reasoning

Case-based reasoning (CBR) is an instance-based learning method that differs from traditional k-nearest neighbor methods by using rich symbolic descriptions of cases instead of real-valued points in Euclidean space. CBR systems, like CADET, are often applied to fields such as conceptual design, legal reasoning, and problem-solving by reusing and combining previous solutions. In CBR, instances are represented by detailed, symbolic descriptions, and cases are retrieved based on their relevance to new queries. When an exact match isn't found, CBR systems use subgraph isomorphisms or other techniques to match partial cases and construct solutions. 

For example, CADET assists in the design of mechanical devices by matching function graphs of new design problems to stored cases. If an exact match isn't found, the system searches for subgraph matches and uses knowledge-based reasoning to adjust function graphs, elaborating them when necessary. However, CBR systems like CADET may encounter issues where retrieved cases are incompatible, requiring backtracking or additional case retrieval. Improving indexing and similarity measures for case retrieval remains a key research challenge. Overall, CBR integrates knowledge-based reasoning and search-intensive methods to solve new problems based on past cases.

## 8.6 Remarks on Lazy vs Eager Learning

This section contrasts lazy and eager learning methods. Lazy methods, like k-nearest neighbor, locally weighted regression, and case-based reasoning, delay generalization decisions until new query instances are encountered. Eager methods, like radial basis function (RBF) networks, generalize before the query is observed by committing to a structure and weights during training.

The key distinction is in computation time and inductive bias. Lazy methods tend to require less computation during training but more during prediction, while eager methods require more computation during training but less during prediction. The critical difference in inductive bias is that lazy methods can adjust the hypothesis based on the specific query instance, whereas eager methods choose a global approximation before observing the query.

A lazy learner can use many local approximations to form a global target function, whereas an eager learner must commit to a single global approximation. Although eager methods like RBF networks can combine local approximations, they do not fully capture the flexibility of lazy methods in customizing responses for specific query instances. 

In summary, lazy methods have more flexibility in customizing local approximations for each query, while eager methods, although capable of using multiple local approximations, must commit to a global solution before encountering the query.

## 8.7 Summary of Instance-Based Learning Methods

This section discusses various instance-based learning methods that delay processing of training examples until they are required for labeling new query instances. These methods avoid creating a global approximation of the target function, instead using local approximations for each query instance. The advantages of these methods include the ability to model complex target functions with simpler local approximations and the retention of training data. However, challenges include the efficiency of querying, determining a suitable distance metric, and the impact of irrelevant features.

Key algorithms discussed are:
- **k-Nearest Neighbors (k-NN):** An instance-based method where target values are estimated based on the k nearest neighbors in an n-dimensional space.
- **Locally Weighted Regression:** An extension of k-NN, where local approximations are constructed for each query using various functional forms.
- **Radial Basis Function (RBF) Networks:** Neural networks using spatially localized kernel functions to form global approximations. They blend instance-based learning with neural networks, often applied in visual scene interpretation.
- **Case-Based Reasoning:** A method where instances are represented by complex symbolic descriptions, applied in areas like legal reasoning and complex planning tasks.

The section also highlights key references for further reading on these methods, including classic works on k-NN, RBF networks, and case-based reasoning.
