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
