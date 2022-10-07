---
description: Probably Approximately Correct (PAC)
---

# The PAC Learning Framework

The PAC framwork helps define the class of learnable concepts in terms of the number of sample points needed to achieve an approximate solution, _sample complexity_,  and the time and space complexity of the learning algorithm, which depends on the cost of the computational representation of the concepts.

## The PAC learning model

* $\mathcal{X}$​: the set of all possible examples or instances (input space).
* $\mathcal{Y}$​: the set of all possible labels or target values.
* $concept~c: \mathcal{X} \rightarrow \mathcal{Y}$: a mapping from $\mathcal{X}$ to $\mathcal{Y}$.
* $concept~class~\mathcal{C}$​: a set of concepts we wish to learn.
* $\mathcal{D}$​: it is assumed that examples are independently and identically distributed ($i.i.d$) according to  some fixed but unknown distribution
* $hypothesis~set~\mathcal{H}$​: a fixed set of possible concepts which might not coincide with $\mathcal{C}$.
* $risk/risk~error/error~R(h)$: the generalization error of a hypothesis $h \in \mathcal{H}$


**The learning problem**: Given a sample $S = (x_1, \cdots, x_m)$​ drawn $i.i.d$​ according to $\mathcal{D}$ with labels $(c(x_1), \cdots, c(x_m))$ where $c \in \mathcal{C}$, the learner intends to select a hypothesis $h_S \in \mathcal{H}$​ that has a small $generalization~error$​ with respect to the concept $c$​.

**Definitions 2.1 Generalization error**: Given a hypothesis $h \in \mathcal{H}$​, a target concept $c \in \mathcal{C}$​, and a sample $S = (x_1, \cdots, x_m)$​ and an underlying distribution $\mathcal{D}$, the generalization error or risk of $h$​ is defined by

$$
R(h) = \mathbb{P}_{x\sim \mathcal{D}}[h(x) \neq c(x)] = \mathbb{E}_{x\sim \mathcal{D}}[1_{h(x) \neq c(x)}]
$$

where $1_\omega$ is the indicator function of the event $\omega$.

**Definitions 2.2 Empirical error** Given a hypothesis $h \in \mathcal{H}$, a target concept $c \in \mathcal{C}$, and a sample $S = (x_1, \cdots, x_m)$, the empirical error or empirical risk of $h$ is defined by

$$
\widehat{R}_S(h) = \frac{1}{m}\sum\limits_{i = 1}^m1_{h(x_i) \neq c(x_i)}
$$

While the generalization error is based on the distribution $\mathcal{D}$ and the concept $c$, which are unknown, the empirical error of $h \in \mathcal{H}$ is based on the sample $S$. Some guarantees can relate these two qunatities with high probability, under certain general assumptions.

Given a fixed $h \in \mathcal{H}$ and an $i.i.d$ sample $\mathcal{S}$, we have

$$
\mathbb{E}_{S \sim \mathcal{D}^m}[\widehat{R}_S(h)] = R(h)
$$

*Proof* : 

Given the fact that the sample $S$ is drawn $i.i.d$, we have
$$
\mathbb{E}_{S \sim \mathcal{D}_m}[\widehat{R}_S(h)] = \frac{1}{m}\sum\limits_{i = 1}^m\mathbb{E}_{S \sim \mathcal{D}^m}[1_{h(x_i) \neq c(x_i)}] = \frac{1}{m}\sum\limits_{i = 1}^m\mathbb{E}_{S\sim \mathcal{D}^m}[1_{h(x) \neq c(x)}]
$$

Therefore, we have

$$
\mathbb{E}_{S\sim\mathcal{D}^m}[\widehat{R}_S(h)] = \mathbb{E}_{S\sim\mathcal{D}^m}[1_{h(x)\neq c(x)}] = \mathbb{E}_{x\sim\mathcal{D}}[1_{h(x)\neq c(x)}] = R(h)
$$

* $O(n)$: the comnputaional cost of representing any $x \in \mathcal{X}$.
* $size(c)$: the maximal cost of the computational representation of $c \in \mathcal{C}$.
* $h_S$: the hypothesis returned by algorithm $\mathcal{A}$ given the sample $S$. (The dependency of $h_S$ on $\mathcal{A}$ is not fully indicated)

**Definition 2.3 PAC-learning** A concept class $\mathcal{C}$ is **PAC-learnable** if there exists an algorithm $\mathcal{A}$ and a polynomial function $poly(\cdot, \cdot, \cdot, \cdot)$ such that for any $\epsilon > 0$ and $\delta > 0$, for all distributions $\mathcal{D}$ on $\mathcal{X}$ and for any target concept $c \in \mathcal{C}$, the following holds for any sample size $m \ge poly(1/\epsilon, 1/delta, n, size(c))$：
$$
\mathbb{P}_{S\sim\mathcal{D}^m}[R(h_S) \le \epsilon] \ge 1 - \delta
$$
the $\mathcal{C}$ is further said to be **efficiently PAC-learnable** if $\mathcal{A}$ runs in $poly(1/\epsilon, 1/delta, n, size(c))$ where $\mathcal{A}$ is called a PAC-learning algorithm for $\mathcal{C}$.



## Guarantees for finite hypothesis sets -- consistent case


## Guarantees for finite hypothesis sets -- inconsistent case

## Generalities

### Deterministic versus stochastic scenarios

### Bayes error and noise

## Chapter notes

