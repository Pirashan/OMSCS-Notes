# 4 - Artificial Neural Networks

## 4.1 - Introduction 
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
