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

## 7.3 Sample Complexity for Finite Hypothesis Spaces

The section discusses the **sample complexity** of learning problems, particularly for **consistent learners**, which always find a hypothesis that perfectly fits the training data when possible. The key challenge in PAC (Probably Approximately Correct) learning is determining how many training examples are required for successful generalization.

A **version space** is the set of hypotheses that correctly classify the training data. To ensure the version space contains no hypotheses with high error, we consider the concept of **ε-exhaustion**, where all remaining hypotheses have error less than **ε**.

### Theorem (Haussler, 1988)
If the hypothesis space **H** is finite and **m** examples are drawn independently, the probability that the version space is **not** ε-exhausted is at most:

\[
|H|(1 - ε)^m
\]

Using an inequality approximation, the number of training examples required to ensure with probability **(1 - δ)** that any consistent hypothesis is approximately correct within error **ε** is:

\[
m \geq \frac{1}{\epsilon} \ln \frac{|H|}{\delta}
\]

### Key Insights:
- **m grows linearly** with **1/ε**, meaning more examples are needed for smaller error.
- **m grows logarithmically** with **1/δ**, meaning reducing uncertainty requires fewer additional examples.
- **m grows logarithmically** with **|H|**, so larger hypothesis spaces require more examples.
- The bound may **overestimate** the required examples, especially for large hypothesis spaces.
- Tighter bounds exist, particularly for infinite hypothesis spaces (covered in Section 7.4).

### 7.3.1 Agnostic Learning and Inconsistent Hypotheses

Agnostic learning refers to cases where the hypothesis space \( H \) may not contain the true target concept \( c \), meaning a hypothesis with zero training error may not be found. In this scenario, the learner selects the hypothesis in \( H \) with the minimum training error. Unlike PAC-learning, which assumes \( c \in H \), an agnostic learner makes no such assumption.

To extend the previous sample complexity bound (Equation 7.2) to this case, Hoeffding bounds (or additive Chernoff bounds) are used. These bounds describe how the observed training error deviates from the true error over independent samples. This leads to a new bound on the probability that the best hypothesis has a true error exceeding its training error by more than \( \epsilon \).

The revised sample complexity bound shows that the required number of training examples \( m \) still grows logarithmically with \( |H| \) and \( 1/\delta \), but now scales as \( (1/\epsilon)^2 \), rather than linearly with \( 1/\epsilon \).

<img width="173" alt="image" src="https://github.com/user-attachments/assets/29f3f760-8f42-4cce-8eef-321820ff8c8e" />

### 7.3.2 Conjunctions of Boolean Literals Are PAC-Learnable

The class of conjunctions of Boolean literals is **PAC-learnable** because a consistent learner requires only a **polynomial number of training examples** and polynomial time per training example. Given \( n \) Boolean variables, the hypothesis space size is \( 3^n \), as each variable can be included as a literal, negated, or ignored. Using Equation (7.2), the sample complexity for learning such conjunctions is shown to be polynomial in \( n \), \( 1/\epsilon \), and \( 1/\delta \).

The **FIND-S algorithm** is an example of a learning algorithm that efficiently PAC-learns Boolean conjunctions. FIND-S incrementally computes the most specific hypothesis consistent with the training data and updates in **linear time** per training example. Given these properties, Theorem 7.2 establishes that conjunctions of Boolean literals are **PAC-learnable** using FIND-S.

<img width="490" alt="image" src="https://github.com/user-attachments/assets/76591fdf-5ee1-46e3-af05-acb22dc0f337" />

### 7.3.3 PAC-Larnability of Othr Concept Classes

Equation (7.2) provides a general way to bound the **sample complexity** for learning target concepts in a given class \( C \). Previously, it was applied to **Boolean conjunctions**, showing they have **polynomial sample complexity**. However, not all concept classes share this property.

#### 7.3.3.1 **Unbiased Learners**
An **unbiased concept class** includes every possible teachable concept relative to \( X \). The total number of target concepts corresponds to the **power set** of \( X \), leading to \( |C| = 2^{|X|} \). For instances defined by \( n \) Boolean features, the number of concepts grows exponentially as \( |C| = 2^{2^n} \).

Since an unbiased learner must use a **hypothesis space equal to the concept space** (\( H = C \)), substituting \( |H| = 2^{2^n} \) into Equation (7.2) results in **exponential sample complexity** under the PAC model. This means **unbiased concept classes are not PAC-learnable**.

#### 7.3.3.2 **k-Term DNF and k-CNF Concepts**
Some concept classes have **polynomial sample complexity** but **cannot be learned in polynomial time**. An example is **k-term Disjunctive Normal Form (k-term DNF)**, where each term is a conjunction of Boolean attributes and their negations. Although the **sample complexity** of k-term DNF is polynomial in \( 1/\epsilon, 1/\delta, n, \) and \( k \), its **computational complexity** is not polynomial, as solving this learning problem is equivalent to problems that are **NP-hard** (unless RP = NP).  

Surprisingly, a **larger concept class**, **k-CNF (k-Clause Conjunctive Normal Form)**, is **PAC-learnable** despite being more expressive than k-term DNF. Since any k-term DNF can be rewritten as a k-CNF (but not vice versa), k-CNF enables **polynomial-time learning** while maintaining **polynomial sample complexity**. Thus, k-term DNF is **PAC-learnable using a hypothesis class of k-CNF**.

##7.4 **Sample Complexity for Infinite Hypothesis Spaces**
When analyzing **sample complexity** in **PAC learning**, Equation (7.2) relates complexity to the logarithm of the hypothesis space size (\(|H|\)). However, this approach has limitations:
1. It can lead to **weak bounds** for large hypothesis spaces.
2. It **cannot be applied to infinite hypothesis spaces**.

To address these issues, a more refined measure, the **Vapnik-Chervonenkis (VC) dimension**, is introduced. **VC dimension (VC(H))** provides a tighter and more useful characterization of sample complexity, particularly for infinite hypothesis spaces.

### 7.4.1 Shattering a Set of Instances

The **VC dimension** measures how well a hypothesis space **H** can discriminate between instances, rather than counting the number of hypotheses. It is defined using the concept of **shattering**:
- A hypothesis space **H** **shatters** a set of instances **S** if it can **represent every possible dichotomy** (labeling) of **S**.
- If a hypothesis space **fails to shatter** a set, there exist some labelings that **cannot be expressed** by any hypothesis in **H**.
- The ability to **shatter** a set indicates the **capacity of H** to represent different target concepts.

<img width="503" alt="image" src="https://github.com/user-attachments/assets/9ca287c0-1762-48f7-a079-138badf59770" />

Figure 7.3 illustrates an example where **three instances** are shattered by a hypothesis space, meaning every possible labeling is covered by some hypothesis.

#### 7.4.2.1 Illustrative Examples

### **Illustrative Examples of VC Dimension**
This section provides illustrative examples to build intuition about the **VC dimension** \( VC(H) \) for different hypothesis spaces.

#### **1. Intervals on the Real Line**
- The instance space \( X \) consists of real numbers, and the hypothesis space \( H \) includes all intervals of the form \( a < x < b \).
- A set of **two** distinct points can be shattered since all possible dichotomies can be represented by intervals.
- However, a set of **three** points **cannot** be shattered because some dichotomies (e.g., including the first and last but excluding the middle) cannot be represented by a single closed interval.
- **Conclusion:** \( VC(H) = 2 \), despite \( H \) being infinite.

<img width="511" alt="image" src="https://github.com/user-attachments/assets/476167be-81fd-4ac0-8d61-1df0b0dcc032" />

#### **2. Linear Decision Boundaries in 2D**
- The instance space \( X \) is the 2D plane, and \( H \) consists of **all linear decision boundaries** (i.e., perceptrons with two inputs).
- Any **two** distinct points can be shattered.
- Any **three** non-collinear points can be shattered using linear decision surfaces.
- However, **four** points **cannot** always be shattered.
- **Conclusion:** \( VC(H) = 3 \), and in general, the VC dimension of linear classifiers in \( r \)-dimensional space is \( r + 1 \).

#### **3. Boolean Conjunctions**
- Each instance in \( X \) is described by three Boolean literals (\( l_1, l_2, l_3 \)), and hypotheses in \( H \) are conjunctions of up to three literals.
- A set of **three** instances can be shattered by constructing hypotheses that exclude specific instances.
- This concept generalizes to **n** Boolean literals.
- **Conclusion:** The VC dimension for conjunctions of **n** Boolean literals is **exactly** \( n \).

These examples illustrate that **VC dimension is independent of the size of \( H \)** and depends on the complexity of how hypotheses can separate instances.

### 7.4.3 Sample Complexity and the VC Dimension  

The sample complexity of learning is closely tied to the VC dimension, providing both upper and lower bounds on the number of training examples required for Probably Approximately Correct (PAC) learning.  

- **Upper Bound (Blumer et al., 1989):**  
  - The number of required training examples grows logarithmically with \(1/\epsilon\) and linearly with VC(H).  
  - The complexity measure \( \log |H| \) is replaced by VC(H), making the bound more refined.  

- **Lower Bound (Ehrenfeucht et al., 1989):**  
  - If the number of training examples is too small, no learner can PAC-learn every target concept in any nontrivial concept class \( C \).  
  - This provides a necessary minimum number of training examples to ensure successful learning.  

Both bounds are logarithmic in \(1/\delta\) and linear in VC(H), with the upper bound differing slightly due to an additional \(\log(1/\epsilon)\) term.  

### 7.4.4 VC Dimension for Neural Networks  

The VC dimension of layered feedforward neural networks can be bounded based on their structure and the VC dimension of their individual units.  

- **Theorem (Kearns & Vazirani, 1994):**  
  - The VC dimension of a layered directed acyclic graph (DAG) network grows linearly with the VC dimension of individual units and logarithmically with the number of internal nodes.  
  - For perceptron-based networks:  
    - A perceptron with \( r \) inputs has a VC dimension of \( r + 1 \).  
    - This property extends to layered networks, allowing us to estimate the number of training samples required for PAC learning.  

- **Limitations for Backpropagation:**  
  1. The theorem applies to perceptron networks, while backpropagation is used for sigmoid-based networks. However, sigmoid units have at least the same VC dimension as perceptrons.  
  2. It does not account for backpropagation's inductive bias, which favors networks with smaller weights and effectively reduces the VC dimension.  

This result provides a general method for bounding the VC dimension of acyclic layered networks but does not fully capture the properties of backpropagation-trained networks.  

## 7.5 The Mistake Bound Model of Learning  

The **Mistake Bound Model** evaluates a learner based on the number of mistakes it makes before converging to the correct hypothesis.  

- **Key Differences from PAC Learning:**  
  - PAC learning focuses on the number of training examples needed for approximate learning.  
  - The mistake bound model requires the learner to predict before seeing the correct answer.  
  - The goal is to minimize the total number of mistakes.  

- **Practical Significance:**  
  - Useful in real-time learning scenarios, such as fraud detection, where mistakes have consequences.  
  - More relevant than just the number of training examples in certain applications.  

- **Learning Settings:**  
  - Can be analyzed in different contexts, including PAC learning and exact learning.  
  - Exact learning requires the hypothesis to match the target function perfectly for all instances.  

### 7.5.1 Mistake Bound for the FIND-S Algorithm  

The **FIND-S Algorithm** incrementally generalizes a maximally specific hypothesis by removing literals inconsistent with positive examples.  

#### Key Properties:  
- **No False Positives:** If the target concept is in the hypothesis space, FIND-S never classifies a negative example as positive.  
- **Mistakes Only on Positive Examples:** Errors occur when a positive example is initially classified as negative.  
- **Incremental Generalization:** Each mistake removes at least one literal from the hypothesis.  

#### Mistake Bound Calculation:  
1. **First Mistake:** Eliminates half of the initial \( 2^n \) literals, leaving \( n \) terms.  
2. **Subsequent Mistakes:** Each removes at least one more term.  
3. **Worst Case Bound:** A maximum of \( n + 1 \) mistakes are made before FIND-S converges to the correct hypothesis.  

### 7.5.2 Mistake Bound for the HALVING Algorithm  

The **HALVING Algorithm** refines the version space by iteratively removing inconsistent hypotheses. It makes predictions using a **majority vote** of the current hypotheses and continues until the version space contains only the correct target hypothesis.  

#### Key Properties:  
- Predictions are based on a majority vote.  
- Mistakes happen only when the majority misclassifies an example.  
- Each mistake eliminates at least half of the hypotheses.  

#### Mistake Bound Calculation:  
- The version space starts with \( |H| \) hypotheses.  
- Each mistake reduces the space by at least half.  
- The worst-case bound is **\( \log_2 |H| \)** mistakes.  

#### Special Cases & Extensions:  
- The algorithm may learn the target **without any mistakes** if incorrect hypotheses are consistently eliminated.  
- A weighted voting variant (e.g., **Bayes optimal classifier**) assigns probabilities to hypotheses based on training data.  

### 7.5.3 Optimal Mistake Bounds  

The **optimal mistake bound** defines the **minimum worst-case mistakes** any algorithm can make when learning a concept class \( C \). It sets a theoretical lower bound for all possible learning strategies.  

#### Key Definitions:  
- \( M_A(C) \): The worst-case mistake bound for algorithm \( A \) on concept class \( C \).  
- **Optimal mistake bound** \( \text{Opt}(C) \): The smallest possible worst-case mistake bound over all algorithms.  

#### Key Results:  
- **FIND-S Algorithm**: \( M_{\text{Find-S}}(C) = n + 1 \) (boolean literals).  
- **HALVING Algorithm**: \( M_{\text{Halving}}(C) = \log_2 |C| \).  
- Littlestone (1987) showed that \( \text{Opt}(C) \) is closely related to the **VC dimension** and the HALVING bound.  
- For some concept classes (e.g., **powerset class**), \( \text{VC}(C) = \text{Opt}(C) = \log_2 |C| \).  
- However, some classes satisfy \( \text{VC}(C) < \text{Opt}(C) < M_{\text{Halving}}(C) \).  

### 7.5.4 WEIGHTED-MAJORITY Algorithm  

The **WEIGHTED-MAJORITY Algorithm** is a generalization of the **HALVING Algorithm**, using **weighted voting** among a pool of prediction algorithms. It dynamically adjusts algorithm weights based on classification performance, making it more flexible than elimination-based approaches.  

#### **Key Properties:**  
- **Handles inconsistent training data** by reducing weights rather than eliminating algorithms.  
- **Adapts to the best performing algorithm** over time.  
- **Bounds the number of mistakes** relative to the best algorithm in the pool.  

#### **Algorithm Steps:**  
1. Initialize all algorithm weights to **1**.  
2. For each training example:  
   - Compute weighted votes.  
   - Predict using majority vote.  
   - Reduce the weight of incorrect algorithms by a factor \( \beta \) (where \( 0 \leq \beta < 1 \)).  

#### **Theoretical Bound on Mistakes:**  
- If **\( k \)** is the number of mistakes made by the best algorithm, WEIGHTED-MAJORITY makes at most **\( 2.4(k + \log_2 n) \)** mistakes, where \( n \) is the pool size.  
- The mistake bound **scales logarithmically** with \( n \), keeping it efficient.  
- Littlestone & Warmuth (1991) generalized this bound for any \( 0 \leq \beta < 1 \).  

<img width="129" alt="image" src="https://github.com/user-attachments/assets/60417f47-b98e-488a-868b-42bfb53714cb" />

## Summary of Section 7.6: Summary and Further Reading

- **PAC Learning Model**: The Probably Approximately Correct (PAC) model focuses on algorithms learning target concepts from a concept class \( C \) using randomly drawn training examples. It ensures that with high probability (\(1 - \delta\)), a hypothesis within error \( \epsilon \) is learned, requiring training data and computational effort that scale polynomially with \( 1/\epsilon, 1/\delta \), instance size, and concept complexity.

- **Consistency in PAC Learning**: Any consistent learner with a finite hypothesis space \( H \) (where \( C \subseteq H \)) will output a hypothesis with error \( \epsilon \), given a sufficient number of randomly drawn training examples.

- **Agnostic Learning Model**: Unlike PAC, this model does not assume prior knowledge of the concept class. Instead, the learner selects the hypothesis with minimal training error, ensuring with probability \( 1 - \delta \) that its error is within \( \epsilon \) of the best hypothesis in \( H \).

- **Complexity and VC Dimension**: The complexity of a hypothesis space \( H \) affects learning requirements. The Vapnik-Chervonenkis (VC) dimension, \( VC(H) \), measures the maximum number of instances that can be shattered (fully separated) by \( H \). Upper and lower bounds on required training samples are derived from \( VC(H) \).

- **Mistake Bound Model**: This model examines how many training examples a learner misclassifies before perfectly learning the target concept. The **Halving Algorithm** guarantees at most \( \log_2 |H| \) mistakes before convergence, while the worst-case bound for any class \( C \) is **Opt(C) ≥ VC(C)**.

- **Weighted-Majority Algorithm**: This algorithm classifies instances using weighted votes from multiple predictors, adjusting weights based on errors. The number of mistakes made is bounded relative to the best-performing predictor in the pool.

- **Historical and Further Reading**: 
  - **Gold (1967)** introduced the Identification in the Limit model.
  - **Valiant (1984)** developed the PAC model, with further insights from **Vapnik (1982)** and **Haussler (1988)**.
  - **Blumer et al. (1989)** compiled results on PAC learning.
  - **Kearns & Vazirani (1994)** provided an extensive discussion on computational learning theory.
  - Research continues in the **Computational Learning Theory (COLT) conference** and journals like *Machine Learning*.
