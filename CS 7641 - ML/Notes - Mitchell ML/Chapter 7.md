# Chapter 7 - Computational Learning Theory

## 7.1 Introduction

The chapter introduces foundational concepts in the computational theory of machine learning, focusing on understanding the inherent difficulty of learning problems, the number of training examples required, and the computational effort needed. Key questions addressed include:

1. **Sample Complexity**: How many training examples are needed for a learner to converge to a successful hypothesis with high probability?
2. **Computational Complexity**: How much computational effort is required for convergence?
3. **Mistake Bound**: How many mistakes will a learner make before converging?

The chapter explores these questions within the **Probably Approximately Correct (PAC)** learning framework, which provides quantitative bounds based on:
- The size or complexity of the hypothesis space.
- The accuracy required for approximating the target concept.
- The probability of outputting a successful hypothesis.
- The manner in which training examples are presented.

Key sections include:
- **PAC Learning**: Introduces the PAC framework and analyzes sample and computational complexity.
- **VC-Dimension**: Measures hypothesis space complexity, extending PAC analysis to infinite hypothesis spaces.
- **Mistake-Bound Model**: Provides bounds on mistakes made by learning algorithms.
- **Weighted-Majority Algorithm**: A practical algorithm for combining predictions from multiple learners, with a theoretical mistake bound.

## 7.2 Probably Learning An Approximately Correct Hypothesis
The section introduces the **Probably Approximately Correct (PAC)** learning model, a framework for understanding the learning problem. It focuses on learning boolean-valued concepts from noise-free training data, though the principles can extend to real-valued functions and noisy data scenarios. The discussion explores the number of training examples and computational resources needed to learn various target functions within the PAC model.

### 7.2.1 The Problem Setting

The problem setting defines a learning framework where a learner \( L \) attempts to learn a target concept \( c \) from a set of instances \( X \). Each target concept is a Boolean function mapping instances to {0,1}. Instances are drawn randomly from an unknown but stationary probability distribution \( D \). The learner receives training examples consisting of instances and their corresponding target values. The learner selects a hypothesis \( h \) from a hypothesis space \( H \) to approximate \( c \). The effectiveness of \( L \) is evaluated based on \( h \)'s performance on new instances drawn from \( D \). The analysis focuses on worst-case scenarios across all possible target concepts and distributions.

### 7.2.2 Error of a Hypothesis

The error of a hypothesis \( h \) measures how well it approximates the target concept \( c \) over the instance distribution \( D \). The **true error** of \( h \), denoted as \( error_D(h) \), is the probability that \( h \) misclassifies a randomly drawn instance from \( D \). This is distinct from **training error**, which is the fraction of training examples misclassified by \( h \). The true error depends on the unknown distribution \( D \), which can significantly influence its value. The learner only observes training error and must estimate true error based on it. A key challenge in learning is determining how likely the training error provides a misleading estimate of the true error, which is closely related to the sample error analysis from Chapter 5. This chapter extends that analysis to account for the dependency between \( h \) and the training set.

<img width="480" alt="image" src="https://github.com/user-attachments/assets/353d1bfe-6dd7-476f-8692-9f24e3e0e981" />

### 7.2.3 PAC Learnability

PAC (Probably Approximately Correct) Learnability characterizes the ability of a learner to reliably learn a target concept class from a reasonable number of training examples and computation. Instead of requiring perfect learning (\(error_D(h) = 0\)), PAC learning allows for a small error \(\epsilon\) and a small failure probability \(\delta\). A concept class \( C \) is PAC-learnable by a learner \( L \) using hypothesis space \( H \) if, for any target concept \( c \in C \) and distribution \( D \), \( L \) can, with probability at least \( 1 - \delta \), produce a hypothesis with error at most \(\epsilon\) in polynomial time with respect to \( 1/\epsilon \), \( 1/\delta \), the instance size \( n \), and the complexity of \( c \). 

PAC learning also establishes that learnability depends on both computational efficiency and the number of training examples, as polynomial computation per example implies polynomially bounded data requirements. However, PAC learning assumes that the hypothesis space \( H \) contains a near-optimal hypothesis for every target concept, which can be restrictive. Later sections explore more flexible learning scenarios that relax this assumption.

