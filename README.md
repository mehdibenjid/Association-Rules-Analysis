# association-rules-analysis
 Association rule mining and outlier detection techniques 
# Association Rules Analysis

**Association Rules Analysis** is a data mining technique used to discover interesting relationships, patterns, or correlations between items in large datasets. This method is commonly applied in **market basket analysis** to find sets of products that frequently co-occur in transactions, but it has applications in many other areas as well.

---

## Key Concepts in Association Rules Analysis

### 1. **Itemset**
An **itemset** is a collection of one or more items. In market basket analysis, an itemset refers to products purchased together in a single transaction.

### 2. **Association Rule**
An **association rule** is an implication of the form:
$$
X \Rightarrow Y
$$
where:
- $X$ (antecedent) is an itemset (one or more items),
- $Y$ (consequent) is another itemset.

The rule suggests that if $X$ is present in a transaction, then $Y$ is likely to be present as well.

For example:
$$
\text{If (bread, butter)} \Rightarrow \text{(milk)}
$$
This means that if a customer buys bread and butter, they are also likely to buy milk.

---

## Key Metrics for Evaluating Association Rules

Association rules are evaluated based on three important metrics: **Support**, **Confidence**, and **Lift**.

### 1. **Support**
The **support** of an itemset $X$ is the proportion of transactions in the dataset that contain the itemset $X$. It measures the frequency of occurrence of $X$.

\[
\text{Support}(X) = \frac{\text{Number of transactions containing } X}{\text{Total number of transactions}}
\]

For the rule $X \Rightarrow Y$, the support is the probability that both $X$ and $Y$ appear together in a transaction:
\[
\text{Support}(X \Rightarrow Y) = \frac{\text{Number of transactions containing both } X \text{ and } Y}{\text{Total number of transactions}}
\]

### 2. **Confidence**
The **confidence** of the rule $X \Rightarrow Y$ is the conditional probability that $Y$ appears in a transaction given that $X$ is already present. It is calculated as:
\[
\text{Confidence}(X \Rightarrow Y) = \frac{\text{Support}(X \cup Y)}{\text{Support}(X)}
\]
This measures the likelihood that $Y$ will occur given that $X$ has occurred.

### 3. **Lift**
The **lift** of a rule is the ratio of the observed support of $X \Rightarrow Y$ to the expected support if $X$ and $Y$ were independent. It is calculated as:
\[
\text{Lift}(X \Rightarrow Y) = \frac{\text{Support}(X \Rightarrow Y)}{\text{Support}(X) \times \text{Support}(Y)}
\]
- If $\text{Lift} > 1$, this suggests a positive correlation between $X$ and $Y$ (i.e., they are more likely to occur together than by random chance).
- If $\text{Lift} = 1$, $X$ and $Y$ are independent.
- If $\text{Lift} < 1$, this indicates a negative correlation.

---

## Example of Association Rule

Consider the following example with a dataset of 100 transactions, where:
- 40 transactions contain "bread"
- 30 transactions contain "butter"
- 20 transactions contain both "bread" and "butter"

For the rule:
$$
\text{If (bread)} \Rightarrow \text{(butter)}
$$

### Support:
\[
\text{Support}(\text{bread} \Rightarrow \text{butter}) = \frac{20}{100} = 0.20
\]
This means that 20% of all transactions contain both bread and butter.

### Confidence:
\[
\text{Confidence}(\text{bread} \Rightarrow \text{butter}) = \frac{20}{40} = 0.50
\]
This means that in 50% of the transactions where bread is purchased, butter is also purchased.

### Lift:
\[
\text{Lift}(\text{bread} \Rightarrow \text{butter}) = \frac{0.20}{(0.40 \times 0.30)} = 1.67
\]
This indicates that bread and butter are 1.67 times more likely to be purchased together than if they were independent.

---

## Applications of Association Rules

- **Market Basket Analysis**: Discover product combinations that frequently appear together in transactions.
- **Recommendation Systems**: Suggest items that a customer might want to purchase based on previous buying patterns.
- **Fraud Detection**: Identify unusual patterns in transactional data.
- **Healthcare**: Detect co-occurring symptoms, treatments, or diagnoses in patient data.

---

### Summary

- **Support**: Measures how frequently items appear in the dataset.
- **Confidence**: Measures how often the rule has been found to be true.
- **Lift**: Measures how much more likely the rule is compared to random chance.

Association Rules Analysis is a powerful tool for uncovering hidden patterns and making actionable decisions based on the relationships between items in large datasets.
