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

### **Key Concepts**  
### 1. **Gradient Descent:**
   - **Gradient descent** is used to minimize error by searching the hypothesis space for the best-fit weight vector.  
   - This technique is essential for training more advanced networks, including multi-layer perceptrons.

### 2. **Training Error Measure:**  
   - The training error is measured by the **half squared difference** between the target output and the actual output for each training example.  
   - The error function `E` is defined as:
![image](https://github.com/user-attachments/assets/e6c588db-a07c-49e8-bc75-b2e5a5261bad)
     where:  
     - `t_d` = target output for training example `d`  
     - `o_d` = output from the linear unit for training example `d`

### 3. **Linear Unit:**  
   - The **delta rule** applies to a **linear unit**, which is a perceptron without a threshold, and aims to minimize error through gradient descent.
![image](https://github.com/user-attachments/assets/c27d8ed1-59d0-4ae6-9be9-18fa5682cd77)

### 4. **Foundation for Backpropagation:**  
   - The delta rule forms the basis for **backpropagation** in multi-layer neural networks, allowing networks to learn through multiple layers of interconnected units.  

---

### **Summary:**  
The delta rule uses gradient descent to find a weight vector that minimizes training error. It works with linear units and serves as a foundation for more advanced learning algorithms, including backpropagation, which enables the training of deep networks.

#### 4.4.3.1 **Visualizing the Hypothesis Space**

To understand **gradient descent**, it is useful to visualize the **hypothesis space** of possible weight vectors for a linear unit. The hypothesis space is represented on a **2D plane** where the axes correspond to the values of the weights (wo, wl), and the vertical axis represents the **error E** relative to a fixed set of training examples.

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
