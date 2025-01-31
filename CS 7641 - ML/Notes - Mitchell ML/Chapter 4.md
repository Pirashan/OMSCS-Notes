# 4 - Artificial Neural Networks

## 4.1 Introduction 
Neural network learning methods effectively approximate various target functions and are particularly useful for interpreting complex real-world sensor data. The **backpropagation algorithm** has been highly successful in applications like handwritten character recognition, speech recognition, and face recognition. Studies, including those by LeCun (1989), Lang (1990), and Cottrell (1990), highlight its practical impact, with additional insights from Rumelhart et al. (1994).

### 4.1.1 Biological Motivation  

Artificial Neural Networks (ANNs) are inspired by biological neural networks, which consist of densely interconnected neurons. Each ANN unit takes multiple inputs and produces a real-valued output, similar to biological neurons.  

The human brain has about **10¹¹ neurons**, each connected to **10⁴ others**, with switching speeds of **10⁻³ seconds**, much slower than computers. However, humans can recognize faces in **10⁻¹ seconds**, suggesting that biological neural processing relies on **highly parallel, distributed computation**.  

ANNs aim to replicate this parallelism, often running on sequential machines or specialized parallel hardware. However, ANNs **do not perfectly model biological systems**, as biological neurons produce complex spike patterns, whereas ANN units output constant values.  

There are two main research motivations for ANNs:  
1. **Modeling biological learning**  
2. **Developing efficient machine learning algorithms** (the focus of this book)

## 4.2 Neural Network Representations  

Neural networks are widely used in learning tasks, as demonstrated by **ALVINN** (Pomerleau, 1993), an ANN-based system for steering an autonomous vehicle at highway speeds. ALVINN’s neural network receives a **30 × 32 grid of pixel intensities** from a forward-facing camera and outputs the steering direction. The system is trained to mimic human driving behavior and has successfully driven at **70 mph for 90 miles** on public highways.  

### **ALVINN Network Structure**  
- **Input layer:** 30 × 32 pixel intensities from the camera  
- **Hidden layer:** 4 units processing weighted combinations of **960 inputs each**  
- **Output layer:** 30 units corresponding to different steering directions  

The **weights in the network** determine how information is processed, with hidden units transforming the input into useful features. A diagram of ALVINN shows the learned weights, where **white boxes** indicate positive weights, **black boxes** indicate negative weights, and **box size** represents magnitude.  

### **ANN Architectures and Learning**  
Most practical **ANN architectures** use **feed-forward networks** with layers forming a **directed acyclic graph**. The **Backpropagation algorithm** is commonly used for training, assigning optimal weight values to connections. While some networks allow cycles, most real-world applications rely on **acyclic feed-forward networks**, like ALVINN.  

## 4.3 Appropriate Problems for Neural Network Learning  

Neural networks (ANNs) are particularly effective for **noisy and complex sensor data** (e.g., images, audio) but also perform well on **symbolic tasks** like decision tree learning. The **Backpropagation algorithm** is the most common ANN training method and is suited for problems with the following characteristics:  

### **Key Characteristics of Problems Suitable for ANNs**  
- **Feature-rich input representations:** Instances have **many attribute-value pairs**, such as pixel values in ALVINN. Inputs can be **correlated or independent** and take real values.  
- **Flexible output types:** The target function can be **discrete-valued, real-valued, or a vector**. ALVINN, for example, outputs a **30-dimensional vector** for steering recommendations, where each value represents confidence between **0 and 1**.  
- **Noise tolerance:** ANN learning is robust to **errors in training data**.  
- **Long training times:** Unlike decision trees, ANN training can take **seconds to hours**, depending on factors like **network complexity and dataset size**.  
- **Fast inference:** Once trained, ANNs can **quickly evaluate new instances**, making them ideal for real-time tasks like ALVINN’s steering system.  
- **Limited interpretability:** ANN models are often **difficult for humans to interpret**, unlike decision trees or rule-based models.  

### **Further Topics in the Chapter**  
The chapter continues with discussions on **alternative neural unit designs** (e.g., perceptrons, linear units, sigmoid units), **Backpropagation for multilayer networks**, and key challenges like **overfitting and alternative training methods**. It also provides a **detailed example of face recognition using Backpropagation**, with data and code for further experimentation.  

## 4.4 Perceptrons  

A **perceptron** is a type of artificial neural network (ANN) unit that computes a **linear combination of inputs** and applies a **threshold function** to determine its output.  

### **How a Perceptron Works**  
- Takes a vector of **real-valued inputs** and assigns **weights** to each input.  
- Computes **a weighted sum of inputs** and outputs:  
  - **1 if the sum exceeds a threshold**  
  - **-1 otherwise**

![image](https://github.com/user-attachments/assets/6c052d79-cc65-4466-b2f5-a43a6def64d9)

The threshold can be rewritten using a **bias term** by adding a constant input \(x_0 = 1\), giving the vector form:  

![image](https://github.com/user-attachments/assets/3b60a5b1-29c3-4bba-bae1-41ba034cf3f5)

### **Learning a Perceptron**  
- The learning process involves **choosing appropriate weight values** (\( w_0, w_1, ..., w_n \)).  
- The **hypothesis space** consists of **all possible real-valued weight vectors**.
![image](https://github.com/user-attachments/assets/c3a8e58b-de3b-4ab7-9a5f-0d736da9d103)

### 4.4.1 Representational Power of Perceptrons  

A **perceptron** represents a **hyperplane decision boundary** in an **n-dimensional space**, where it classifies instances as **1 or -1** based on their position relative to this boundary.  

![image](https://github.com/user-attachments/assets/9ce8dc61-0760-4ba0-bf05-bc83be382d6d)

### **Key Concepts**  

#### **Linearly Separable vs. Non-Separable**
- Perceptrons can classify **linearly separable** data but **fail** for **non-linearly separable** cases.  
- **Example:**  
  - **AND, OR** functions can be implemented using a single perceptron.  
  - **XOR function** cannot be represented because it is not linearly separable.  

#### **Boolean Function Representation**  
- Perceptrons can represent:
  - **AND function:** \( w_0 = -3 \), \( w_1 = w_2 = 0.5 \)  
  - **OR function:** \( w_0 = -0.3 \)  
  - **NAND, NOR functions**  
- **Any Boolean function** can be built using a **combination of these basic functions**.  

#### **Multilayer Networks for Complex Functions**  
- **Single-layer perceptrons** are limited in their representation.  
- **Multilayer networks** can represent **any Boolean function** by:  
  - Using a **two-layer structure** with intermediate perceptrons computing ANDs and a second layer computing ORs.  
  - Expressing functions in **Disjunctive Normal Form (DNF)** (OR of ANDs).  
  - Handling **negations** by flipping weight signs.  

### **Conclusion**  
Because single perceptrons have **limited representation power**, **multilayer perceptrons** are necessary for learning **more complex decision boundaries**.  

### 4.4.2 Perceptron Training Rule
The perceptron training rule is a fundamental algorithm for adjusting the **weights** of a perceptron to correctly classify training examples. It works by iteratively updating the weights whenever the perceptron misclassifies a sample.

---

### **Key Concepts**  
### 1. **Learning Objective:**  
   - Find a weight vector that correctly classifies **all** training examples.  
   - If the dataset is **linearly separable**, the algorithm is guaranteed to **converge**.  

### 2. **Training Process:**  
   - **Start with random weights**.  
   - **Iterate** through the training examples.  
   - **Update the weights** whenever the perceptron misclassifies a sample.  
   - **Repeat** until all examples are correctly classified.  

### 3. **Perceptron Weight Update Rule:**  
![image](https://github.com/user-attachments/assets/4900894b-3b17-4377-bde4-60e3beb89a97)

where:  
- `w_i` = weight for input `x_i`  
- `t` = target output (+1 or -1)  
- `o` = perceptron output (+1 or -1)  
- `η` = **learning rate** (small positive constant, e.g., 0.1)  

### 4. **Role of the Learning Rate (η):**  
- Controls how much the weights **change per update**.  
- Often **decays** over time to stabilize learning.  

---

### **Why Does the Rule Work?**  
### **1. Correctly Classified Example:**  
- If `t = o`, then `(t - o) = 0` → **No weight update needed**.  

### **2. Misclassified Example (Underestimation):**  
- If perceptron outputs **-1**, but the target is **+1**:  
- We need to **increase the weighted sum** to get closer to +1.  
- Rule **increases** the weight `w_i` if `x_i > 0`.  

### **3. Misclassified Example (Overestimation):**  
- If perceptron outputs **+1**, but the target is **-1**:  
- We need to **decrease the weighted sum** to get closer to -1.  
- Rule **decreases** the weight `w_i` if `x_i > 0`.  

---

### **Convergence Guarantee**  
- If the training data is **linearly separable**, the perceptron rule **converges** to a perfect classifier **in a finite number of updates** (Minsky & Papert, 1969).  
- If the data is **not** linearly separable, the perceptron will **never converge**, continuing to update weights indefinitely.  

---

### **Example Calculation**  
Let’s assume:  
- **Training example**: `x_i = 0.8`, **learning rate** `η = 0.1`  
- **Target output** `t = 1`, **Perceptron output** `o = -1`  

Using the update rule:  
Δw_i = η (t - o) x_i = 0.1(1 - (-1)) (0.8) = 0.16
The weight `w_i` **increases by 0.16**, making it more likely to classify correctly in the future.

---

### **Summary**  
- **Perceptron training rule updates weights iteratively** until the perceptron correctly classifies all training examples.  
- Works **only for linearly separable data**; otherwise, it fails to converge.  
- Forms the **basis for training more advanced artificial neural networks**.

### 4.4.3 Gradient Descent and the Delta Rule

The **delta rule** improves the **perceptron rule** for cases where training examples are **not linearly separable**. It uses **gradient descent** to search the hypothesis space and find the best-fit weight vector, which is an approximation to the target concept. The delta rule is foundational for **backpropagation** and learning algorithms in networks with multiple interconnected units.

---

#### **Key Concepts**  
#### 1. **Gradient Descent:**
   - **Gradient descent** is used to minimize error by searching the hypothesis space for the best-fit weight vector.  
   - This technique is essential for training more advanced networks, including multi-layer perceptrons.

#### 2. **Training Error Measure:**  
   - The training error is measured by the **half squared difference** between the target output and the actual output for each training example.  
   - The error function `E` is defined as:
![image](https://github.com/user-attachments/assets/e6c588db-a07c-49e8-bc75-b2e5a5261bad)
     where:  
     - `t_d` = target output for training example `d`  
     - `o_d` = output from the linear unit for training example `d`

#### 3. **Linear Unit:**  
   - The **delta rule** applies to a **linear unit**, which is a perceptron without a threshold, and aims to minimize error through gradient descent.
![image](https://github.com/user-attachments/assets/c27d8ed1-59d0-4ae6-9be9-18fa5682cd77)

#### 4. **Foundation for Backpropagation:**  
   - The delta rule forms the basis for **backpropagation** in multi-layer neural networks, allowing networks to learn through multiple layers of interconnected units.  

### **Summary:**  
The delta rule uses gradient descent to find a weight vector that minimizes training error. It works with linear units and serves as a foundation for more advanced learning algorithms, including backpropagation, which enables the training of deep networks.

---

#### 4.4.3.1 **Visualizing the Hypothesis Space**

To understand **gradient descent**, it is useful to visualize the **hypothesis space** of possible weight vectors for a linear unit. The hypothesis space is represented on a **2D plane** where the axes correspond to the values of the weights (wo, wl), and the vertical axis represents the **error E** relative to a fixed set of training examples.

![image](https://github.com/user-attachments/assets/10b1ede1-81f2-456d-bc23-c8ff7dd0f2b6)

---

##### **Key Concepts:**

##### 1. **Error Surface:**
   - The **error surface** is parabolic with a **single global minimum**.  
   - The error value is dependent on the weight vector and the training examples.

##### 2. **Gradient Descent:**
   - **Gradient descent** works by starting with an arbitrary initial weight vector and modifying it iteratively in small steps.  
   - The steps are taken in the direction of the steepest descent along the error surface, aiming to reach the global minimum error.

##### 3. **Objective:**
   - The goal of the gradient descent is to **minimize the error** by finding the optimal weight vector, i.e., the global minimum of the error surface.

#### 4.4.3.2 **Derivation of the Gradient Descent Rule**

To find the **direction of steepest descent** on the error surface, the **gradient of the error function (E)** is computed. The gradient is a vector consisting of the **partial derivatives of E** with respect to each weight component. The **negative gradient** specifies the direction of steepest decrease, guiding the weight vector towards minimizing the error.

---

##### **Key Concepts:**

##### 1. **Gradient Calculation:**
   - The **gradient** of E is a vector of partial derivatives of E with respect to each weight.
   - The **negative gradient** indicates the direction of steepest decrease.
![image](https://github.com/user-attachments/assets/0833422f-9017-4ec8-8fbf-d491a4edaa2e)

##### 2. **Gradient Descent Update Rule:**
   - The weight update is given by:  
     `w_i = w_i - η * ∇E(w)`  
   where **η** is the **learning rate**, and **∇E(w)** is the gradient.
![image](https://github.com/user-attachments/assets/a76e6b1f-8c88-4bcb-b484-aaecadea02e4)

The component form:
![image](https://github.com/user-attachments/assets/5f553b9f-29d5-4743-925c-72f4d41a9964)

The vector of partial derivatives for each weight that forms the gradient can be obtained by differentiating E from above as:
![image](https://github.com/user-attachments/assets/e78456f4-2a6f-49f5-b77f-accfa4b4d935)

Substituting gives the weight update rule for gradient descent:
![image](https://github.com/user-attachments/assets/9af83531-80dd-46e6-921a-f4ebadfeda6e)

##### 3. **Algorithm:**
   - Start with a **random initial weight vector**.
   - Compute the **gradient** for each weight using the training examples.
   - Update each weight by adding the change in weight calculated from the gradient.
   - Repeat the process until convergence.

##### 4. **Learning Rate (η):**
   - A sufficiently small learning rate ensures convergence, as large values risk overshooting the minimum.  
   - **Gradually decreasing** the learning rate over time can help prevent overshooting.

#### 4.4.3.3 **Stochastic Approximation to Gradient Descent**

Gradient descent is a common learning strategy but faces practical challenges, including slow convergence and the risk of getting stuck in local minima. **Stochastic Gradient Descent (SGD)** addresses these issues by updating weights incrementally after each training example.

---

##### **Key Concepts:**

##### 1. **Stochastic Gradient Descent (SGD):**
   - Weights are updated after processing each training example, rather than after the entire dataset.
   - This makes the training process faster and helps avoid local minima by introducing variability.

##### 2. **Delta Rule:**
   - A variation of gradient descent, similar to the perceptron rule but applied to linear units.
   - The delta rule can be used for both unthresholded and thresholded perceptrons.
   - **Key Difference**: The delta rule minimizes the error in the linear output, leading to correct classification for thresholded outputs.

The modified training rule is like the training rule earlier, except that as we iterate through each training example we update the weight according to:
![image](https://github.com/user-attachments/assets/43d9d4fb-ab9c-473d-a7a9-bd901cfbe843)

##### 3. **Advantages of SGD:**
   - **Faster updates** compared to traditional gradient descent.
   - Can help avoid local minima by iterating over training examples.
   - **Flexibility**: SGD works well when there are multiple local minima in the error surface.

##### 4. **Challenges of SGD:**
   - Although faster, SGD can introduce more **variability** in the weight updates.
   - May require careful tuning of learning rate to avoid overshooting or slow convergence.

---

### 4.4.4 **Remarks on Perceptron Weight Learning Algorithms**

There are two main algorithms for learning perceptron weights: the **Perceptron Training Rule** and the **Delta Rule**. The perceptron rule updates weights based on the error in the thresholded perceptron output, while the delta rule updates weights based on the error in the unthresholded linear combination of inputs.

#### **Key Differences:**

#### 1. **Perceptron Training Rule:**
   - Updates weights based on thresholded perceptron output.
   - **Convergence:** Converges after a finite number of iterations to a hypothesis that perfectly classifies the training data, **provided the data is linearly separable**.

#### 2. **Delta Rule:**
   - Updates weights based on unthresholded linear combinations.
   - **Convergence:** Converges asymptotically toward the minimum error hypothesis, but may require unbounded time. It converges regardless of whether the training data is linearly separable.

#### **Alternative Approach: Linear Programming:**
   - Efficient for solving linear inequalities.
   - Only works when training examples are **linearly separable**.
   - **Limitation:** Does not scale well for multilayer networks, whereas gradient descent can be extended to multilayer networks.

## 4.5 **Multilayer Networks and the Backpropagation Algorithm**

Single perceptrons can only create **linear decision surfaces**, but **multilayer networks**, trained using the **Backpropagation Algorithm**, can express **nonlinear decision surfaces**.

### Example: Speech Recognition
- Task: Distinguish among 10 vowels spoken in the context of "h-d" (e.g., "hid," "had").
- **Multilayer Networks**: Capable of representing highly nonlinear decision surfaces, making them much more expressive than the linear decision surfaces of single perceptrons.

This section explains how to learn such multilayer networks using a **gradient descent algorithm**, similar to the one discussed in earlier sections.

### 4.5.1 **A Differentiable Threshold Unit**

In constructing multilayer networks, **linear units** and **perceptrons** are not suitable for representing nonlinear functions or for gradient descent. The solution is the **sigmoid unit**, which has a **differentiable threshold**.

![image](https://github.com/user-attachments/assets/02919c12-c8e3-4beb-8775-1f3db4bc7e22)

![image](https://github.com/user-attachments/assets/1bab49bd-73e2-4824-9f3d-e81da7b262c0)

#### Key Points:
- **Sigmoid Unit**: Computes a linear combination of inputs, followed by a continuous threshold.
- **Output Range**: 0 to 1.
- **Property**: The derivative of the sigmoid function is easily expressed in terms of its output, which is essential for gradient descent.
- **Alternatives**: Variations of the sigmoid function, such as using a constant to adjust the steepness of the threshold or using the **tanh** function.

### 4.5.2 **The BACKPROPAGATION Algorithm**

The **BACKPROPAGATION algorithm** is a gradient descent method used to train multilayer networks by minimizing the squared error between the network's outputs and target values. 

Because we are considering networks with multiple output units rather than single units as before, we begin be redefining E to sum the errors over all of the network output units:
![image](https://github.com/user-attachments/assets/e939c786-915d-4950-ada1-c9b2a1edeabb)
where outputs is the set of output units in the network, and tkd and Okd are the target and output values associated with the kth output unit and training example d.

![image](https://github.com/user-attachments/assets/9509668a-9648-4ab4-b945-2d719b676f08)

#### Key Points:
- **Error Calculation**: The error is computed for all output units, and the network weights are updated to reduce this error.
- **Forward and Backward Passes**: The algorithm propagates the input forward to calculate the output, and then propagates errors backward to adjust weights.
- **Challenges**: The error surface for multilayer networks can have multiple local minima, making it hard to guarantee convergence to the global minimum.
- **Stochastic Gradient Descent**: Weights are updated incrementally for each training example.
- **Termination Conditions**: The algorithm can stop after a fixed number of iterations, once the error reaches a certain threshold, or based on a validation set.

#### 4.5.2.1 **Adding Momentum to BACKPROPAGATION**

A popular variation of the **BACKPROPAGATION algorithm** is the addition of **momentum** to the weight-update rule. This modification makes the weight update at iteration \(n\) depend partially on the update from the previous iteration.

##### Key Points:
- **Momentum Term**: The weight update in the current iteration is influenced by the previous iteration’s update, with a constant \(\alpha\) controlling the momentum.
- **Effect of Momentum**: Momentum helps the algorithm keep moving in the same direction, enabling it to pass through small local minima or flat regions in the error surface.
- **Speeding Up Convergence**: By maintaining momentum, the algorithm can gradually increase the step size, accelerating convergence in certain regions.

The most common way is to alter the weight-update rule by making the weight update on the nth iteration depend partially on the update that occurred during the (n - 1)th iteration, as follows:
![image](https://github.com/user-attachments/assets/8410aca1-b46c-4741-a4a7-ed2da9cc14e5)

#### 4.5.2.2 **Learning in Arbitrary Acyclic Networks**

The **BACKPROPAGATION algorithm** can be generalized to work with **feedforward networks of arbitrary depth**. While the weight update rule remains the same, the procedure for computing error terms (\( \delta_r \)) is adapted.

##### Key Points:
- **Recursive Error Calculation**: The error term for each unit is computed recursively from the output layer to the earlier layers.
- **Generalization to Directed Acyclic Graphs (DAGs)**: The algorithm can be extended to networks where units are not in uniform layers. In such cases, the error term for internal units depends on the downstream units that receive input from them.

### 4.5.3 **Derivation of the BACKPROPAGATION Rule**

This section provides the derivation of the **stochastic gradient descent (SGD) rule** used in the **BACKPROPAGATION algorithm** for updating weights during training.

#### Key Points:
- **Stochastic Gradient Descent**: The algorithm updates weights by iterating through training examples, calculating the gradient of the error for each example.
  
#### Two Key Cases in Derivation:
1. **Output Unit Weights**: The weight updates for output units are derived using the chain rule, where the error is computed with respect to the output.
2. **Hidden Unit Weights**: The weight updates for hidden units involve accounting for indirect influences on the error through **downstream units** in the network.

![image](https://github.com/user-attachments/assets/eb5939e5-af6a-4389-b2be-a860278fa7f8)
![image](https://github.com/user-attachments/assets/2ad06e6e-2c0a-4f2e-88fe-0a007b143f51)

![image](https://github.com/user-attachments/assets/57a42d05-e9ab-4ea9-b958-8df62806a0b7)

#### Final Result:
The weight update rule derived for output units and hidden units forms the basis of the **BACKPROPAGATION algorithm** used to train the network, with the hidden units' updates considering the downstream units.

## 4.6 **Remarks on the BACKPROPAGATION Algorithm**
### 4.6.1 Convergence and Local Minima

This section discusses challenges with **gradient descent** and the risk of getting trapped in **local minima** during **BACKPROPAGATION**. While the algorithm is effective for function approximation, it does not guarantee convergence to the global minimum error.

### Key Points:
1. **Local Minima**: The gradient descent process can get stuck in local minima instead of finding the global minimum.
2. **High Dimensionality**: Networks with many weights have large error surfaces with multiple "escape routes," reducing the chance of getting stuck in one local minimum.
3. **Network Function Evolution**: In early stages of training, the network represents simple, linear functions. As training progresses, it can represent more complex functions, which may have more local minima.
4. **Heuristics for Avoiding Local Minima**:
   - Add a **momentum** term to the weight-update rule.
   - Use **stochastic gradient descent** to navigate different error surfaces.
   - Train **multiple networks** with different initializations and select the best one or combine them into a "committee."
  
### 4.6.2 **Representational Power of Feedforward Networks**

Feedforward networks have the ability to represent a wide range of functions, with increased representational power as the network depth and width increase. Three general results are known:

### Key Results:
1. **Boolean Functions**: Any boolean function can be represented by a two-layer network, though the number of hidden units grows exponentially with the number of inputs. Each hidden unit is activated by a specific input vector, and the output unit functions as an OR gate for desired input patterns.
   
2. **Continuous Functions**: Any bounded continuous function can be approximated with arbitrarily small error by a two-layer network using sigmoid units in the hidden layer and linear units in the output layer. The number of hidden units required depends on the function.

3. **Arbitrary Functions**: Any function can be approximated to arbitrary accuracy by a three-layer network with two hidden layers using sigmoid units and a linear output layer. This approximation involves using linear combinations of localized functions.

### 4.6.3 **Hypothesis Space Search and Inductive Bias**

In **BACKPROPAGATION**, the hypothesis space is the n-dimensional Euclidean space of network weights, which is continuous, unlike methods like decision tree learning that use discrete representations. This continuous hypothesis space, along with the differentiable error function, provides a well-defined error gradient that organizes the search for the best hypothesis.

#### Inductive Bias:
The inductive bias of **BACKPROPAGATION** is hard to characterize precisely but can be described as **smooth interpolation** between data points. When positive training examples are close together with no negative examples between them, the network tends to classify intermediate points as positive, leading to smoothly varying decision regions.

### 4.6.4 **Hidden Layer Representations**

A distinctive feature of **BACKPROPAGATION** is its ability to **automatically discover useful intermediate representations** at the hidden layers of the network. Unlike methods that rely on predefined features, **BACKPROPAGATION** allows the network to learn new hidden layer features that help minimize the squared error \(E\).

For example, in a network with **three hidden units** and **eight input-output units**, the hidden units will capture relevant features from the inputs. As the network learns, these representations can resemble common patterns such as **binary encodings**. This flexibility enables **ANNs** to create features not explicitly designed by humans, making the learning process more adaptable.

![image](https://github.com/user-attachments/assets/308091de-90ff-4714-9c7b-d82701c035d3)

The process of discovering these representations occurs gradually through the **gradient descent** procedure, where the network adjusts weights over several iterations to reach optimal hidden layer encodings. 

### 4.6.5 Generalization, Overfitting, and Stopping Criterion

The BACKPROPAGATION algorithm requires an appropriate stopping criterion to prevent overfitting. Simply minimizing the training error can lead to poor generalization, as the model starts capturing idiosyncrasies of the training data rather than learning general patterns. Overfitting tends to occur in later iterations as weight adjustments increase model complexity.

To combat overfitting, techniques like **weight decay** (reducing weight values) and **validation-based stopping** are used. The validation approach monitors error on a separate dataset, stopping training when validation error starts increasing. A common strategy stores the best-performing weights based on validation error and returns them as the final model. However, identifying the exact stopping point can be tricky due to fluctuations in validation error.

For small datasets, **k-fold cross-validation** helps optimize the stopping point by averaging results from multiple partitions of the data. The final model is then trained on the full dataset using the optimal number of iterations identified through cross-validation.

![image](https://github.com/user-attachments/assets/c032959b-45b7-45f8-931b-af35a4cfc0c9)
![image](https://github.com/user-attachments/assets/88acdde3-4305-4efd-9347-e9727252fa56)

## Illustrative Example: Face Recognition

This section provides an illustrative example of applying the **Backpropagation** algorithm to a **face recognition** task. It discusses the **practical design choices** involved in using Backpropagation for this problem. Additionally, it mentions that all **image data and code** used in the example, along with complete documentation, are available online for users t

### 4.7.1 The Task

The learning task involves **classifying camera images** of faces from **20 individuals** in various **poses, expressions, and conditions** (e.g., with/without sunglasses). A dataset of **624 greyscale images** (120×128 resolution) was collected, capturing variations in **background, clothing, and face position**. Multiple classification tasks can be performed, such as identifying the person, their gender, or whether they are wearing sunglasses. This section focuses specifically on **predicting the direction** in which the person is facing (left, right, straight ahead, or upward).

![image](https://github.com/user-attachments/assets/3a1f9fab-563e-43c8-b66e-5970816ae56c)

### 4.7.2 Design Choices  

The design of the **face direction classification** neural network required multiple considerations:  

- **Input Encoding**: The original **120×128 images** were downsampled to **30×32 pixels**, with grayscale values scaled between **0 and 1** to reduce computational demands while maintaining classification accuracy.  
- **Output Encoding**: A **1-of-n encoding** (four output units) was used instead of a single unit to provide **better representation capacity** and a measure of **classification confidence**. Target values were set to **0.1 and 0.9** instead of 0 and 1 to prevent unbounded weight growth.  
- **Network Structure**: A **feedforward** architecture with **one hidden layer** was chosen. A network with **three hidden units** achieved **90% accuracy**, while **30 hidden units** improved accuracy slightly but required significantly longer training.  
- **Training Parameters**: A **learning rate of 0.3**, **momentum of 0.3**, and **full gradient descent** were used. Input weights were initialized to **zero** for better visualization, and output weights were set to **small random values**. The best network was selected based on **validation set accuracy**, and the final accuracy was reported on a separate **test set**.

### 4.7.3 Learned Hidden Representations

The learned hidden representations in the neural network reveal how weight values evolve over training iterations. The network contains 2,899 weights, with Figure 4.10 visualizing their changes after 1 and 100 training iterations. Each of the four output units (left, straight, right, up) has four associated weights, with values depicted using grayscale intensity. The hidden units receive inputs from all 30x32 image pixels, and their weight patterns align with facial and body regions in the images.

After 100 training iterations, weight values significantly adjust, showing distinct patterns. For example, the output unit indicating a person looking right has a strong positive weight from one hidden unit and a strong negative weight from another. These weights correspond to facial and hair regions, helping the network effectively classify directions based on pixel intensity alignment.

## 4.8 Advanced Topics in Artificial Neural Networks
### Summary of 4.8.1 Alternative Error Functions  

Gradient descent can be applied to various differentiable error functions beyond the standard sum of squared errors used in basic backpropagation. Different error functions allow for incorporating constraints to improve generalization and learning efficiency.  

#### 1. Weight Magnitude Penalty  
- Adding a penalty term to the error function discourages large weight values, reducing overfitting.  
- This technique, known as weight decay, modifies the weight update rule by multiplying each weight by a constant factor.

![image](https://github.com/user-attachments/assets/d440fb74-601f-47e3-ad01-a6897e2bfab5)

#### 2. Error in Function Derivatives  
- Some applications, like character recognition, use derivative-based constraints to enforce invariance (e.g., translation invariance). 
- The error function is modified to minimize the difference between learned derivatives and known training derivatives.  

![image](https://github.com/user-attachments/assets/7d58c3c8-c003-4c21-aa40-583eab23cd1e)

#### 3. Minimizing Cross-Entropy  
- When training probabilistic models (e.g., loan repayment prediction), minimizing cross-entropy leads to better probability estimates. 
- This approach is useful when the goal is to model likelihood rather than exact target values.  

![image](https://github.com/user-attachments/assets/9e850f62-5c53-4b09-a5d7-39f3b41f3403)

#### 4. Weight Sharing  
- Used in domains like speech recognition to enforce constraints known in advance.  
- By tying together weights for different units, the model reduces hypothesis space complexity, improving generalization.  
- Shared weights are updated separately and then averaged to maintain consistency.  

By modifying the error function, neural networks can learn more effectively under different constraints and problem-specific requirements.

### Summary of 4.8.2 Alternative Error Minimization Procedures  

Gradient descent, while widely used, can be inefficient for training complex neural networks, often requiring thousands of iterations. Alternative optimization methods aim to improve efficiency by modifying how weight updates are determined.  

#### 1. Gradient Descent in Backpropagation  
- Chooses update direction as the negative gradient.  
- Update distance is determined by a fixed learning rate.  

#### 2. Line Search  
- Instead of a fixed learning rate, the update distance is chosen by minimizing the error function along the chosen direction.  
- This allows for larger or smaller updates depending on the error function's behavior.  

#### 3. Conjugate Gradient Method  
- Builds on line search by performing a sequence of searches for the minimum error.  
- The first step follows the negative gradient, while subsequent steps ensure that previously minimized components remain zero.  

While these methods can improve training efficiency, they do not significantly impact the network's generalization performance. They may, however, lead to different local minima. Bishop (1996) provides a broader discussion of various parameter optimization methods.  

### Summary of 4.8.3 Recurrent Networks  

Recurrent neural networks (RNNs) differ from traditional feedforward networks by incorporating directed cycles, making them well-suited for time-series data. Unlike acyclic networks, RNNs use outputs from previous time steps as inputs for future time steps, allowing them to capture temporal dependencies.  

![image](https://github.com/user-attachments/assets/57a5e341-0150-4cc4-9d2f-defc28099095)

#### 1. Recurrent Networks vs. Feedforward Networks  
- Feedforward networks predict outputs using only current inputs, limiting their ability to model dependencies on past data.  
- RNNs address this by introducing hidden units that store information from previous time steps, enabling them to learn patterns over time.  

#### 2. How Recurrent Networks Work  
- An additional hidden unit (b) and an input unit (c) are introduced, where c(t) receives the value of b from the previous time step (t-1).  
- This allows the network to retain and process historical information across an arbitrary time window.  
- More complex architectures can incorporate multiple hidden layers or additional context units.  

#### 3. Training Recurrent Networks  
- RNNs can be trained using a variant of backpropagation called **Backpropagation Through Time (BPTT)**.  
- The network is "unfolded in time," converting the recurrence into a deep feedforward network, which can then be trained using standard backpropagation.  
- After training, the final weights in the recurrent network are derived as the average of weights from the unfolded versions.  

While RNNs provide greater representational power, they are more challenging to train and do not generalize as reliably as feedforward networks. However, they remain critical for applications involving sequential data.  

### Summary of 4.8.4 Dynamically Modifying Network Structure  

In neural network learning, while we often adjust weights within a fixed structure, there are methods that dynamically modify the network’s architecture by adding or removing units and connections to improve training efficiency and generalization accuracy.

#### 1. Growing the Network (CASCADE-CORRELATION Algorithm)  
- The CASCADE-CORRELATION algorithm starts with a network that has no hidden units, and it adds hidden units as needed to reduce training error.  
- After training the initial network, the algorithm adds hidden units, ensuring each new unit maximizes correlation with the residual error.  
- This process repeats until the error is reduced to an acceptable level. However, the risk of overfitting increases as the network grows, requiring precautions to avoid this issue.  
- The algorithm has been shown to reduce training times because only one layer of units is trained at each step.

#### 2. Pruning the Network  
- Another approach starts with a complex network and removes connections that are deemed unnecessary.  
- One method to assess whether a weight is unnecessary is to measure its effect on the network's error.  
- The "optimal brain damage" approach iteratively removes the least salient connections, improving generalization accuracy and training efficiency.  
- This approach has successfully reduced network size while enhancing performance, as demonstrated in a character recognition task.  

#### 3. General Effectiveness  
- While dynamically modifying network structure can sometimes improve training efficiency, its impact on generalization accuracy remains uncertain.  
- Despite mixed results, these methods have been proven to provide significant improvements in training times.

---

# 4.9 Summary

This section provides an overview of artificial neural network (ANN) learning, its key methods, challenges, and further reading recommendations.

#### 1. Overview of Backpropagation  
- **Backpropagation** is the most commonly used ANN learning algorithm and applies to a wide range of tasks like handwriting recognition and robot control.  
- **Feedforward networks** with three layers can approximate any function given enough units. Backpropagation uses **gradient descent** to minimize error by adjusting network weights, but it converges to a local minimum.  
- One of the main advantages of backpropagation is its ability to invent **intermediate features** useful for learning tasks, which are not explicitly present in the input data.  

#### 2. Overfitting and Cross-Validation  
- **Overfitting** occurs when a network fits training data too well but generalizes poorly to new data. Cross-validation is used to determine when to stop the gradient descent to avoid this problem.

#### 3. Other ANN Algorithms  
- While backpropagation is widely used, other algorithms, such as those for **recurrent neural networks** or **CASCADE-CORRELATION**, dynamically adjust both network structure and weights for specialized tasks.
