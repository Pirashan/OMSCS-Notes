# Module 1

This module covers lessons 1 through 5. Notes will be primarily from the main lecture content rather than external resources.

In the following lessons, we will cover the impacts that AI and ML have on individuals and society. We will look into a wide range of societal issues ranging from fairness and bias to ethics, legality, data collection, and privacy.

## Lesson 1 Introduction

### What Is Big Data

**Big data** is the term increasingly used to describe the process of applying serious computing power - the latest in ML and AI - to seriously massive and often highly complex sets of information. As of 2019, there are 2.5 quintillion bytes of data created each day at our current pace.

Some of the goals of this class include:

- How do we design algorithms that effectively deal with the large amounts of data that are used to train them, while ensuring their outcomes aren't misused?
- We will examine various AI/ML techniques that can be used to counterbalance the potential abuse and misuse of learning from big data, with a focus on the impacts of these technologies on society

## Lesson 2 Overview

### Targeted Messaging

- Big data allows organizations to now target specific demographics (not possible 20 years ago)
- Big data also allows organizations to do a lot more than targeted advertising

### Whats The Problem

Humans are inherently biased. If bad data is used to train an algorithm then results will have unintended consequences.

## Lesson 3 Ethics Vs. Law

### AI And Unintended Consequences

There are many unintended consequences if algorithms are trained with bad data:

- Appearance biases in identity software
- Gender biases in identity software
- Biases in AI chat bots
- Biases in health systems
- Biases in automated hiring systems
- Biases in automated justice systems

### Relationship Between Ethics And Law

**Law** is the system of rules of conduct established by the government of a society to maintain stability and justice. Law defines the legal rights and duties of the people and provides the means of enforcing these rights and duties

**Ethics** is defined as the set of moral principles that distinguish what is right from what is wrong. **Moral standards** are rules about the kinds of actions that are morally right or wrong, as well as the values placed on what is morally good or bad.

Note that laws carry sanctions of a governing authority whereas ethics do not.

There are three primary relationships between ethics and law:

1. Overlap
2. No overlap
3. Conflict

### Overview Of US Laws

There are several general categories of US law:

- Civil
- Criminal
- Private
- Public

On the other hand, the purpose of _regulations_ is to achieve certain public desired goals that the market may fail to realize (i.e., protect to public). Some examples include:

- Credit
- Education
- Employment
- Housing and public accommodation

**Discrimination** is prohibited on the basis of membership in a protected class-group which has historically been discriminated against.

The protected classes are as follows:
- Race (Civil Rights Act of 1964, 1991)

- Color (Civil Rights Act of 1964, 1991)

- Sex (Equal Pay Act of 1963; Civil Rights Act of 1964, 1991)

- Religion (Civil Rights Act of 1964, 1991)

- National origin (Civil Rights Act of 1964, 1991)

- Citizenship (Immigration Reform and Control Act)

- Age (Age Discrimination in Employment Act of 1967) (over 40)

- Pregnancy (Pregnancy Discrimination Act)

- Familial status (Civil Rights Act of 1968)

- Disability status (Rehabilitation Act of 1973; Americans with Disabilities Act of 1990)

- Veteran status (Vietnam Era Veterans' Readjustment Assistance Act of 1974; Uniformed Services Employment and Reemployment Rights Act)

- Genetic information (Genetic Information Nondiscrimination Act)

Forms of discrimination (or bias) include:

- Intentional
- Unconscious

How do we know if a group is statistically discriminated against?

- Numerical analysis suggests that groups are treated or affected differently although one must rule out other explanations (very difficult)
- Direct evidence showing deliberate intention in a particular case, e.g., various documents, conversations, compensation patterns, etc.; however, this data is typically not available to individuals

**Equality of opportunity** is typically concerned with ensuring that decision-making processes treat similar people similarly on the basis of relevant features, given their current degree of similarity.

**Equality of outcome** is a notion of equality of opportunity that forces decision-making to treat seemingly dissimilar people similarly, on the belief that their current dissimilarity is the result of past injustices.

### Ethical Decision Making

**Dilemma** occurs when a decision that could benefit a person, organization, or both, might also cause harm with others. Cultural differences also create difficulty in determining what is and is not ethical. Difficulties arise when one community's ethical construct conflicts with the ethics of another community.

### Code Of Ethics

Professional boards and organizations have written cods which hold members to a higher standard than the law imposes - ethic codes.

### Ethical Issues For Big Data

There are four main ethical issues regarding big data:

1. **Privacy**: right of individual to control personal information
2. **Accuracy**: who is responsible for the authenticity, fidelity, and accuracy of information?
3. **Property**: who owns the information and who controls access?
4. **Accessibility**: what information does an organization have the right to collect? Under what safeguards? What can they do with it after?

Frameworks for handling ethics issues and making decisions include:

1. **Consequence-based ethics**:
   - Priority is given to choices that lead to a good outcome
   - The outcome outweighs the method
   - **Utilitarian view**: the _right_ choice delivers the greatest good to the most people
   - **Individualism view**: the _right_ choice is best for long-term self-interest
2. **Rule-based ethics**:
   - Priority is given to following the rules without undue regard to the outcome
   - Rules are often thought to codify principles like truthfulness, right to freedom, justice, etc.
   - **Moral-rights view**: the _right_ choice is that which respects fundamental rights shared by all human beings
   - **Rule-based/justice view**: the _right_ choice is that which is impartial, fair, and equitable in treating people; exists for the benefit of society and should be followed

### Example Ethical Issue

Scenario: code is stolen from a competitor but could potentially save millions of lives. Who is right?

- Moral-rights view: come out and tell the truth to the public regardless of consequences
- Utilitarian view: we can save millions of lives now so why not?

## Lesson 4 Data Collection

### Information Privacy

**Information privacy** is the relationship between the collection and dissemination of data, technology, the public expectation of privacy, legal, and political issues surrounding them.

### Data Management Practices

Who owns our data? There are billions of users online everyday that unknowingly have their data collected by mysterious third parties. Why is it that for most services we use in life there is ownership but when it comes to data the answer is ambiguous?

### Intellectual Property Rights And Protections

**IP (intellectual property) rights** are the rights given to persons over the creations of their minds. They usually give the creator an exclusive right over the user of his/her creation for a certain period of time. When you create information, you typically acquire the rights to that information. Consequently, unauthorized replication and/or re-use of your information would be a breach of your rights.

Thankfully, laws such as **GDPR (General Data Protection Regulation)** imposes new rules on organizations that offer goods and services to people in the EU (European Union). Key GDPR clauses include:

- Valid consent must be _explicit_ (opt-in based) for data collected and the purposes data is used
- The data subject has the right to request _erasure_ of personal data related to them
- A person shall be able to transfer their personal data from one electronic processing system to and into another, without being prevented from doing so
- As of May 2018, has force of law and includes steep penalties
- Law is _extraterritorial_ (i.e., applies to any organization which stores, transfers, or otherwise processes data from EU citizens, regardless of whether that organization is based in the EU or not)

## Lesson 5 Fairness And Bias

### What Is Bias

**Bias** is a predisposition, partially, prejudice, preference, or prediction. Biases have to do with:

- Stereotypes
- Prejudice
- Discrimination

### An Incorrect Assumption About AI

An incorrect assumption about AI is that algorithmic inputs include only objective elements, they thus should **not** be biased. However, there exists many counter-examples that disprove this assumption as we mentioned in previous lessons.

### Algorithmic Bias​

The problem with biases in algorithms is that the data used to train algorithms were likely created by humans which are inherently biased.

Another issue is that algorithms are black boxes since algorithms owned by companies are considered proprietary information and are outside of regulators' jurisdiction. This obscures biases and consequently makes it difficult to mitigate bias.

### Biases In Data​

How can data be biased?

- **Data inputs**: incomplete, incorrect, or outdated inputs, poor selection of inputs, and historically biased inputs
- **Algorithmic processing**: decision-making systems that assume $correlation \Rightarrow causation$, misrepresented populations, complex outputs

Additionally, the data collection and measurement processes could introduce bias in out data. Some biases are preexisting. All the above issues makes it difficult to identify which specific group the algorithm might be biased against.

Another problem that exists is that if researchers want to find if bias exists with respect to individuals having attribute $X$, they would likely have to _infer_ attribute $X$ from a database which implies that companies would have to reconstruct data (a potential privacy violation).

### Fairness​

How can we ensure that our algorithms act in ways that are _fair_? **Algorithmic fairness** is a vague and somewhat circular concept which make be related to accountability, transparency, or safety. Generally there is tension between:

- Different notions of fairness
- Fairness and accuracy
- Different methods for achieving fairness

One idea to eliminate biases in our data is to remove the sensitive attribute in our data. However, in practice sensitive attributes could already be correlated with other attributes where it is fairly easy to predict class given other supporting information. More advanced bias mitigation strategies are required in this scenario.

### Principles For Quantifying Fairness​

How do we go about quantifying fairness? We can use the loan scenario as an example:

- **Statistical parity**: ensure group fairness requires the same percentage of A and B receiving the same service. One issue is what happens if one group is more likely to repay vs. another?
- **Consistency**: ensure individual fairness by ensuring similar individuals experience similar outcomes. One issue is what happens if a _fair_ outcome treats everyone poorly?

# Module 2

This module covers lessons 6 through 11. Notes will be primarily from the main lecture content rather than external resources.

In the following lessons, we will go over the underlying components of big data and statistical techniques. We will also cover issues that occur when learning from Big Data.

## Lesson 6 Overview

### Why Statistics

Data is everywhere and statistical techniques are used to make decisions that affect our lives. **Statistics** is:

> The science of collecting, organizing, presenting, analyzing, and interpreting data to assist in making more effective decisions

Consequently, **statistical analysis** is used to manipulate, summarize, and investigate data so that useful decision-making information results. The term statistics, derived from the word state, was used to refer to a collection of facts of interest to the
state.

### How To Mislead Through Poor Sampling

In order to analyze and interpret data, we must first collect it. The data that is collected is known as a **sample**. The sample is collected from a **population**.

### How To Mislead Through Poor Analysis

**Data analysis** is a process of gathering, modeling, and transforming data with the goal of highlighting useful information, suggesting conclusions, and supporting decision making. If we aren’t careful, data analysis could mislead by miscalculating trends.

### How To Mislead Through Interpretation

Interpreting data often involves displaying it in some useful way (e.g. chart, graphs, etc.). Unfortunately it is fairly easy to lie, cheat, manipulate, or mislead the public with graphical displays.

## Lesson 7 Python And Stats 101

### Defining Data Analytics

There are two types of analytics:

1. **Descriptive analytics**: methods of organizing, summarizing, and presenting data in an informative way
2. **Inferential analytics**: the methods used to determine something about a population on the basis of a sample

**Big data** focuses on issues with handling non-traditional _big_ data whereas **data analytics** focuses on gaining meaningful insight regardless of the size of the data. Data analytics depends heavily on machine learning.

### All About The Data

Stats starts with data, the facts and figures collected, summarized, analyzed, or interpreted. Data can come in various flavors:

- **Quantitative/qualitative**
- **Continuous**: data is infinitely divisible into whatever units a researcher may choose
- **Ordinal/rank**: in order but not necessarily equal (eg. letter grades)
- **Categorical/discrete**: data consists of indivisible categories

Ordinal/rank could look the same as categorical/discrete in certain cases.

**Cross-Sectional Data** are collected at the same or approximately the same point in time, as opposed to **Time-Series Data** which is collected over several time periods.

### Introduction To Python And Jupyter

Objective for this section is to cover key concepts in statistics and
Python data analytics:

- Python basics for stats/data analytics
- Python data analytics libraries
- Jupyter Notebook

### Basic Statistical Measures And Data Analytics Using Python

**Jupyter Notebook** (browser-based interpreter) is an open source web-based interactive data analysis environment that supports iPython, a Python command shell for interactive computing.

Jupyter Notebook documents allow us to incorporate text, code, as well as the output.

### Hands On Tutorial: Pandas Basics 1

Optional tutorial for Pandas basics: [Pandas Tutorial 1: Pandas Basics (Reading Data Files, DataFrames, Data Selection)](https://data36.com/pandas-tutorial-1-basics-reading-data-files-dataframes-data-selection/).

## Lesson 8 Descriptive Statistics

### Types Of Studies And Sampling Errors

Recall that descriptive analytics are methods of organizing, summarizing, and presenting data in an informative way which may include:

- Frequency tables
- Histograms
- Mean
- Variance

While inferential analytics are the methods used to determine something about a population on the basis of a sample (ML/AI for big data) which may include:

- **Population**: the entire set of individuals or objects of interest or the measurements obtained from all individuals or objects of interest
- **Sample**: a portion, or part, of the population of interest

There are various types of studies:

- **Experimental**: one variable is manipulated. A second variable is observed and measured to determine effect of manipulated variable. The measurements are then compared to see if there are differences between conditions
- **Correlation**: determine whether there is a relationship between two variables and to describe the relationship. A correlational study simply observes the two variables as they exist naturally
- **Quasi-experimental**: compares groups based on a variable that differentiate the groups (e.g., male/female)

The discrepancy between a sample statistic and its population parameter is called **sampling error**. We will look at this later through the lens of **sampling bias**.

### Median, Mean, And Mode

Recall the following definitions:

- **Mean**: the arithmetic average which is best for symmetric distributions
- **Median**: the middle value in an **ordered sequence** of observations which is _less_ sensitive to outliers (extreme scores) than the mean and thus a better measure than the mean for highly skewed distributions (**not normally distributed**). This is for an **ordered sequence** of observations.
- **Mode**: the most frequently occurring number

### How To Mislead With Averages

Since it is fairly easy to mislead with poor sampling, analysis, and interpretation, it should be no surprise that it would be easy to mislead with averages which can tell a completely different story when broken down (see real-estate example in lecture).

### Frequency Distribution

A **frequency distribution** keeps count of the number of times a data item occurs by keeping a tally. The number of times the item occurs is called the frequency of that item. With a _cumulative_ frequency distribution, you can also find a _running total_ of frequencies. It is useful to know the running total of the frequencies as this tells you the total number of data items at different stages in the data set.

### Variability

**Variability** (or dispersion) measures the amount of scatter in a dataset. Gives us an indication of how well the **average characterizes the data as a whole**.

Commonly used variability methods include: range, variance, standard deviation, inter-quartile range, coefficient of variation, etc.

**Range** is the difference between the largest and the smallest observations.
**Variance** is the average of the squares of the deviations of the observations from their mean.
**Standard Deviation** is the square root of the variance.
**Quartiles** are the cut points of data being divided into four regions.

The **five number summary**: is a summary of a distribution which consists of:

1. Min
2. Q1 (first quartile or min to 25% of the data)
3. Q2 (second quartile or 25% to 75% of the data where the upper bound is the median)
4. Q3 (third quartile or 75% to max of the data)
5. Max

**Anscombe's quartet** comprises four datasets that have nearly identical simple statistical properties, yet appear very different when graphed (see [Anscombe's Quartet Worksheet](https://www.geogebra.org/m/PNg789TK) for more information).

### Descriptive Statistics In Pandas

This section covers general Pandas methods and examples for descriptive statistics (see lecture for more details).

### Hands On Tutorial: Pandas Basics 2

Optional tutorial for Pandas basics: [Pandas Tutorial 2: Pandas Basics (Aggregation and Grouping)](https://data36.com/pandas-tutorial-2-aggregation-and-grouping/).

## Lesson 9 Inferential Statistics: Sampling Bias

### Inferential Statistics Introduction

Recall that inferential statistics provide numerical indications of how likely it is that a given event will occur. It is an inference based on a sample that indicates the likelihood of something for the total population.

<img width="400" alt="image" src="https://github.com/user-attachments/assets/dc4d79fd-d112-4d27-b390-2b8c367f1086" />

A **common mistake** is that not **all samples** will lead to **good predictions** about an **entire population**.

**Statistical probability** is the odds that what we observed in the sample did not occur because of errors (random and/or systematic). In other words, the probability associated with a statistics is the **level of confidence** we have that the sample group that we measured actually represents the total population.

### Warm-up Exercise

This section includes a warm-up exercise (see lecture for more details).

### Simpson’s Paradox

**Simpson’s paradox** is a phenomenon in probability and statistics in which a trend appears in several different groups of data but disappears or reverses when these groups are combined.

### Biased Sampling

The equation to measure statistical bias can be summarized as:

$Bias = E(x) - Mean$

Where $E(x)$ is the [expected value](https://en.wikipedia.org/wiki/Expected_value) (or mean of the means) of our data and $Mean$ corresponds to the true mean. If the expected value is the same as the true mean then we may say that the estimator is _unbiased_ (unlikely in practice).

Since we can’t have a boundless survey that covers all data points. There are many different types of sampling bias:

- **Area bias**: introduced by conducting the study in a specific area that does not include a representative sampling of the population being studied
- **Selection bias**: introduced by the selection of individuals, groups or data for analysis in such a way that proper randomization is not achieved, thereby ensuring that the sample obtained is not representative of the population intended to be analyzed
- **Self-selection bias**: when a participants' decision to participate may be correlated with traits that affect the study, making the participants a non-representative sample
- **Leading question bias**: biases respondents by giving them a clue to the desired answer or leads respondents to answer a certain way, resulting in the tendency for respondents to agree with the direction of the leading question
- **Social desirability bias**: type of response bias that is the tendency of respondents to answer questions in a manner that will be viewed favorably by others

### Biased Sampling Example

_What seems to be a good sampling method (provided in lecture)_?

- B, since the distribution is normal and the population parameter is right in the middle of the distribution.
However, real world situations do not always follow a Gaussian distribution!

### Types Of Randomized Sampling

Benefits of **randomized sampling** include:

- Reduces issues with sampling bias
- Ensures that on average the sample set looks like the rest of the population
- Enables us to make rigorous probabilistic statements concerning possible error in the sample

Randomization methods include:

- Random sampling
- Simple random sampling

In **systematic sampling**, all data is sequentially numbered and every $n$ piece of data is chosen. We can combine this technique with random sampling to systematically generate a randomized sample.

Additionally, data may be divided into subgroups (strata) as in **stratified sampling** or clustered as in **cluster random sampling** where each cluster is a miniature version of the entire population (useful when it is difficult and costly to develop a complete list of the population members).

The high cost of obtaining data has some companies looking for data on the internet. On the internet a common sampling method is **non-probability sampling** where participants are chosen or choose themselves so that the chance of being selected is not known.

**Simple Random Sampling** is when each population element has an equal chance of being selected into the sample. Sample drawing using random number table/generator.

**Systematic Sampling** is when an element of the population is selected at the beginning with a random start, and following the sampling skip interval selects every kth element.

**Stratified Sampling** is when we divide into subpopulations or strata and use simple random sampling on each stratum. Results may be weighted or combined.

**Cluster Random Sampling**
- Sometimes stratifying isn't practical and simple random sampling is difficult
- Splitting the population into similar parts or clusters can make sampling more practical
- Each cluster should be a miniature version of the entire population
- Then we could select one or a few clusters at random and select a simple random sample from each chosen cluster
- If each cluster fairly represents the full population, cluster random sampling will give us an unbiased sample

This is useful when it is **difficult and costly** to develop a complete list of the population members.

**Non-Probability Sampling**
- The high cost of obtaining data has companies looking to data on the internet.
- Non-probability sampling: participants are chosen or choose themselves so that the chance of being selected is not know.
- **No one has figured out how to select a representative sample of internet users that reflects a global population.**

### Sampling Bias Example Experiments

This section includes sampling bias examples (see lecture for more details).

## Lesson 10 Inferential Statistics: Causation Vs. Correlation

### Correlation Vs. Causation

Correlation tells us two variables are _related_. Types of relationship reflected in correlation:

1. $X$ causes $Y$ or $Y$ causes $X$ (**causal relationship**)
2. $X$ and $Y$ are caused by a third variable $Z$ (**spurious relationship**)

Of course, correlation does not imply causation!

The **correlation coefficient** summarizes the association between two variables. A zero correlation coefficient indicates no linear relationship. A value of +1 indicates a perfect positive correlation, while a value of -1 indicates a perfect negative correlation.

### Correlation Vs. Causation Examples

This section includes correlation vs. causation examples (see lecture for more details).

### Relationships

A strong relationship between two variables does **not** always mean that changes in one variable causes changes in the other. The relationship between two variables is often influenced by other variables which are lurking in the background.

There are two relationships which can be mistaken for causation:

1. **Common response**: refers to the possibility that a change in a _lurking variable_ is causing changes in both our explanatory variable (x) and our response variable (y).
2. **Confounding**: refers to the possibility that either the change in our explanatory variable is causing changes in the response variable OR that a change in a _lurking variable_ is causing changes in the response variable.

### Additional Material: Measuring Linear Correlation In Python

This section includes materials for measuring linear correlation in Python (see lecture for more details).

## Lesson 11 Inferential Statistics: Confidence

### Empirical Rule

The [empirical rule](https://www.investopedia.com/terms/e/empirical-rule.asp) or three-sigma rule states that 99.7% of data observed following a normal distribution, or Gaussian Distribution, lies within 3 standard deviations of the mean. Additionally, 68% of the data falls within one standard deviation, 95% percent within two standard deviations, and 99.7% within three standard deviations from the mean.

### Population Proportions And Margin Of Error

When sampling from the population, we could say with a certain degree of confidence - if the sample was _large enough and representative_, then the proportion of the sample would be approximately the same as the proportion of the population.

Since we are 95% certain that the population proportion is within 2
standard deviations of the sample proportion (by the empirical rule), the **margin of error** in this scenario is:

$MOE = \frac{1}{\sqrt{n}}$

Where $MOE# is margin of error and $n$ is the sample size.

### Sample Size Vs. Margin Of Error

The size of the population does not matter. Margin of error estimates how accurately the results of a poll reflect the _true_ feelings of the population. In general, as sample size _increases_, margin of error _decreases_.

# Module 3

This module covers lessons 12 through 18. Notes will be primarily from the main lecture content rather than external resources.

In the following lessons, we will go more in-depth on the different types of AI algorithms deployed in practice (e.g., facial recognition, NLP, and predictive algorithms). We continue to focus on instituting _fairness_ in these algorithms by examining scenarios, tools used in each scenario, ethical issues, and possible solutions.

## Lesson 12 Word Embeddings

### Fairness In AI/ML

The goal of this lesson is to understand and apply basic AI/ML techniques to data scenarios, with a focus on instituting _fair_ practices when designing decision-making systems based on big data.

### Word Embedding (NLP)

- Word embeddings are a _set of techniques_ in **NLP (natural language processing)** for identifying similarities between words in a corpus by using some type of model to _predict the co-occurrence_ of words within a small chunk of text
- Word embeddings _transform human language_ meaningfully into a _numerical form_. This allows computers to understand the nuances implicitly encoded into our languages

### Word Similarity And Relatedness

How do we determine similarities and relatedness for words?

- _Representing words_ has become a convenient way to compute _similarities_ (e.g., pizza to pasta)
- **Relatedness**: measures the semantic similarity between words (e.g., pizza to Italy)

Regarding vector space models:

- **Vectorization**: the process of converting text to numbers. This conversion helps us to measure the similarity between words
- **Vector space model**: an algebraic model for representing text as a vector of identifiers in which semantically similar words are mapped to proximate points in geometric space

Vectors space models can be represented as:

- **Document occurrence**: assign identifiers corresponding to the count of words in each document (from a cluster of documents) in which the word occurs
- **Word context**: quantify co-occurrence of terms in a corpus by constructing a co-occurrence matrix which captures the number of times a term appears in the context of another term

### Cosine Similarity And Word Analogy

We can use **cosine similarity** to compute the similarity between two word vectors. However, this notion of similarity depends on what vector representation is selected to represent the words found in your corpus. Given two vectors $a$ and $b$, the cosine similarity is defined as the _dot-product_ of the two vectors divided by their _length_.


A value of 1 mans the vectors are quite similar to eachother, while -1 means they are similar but opposite.

Word analogy problems have become one of the _standard tools for evaluating context-based word vectors_.

### Word Embeddings (`word2vec`)

> Word2vec is a technique for natural language processing published in 2013. The word2vec algorithm uses a neural network model to learn word associations from a large corpus of text. Once trained, such a model can detect synonymous words or suggest additional words for a partial sentence. As the name implies, word2vec represents each distinct word with a particular list of numbers called a vector. The vectors are chosen carefully such that a simple mathematical function (the cosine similarity between the vectors) indicates the level of semantic similarity between the words represented by those vectors. -Wiki

- Stores each word as a point in space, where it is represented by a vector of a fixed number of dimensions (generally 30)
- Unsupervised, built just by reading huge corpus of data
- Dimensions are projections along different axes

Predict the context of a given word by learning probabilities of co-occurrence from a corpus.
In theory, words that share similar contexts tend to have similar meanings. As such, instead of counting co-occurrences directly, we should be able to generate word vectors that can predict the context of a word based on its surrounding words by learning form a corpus of data.

Continuous Bag of Words is a neural network that ist rained to predict which word fits in a gap in a sentence. For example, given the partial sentence "the student _ the exam", the neural network predicts that "passed" has a high probability of filling the gap.

Skip gram starts with a single word embedding and tries to predict the surrounding words. Word2vec uses words a few positions away from each center word to predict similarities between every word and its context words. The pairs of center word/context word are called "skip-grams".

## Lesson 13 Bias In Word Embeddings

### Bias In Word Embedding

The following biases occur in word embeddings:

- Cultural biases
- Biased framings of women
- Ethnic stereotypes
- African-american names are associated with unpleasant words
- Male names associated more with career words, female names with family words
- Competence adjectives are biased toward men

### Why Does This Happen (Word Embeddings)

In general, embeddings reflect ethnic stereotypes over time.

How do we go about fixing this issue? A couple of ways:

1. **Identify bias direction**: may involve calculating error differences and then averaging out the result (average difference)
2. **Neutralize**: for every word that is **not** definitional, _project_ to get rid of bias
3. **Equalize pairs**: for each pair of words, ensure that the vector length is equal

## Lesson 14 Facial Recognition

### Facial Recognition

Example of facial recognition:

- Exam identity verification
- Physical building access
- Computer/device access
- Passport verification
- Jail management systems and booking
- Law enforcement investigations
- Photo tagging in Facebook
- Smartphone and app access

### Facial Recognition Algorithms

In general, facial recognition algorithms involve:

- **Face detection**: to identify and locate human faces in an image regardless of their position, scale, in plane rotation, orientation, pose (out of plane rotation), and illumination
- **Two-class classification**: face vs. non-face

The objective of any face detection algorithm is to locate all faces, irrespective of:

- Positioning (e.g., frontal, side-view, upside down)
- Rotation and pose
- Occlusion
- Resolution or image quality
- In a _single_ image or a _sequence_ of images involving motion (such as in video)
- After detecting the face, image is typically _segmented_ based on this information, and normalizes for translation, scale, rotations

Types of facial recognition tasks:

- **Multi-class classification**: one person vs. all the others
- **Face identification**: given an image that belongs to a person in a database, tell which person it is
- **Face verification**: Given an image, verify whether it is from the same person it is claiming to be

**Face space** is a theory in psychology that defines a _multidimensional_ space in which recognizable faces are stored. The representation of faces within this space are according to _invariant features_ of the face itself.

Human biases during facial recognition include:

- **“Own-race” bias**: We are over twice as likely to identify own own-race than other-race. Less hits, more false alarms with other-race faces than with own-race faces
- **"Own-gender" bias**
- **"Own-age" bias**

Appearance-based methods (classifier) can be trained, typically using positive (and usually negative) examples of faces, for face recognition applications.

### Deep Neural Network Examples

**Deep neural networks** are now one of the most common methods for face recognition and in encoding attributes from the images. The general procedure includes:

1. _Extract_ facial features for an image
2. _Feed_ the features into a classifier such as a neural network
3. _Classify_ the image/features to one of the pre-selected emotion categories (6 universal emotions + neutral)

Cross-cultural research by Ekman shows (and has also been refuted by others) that some emotional expressions are universal:

- Happiness
- Sadness
- Anger
- Fear
- Disgust/surprise

Emotions are reflected in _voice_, _hand_ and _body gestures_, and mainly through _facial expressions_. By knowing a person’s emotion, an AI/ML system can adapt to the user. Responding appropriately to the user’s emotional state will be perceived as more natural, engaging, and trusting.

In addition to market research, emotion detection can be used to monitor driver attention, monitor movie audience reactions, and even help healthcare professionals assess the wellbeing of patients.

## Lesson 15 Bias In Facial Recognition

### Issues With Facial Recognition Algorithms

Identification becomes problematic due to:

- Resolution (not enough pixels)
- Facial pose (e.g., angled)
- Illumination
- Occluded facial areas

These result in distorted facial features, high errors in measurements, and limited data or feature points to analyze. No standards exist for _acceptable_ error rates meaning _success_ is subjective. It varies depending on the facial recognition system used and the application it’s used in. There are two kinds of errors:

1. **False-positives**: wrongly matching innocent people with photos in the database
2. **False-negatives**: not catching people even when their photo is in the database

### Bias In Facial Recognition

Some additional problems with facial recognition bias:

- **Priors**: demographics in law enforcement databases $\not =$ general population. More males, more minorities, younger age
- **Bias**: The most prominent study (Klare et al.) found that several leading algorithms performed worse on underrepresented minorities, women, and young adults than on Caucasians, men, and older people, respectively
- **Consequences**: If the suspect is an underrepresented minority, the system is more likely to erroneously fail to identify the right person, potentially causing innocent people to be bumped up the list—and possibly even investigated
- **Awareness**: e.g., police claim that their photo comparison algorithm is **not** biased towards minorities since it matches through distance and patterns only instead of through skin, age, or sex but in practice this may not be the case
- **No tests for bias**: There is no _independent_ testing regime for biased error rates, e.g., two major face recognition companies admitted that they did not run these tests

### Why Does this Happen (Facial Recognition)

Why do biases occur in facial recognition systems?

- Training sets are _hard_ to get
- If you are testing your accuracy on equally non-diverse image set, you will **not** get real-world accuracy measurements
  - To address – some companies make an effort to pay for extra images
  - Others, scrape the web to get the images that they need, which sometimes causes push-back

What are some ways bias is being addressed in industry:

- **InclusiveFaceNet**: improving face attribute detection with race and gender diversity
- Google researchers discuss a system for detecting _face attributes_ by learning the different attributes associated with different race and gender identities
- Example _face attributes_ for _race representation_ include: bangs, big lips, blurry, chubby, double chin, narrow eyes, pale skin, pointy nose, wearing necklace, and young

## Lesson 16 Predictive Algorithms Part 1

### What Are Predictive Algorithms

**Predictive algorithms** define and learn models to estimate likely outcomes based on historical data. Why predictive algorithms?

- Some outcomes may be _difficult_ to model except with examples (e.g., recognition of faces)
- The amount of knowledge needed to find correlations may be _too large_ for encoding by humans or by hand (e.g., in medical diagnostics)
- Some problems may adapt quickly over time and continuous redesign of the system by hand may be difficult (e.g., search engines)

Typical prediction tasks include:

- **Classification**: classify an instance into a category
- **Regression**: predict a numerical label for an unlabeled observation
- **Clustering**: discovering groups of similar instances

Classification is supervised learning, which classifies data (constructs a model) based on the training data and the values (class labels) indicating the class of the observations. New data is classified based on the training set.

Prediction models continuous-valued functions, i.e., predicts unknown or missing
values. Prediction is _similar_ to classification: construct a model and use model to predict unknown value. Prediction is _different_ from classification, prediction models continuous-valued functions versus predicting categorical class labels.

Classification Process - Evaluation
Counts of test records that are correctly or incorrectly predicted by the classification model.
Confusion Matrix:

<img width="1344" alt="image" src="https://github.com/user-attachments/assets/1f368073-c8a3-4650-bb29-e5183e41a390" />

Accuracy = # correct predictions/total predictions
Error Rate = # false predictions/total predictions

Precision = percentage of correct positive predictions = (PPV)TP/(TP+FP)
Recall/Sensitivity = Percentage of positively labeled instances, also predicted as positive = TP/(TP+FN)
Specificity = Percentage of negatively labeled instances, also predicted as negative = TN/(TN+FP)
Speed and Scalability = Time to construct the model or time to use the model
Interpretability = Understanding and insight provided by the model

Another issue that occurs in predictive algorithms is _generalization_:

- How do we ensure good generalization, i.e., avoid “over-fitting” on our particular data samples?
- We are ultimately interested in good performance on new (unseen) test data (i.e., the population).

### Predictive Algorithm Examples

This section includes real-world predictive algorithm examples (see lecture for more details).

### Learning Methods

As mentioned previously, predictive algorithms include:

- **Supervised learning**: labels are provided and there is a strong learning signal present between inputs and outputs (e.g., classification, regression)
- **Unsupervised learning**: there is no direct learning signal or obvious correlations between inputs and outputs. We’re simply trying to find some structure in the data (e.g., clustering, dimensionality reduction)

### Clustering

Clustering methods include the following tasks:

- Finding a picture in the database which is closest to the query image
- Checking feature labels
- Declaring the class of query image to be the same as that of the closest picture

In general, clustering can be accomplished by:

1. Finding a group structure in the data
2. Establishing the existence of classes given features
3. Mapping each data point to a discrete cluster index

### Regression

Some observations when doing regression:

- **Ockham’s razor**: prefer the simplest hypothesis consistent with data
- **Similarity/continuity bias**: similar inputs should have similar outputs

Two types of generalization errors:

1. **Overfitting**: models with too _many_ parameters may fit the training data well (_low bias_), but are sensitive to choice of training set (_high variance_)
2. **Underfitting**: models with too _few_ parameters may not fit the data well (_high bias_) but are consistent across different training sets (_low variance_)

### Decision Tree

**Decision trees** are simple, practical, and easy to interpret. Given a set of instances (with a set of features), a tree is constructed with internal nodes as the features and the leaves as the classes:

- Phase one: _tree construction_
  - At start, all the training examples are at the root
  - Examples are partitioned recursively based on selected attributes
- Phase two: _tree pruning_ is where branches are removed that are identified as noise or outliers
- _Testing_: the attribute values of a new data example are tested against the
  decision tree

## Python Predictive Algorithms (Supplemental Material)

This section includes supplemental material on Python predictive algorithms (see lecture for more details).

## Lesson 17 Predictive Algorithms Part 2

### Crime-based Predictive Algorithms In Use​

Crime-based predictive algorithms have many applications. One type of application is identifying potential crime hot spots based on where crime is _previously reported_, **not** where it is known to have _occurred_.

### COMPAS

**COMPAS (Correctional Offender Management Profiling for Alternative Sanctions)** is a 137-question questionnaire and predictive model for _risk of recidivism_. The model is a proprietary secret of Northpointe, Inc.

Supreme Court of Wisconsin ruled that judges are allowed to use COMPAS scores, but they:

- Must receive them accompanied by disclaimers and criticisms
- Can use them as a factor to give non-prison alternatives to prison
- Can use them as a factor to impose terms and conditions in parole

_Tradeoffs_ must be built into the prediction algorithm and are _policy decisions_.

### Judges’ Release Decisions Vs. Machine Predictions And Crime Risk​

Decisions to jail vs. releasing defendants:

- Kleinberg et al. (2017) compares the accuracy of human decisions and machine predictions in the criminal justice system
- Data: 750,000 individuals arrested in New York City between 2008-2013

Are predictive algorithms at least better than people?

Discrimination/suboptimal choice is **not** driven entirely by deep-rooted beliefs. Decisions can also vary greatly based on factors _unrelated_ to substantive features of the issue at hand.

Use of big data for predictive analytics raises serious ethical concerns, particularly in the context of _criminal justice_. How large should the gains be from machine prediction before its adopted? Tension between two views:

1. Should a person be treated _differently_ simply because they share attributes with others who have higher risks of crime?
2. Should police/judges/decision makers _discard_ information that could help make society fairer and potentially more just than it is now _on average_?

## Lesson 18 Predictive Algorithms Part 3

### Bias In Predictive Algorithms

Below are some scenarios and problems regarding bias in predictive algorithms:

- Imagine that you are an emergency room in a hospital that collects data on newly admitted patients (e.g., blood pressure, age, gender, etc.)
  - _Problem_: how to predict high-risk patients and discriminate them from low-risk patients
- Credit card company that collects thousands of applications every day for applicants applying for new credit cards
  - _Problem_: how to predict whether a credit application should be approved or not approved and the amount of credit to provide

In summary, predictive algorithms use _labeled data_ to make predictions, such data is rampant with _human biases_. Examples of human bias in labeled data include:

- Reporting bias
- Selection bias
- Stereotypical bias
- Historical biases

Additionally, there are also biases present in the _collection of data_.

# Module 3

This module covers lessons 19 through 22. Notes will be primarily from the main lecture content rather than external resources.

In the following lessons, we will learn how to examine an AI system design using various fairness parameters and AI toolboxes (E.g., Fairness 360 and What-If). Additionally, we will assess bias while taking into consideration the ethical and legal issues associated with bias. The goal is to be able to use these tools to transform a biased dataset into a more objective dataset.

## Lesson 19 Fairness And Bias

### Fairness And Bias

**Algorithmic fairness**: is a growing field of research that aims to mitigate the effects of unwarranted bias/discrimination on people propagated by AI/ML algorithms. The primary focus is on mathematical formalisms and algorithm approaches of fairness to help develop solutions.

Feedback loop of algorithmic bias includes:

- **Representational harm**: when an AI/ML system amplifies or reflects negative stereotypes about particular groups
- **Opportunity denial**: when an AI/ML system negative impacts individuals’ access to opportunities, resources, and overall quality of life
- **Disproportionate failure**: when the experience of interacting with an AI/ML system is disproportionately failing for particular groups

### Addressing Source Of Bias

In the past, there were very few views and mitigation strategies to address bias. Today, one view is that algorithmic biases are a result of _human biases_ (which may be caused by misinformation or bad data). As the saying goes: _garbage in, garbage out_. See the lecture slides for specific examples of bias problems in practice and how to go about addressing _sources of bias_.

### Addressing Fairness Measures

Much like addressing sources of bias, there were no previous strategies to do so. Currently, we examine _blindness and disparate impact_ as a metric to gauge fairness. See the lecture slides for specific examples of bias problems in practice and how to go about addressing _fairness measures_.

Some principles for quantifying fairness include:

- _Predictive algorithms_:
  - Predictions for people with similar non-protected attributes should be similar
  - Differences should be mostly explainable by non-protected attributes
- _Frameworks_
  - Fairness at the individual level: _consistency or individual fairness_
  - Fairness at the group level: _statistical parity_

Algorithms for bias mitigation include:

- **Pre-processing algorithms**:
  - Reweighing
  - Optimized pre-processing
  - Learning fair representations
  - Disparate impact remover
- **In-processing algorithms**:
  - Adversarial de-biasing
  - Prejudice remover
- **Post-processing algorithms**:
  - Equalized odds post-processing
  - Calibrated equalized odds post-processing
  - Reject option classification

For more information on each of these algorithms see [Machine Learning Models: Bias Mitigation Strategies](https://dzone.com/articles/machine-learning-models-bias-mitigation-strategies)

## Lesson 20 Fairness And Bias Assessment Tools

### AI Fairness 360

**AI Fairness 360** is an extensible toolkit for detecting, understanding, and mitigating unwanted algorithmic bias. It comprises of leading fairness metrics and algorithms from industry and academia. The 360 tool is designed to translate new research from the lab to industry practitioners (via _Scikit-learn's fit/predict paradigm_)

### What-If Tool

**What-If Tool** was created to address the following gap:

> What if you could inspect machine learning models, with minimal coding required?

It also tries to show how a model performs before and after bias is mitigated. See the class notes or lecture for more details on how this bias mitigation tool works.

## Lesson 21 AI/ML Techniques For Bias Mitigation

### Solutions To Mitigate Bias

In the past, very few if any solutions existed to address bias. Today, we can utilize _fair classifiers_ to mitigate biases in our AI and ML models. Note that it still is not 100% possible to mitigate bias and create fair algorithms.

Questions to keep in mind when evaluating fairness-aware algorithms:

- _Which algorithm is the best_?
  - On which dataset?
  - How was it pre-processed?
  - Under which measure?
  - With which training/test split?
  - What if there are multiple sensitive attributes?

One of the challenges of bias mitigation is that we **cannot** simply drop protected attributes since other features are correlated with them. Performance can depend on which _attribute_ you focus on and what _algorithm_ you choose.

### Fairness-aware Algorithms Trade-offs

Some trade-offs to consider when mitigating biases:

- Is the model doing _good_ things or _bad_ things to people?
  - If your model is sending people to jail, may be better to have more false positives than false negatives
  - If your model is handing out loans, may be better to have more False Negatives than False Positives
- Determining thresholds for accuracy vs. fairness must take into considerations _legal, ethical and trust_ guidelines (see lecture for more details and examples)

## Lesson 22 AI, Society, And Ethics Wrap-up

### It's Not Easy

Discovering, addressing, and mitigating bias is not easy. There are many ongoing events in society and in industry that prove that this is the case in practice (see lecture).

### Last Thoughts

Some takeaways include:

- Intended use of AI/ML can provide great value:
  - Increased productivity
  - Overcome human biases
- The stakes are high, with potential _long-term negative social impact_
  - Injustice
  - Significant public embarrassments
- AI/ML models may boost bias even further
  - Pros and cons of benchmark datasets
  - Facebook feed: elections/polarizations
  - Twitter bots: Brexit
- We do not know the ground truth that ML relies on:
  - What does _fairness_ or _unbiased_ really mean?
  - How to translate the definition of fairness to math and supervise our models?

Why should we care about AI, ethics, and society?

- Ethical responsibility
- Selfish reasons (since we are humans and we want AI algorithms to work for us)

At the end of the day, both are valid reasons for studying AI, ethics, and society.
