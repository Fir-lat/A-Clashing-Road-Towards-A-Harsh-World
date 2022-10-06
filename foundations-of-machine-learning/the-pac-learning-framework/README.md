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
* $risk/risk~error/error~R(h)$: the generalization error of a hypothesis $h \in \mathcal{H}$​

**The learning problem**: Given a sample $S = (x_1, \cdots, x_m)$​ drawn $i.i.d$​ according to $\mathcal{D}$ with labels $(c(x_1), \cdots, c(x_m))$ where $c \in \mathcal{C}$, the learner intends to select a hypothesis $h_S \in \mathcal{H}$​ that has a small $generalization~error$​ with respect to the concept $c$​.

**Definitions 2.1 Generalization error**: Given a hypothesis $h \in \mathcal{H}$​, a target concept $c \in \mathcal{C}$​, and a sample $S = (x_1, \cdots, x_m)$​ and an underlying distribution $\mathcal{D}$, the generalization error or risk of $h$​ is defined by

$$
R(h) = \mathbb{P}_{x\sim \mathcal{D}}[h(x) \neq c(x)] = \mathbb{E}_{x\sim \mathcal{D}}[1_{h(x) \neq c(x_i)}]
$$

## Guarantees for finite hypothesis sets -- consistent case

## Guarantees for finite hypothesis sets -- inconsistent case

## Generalities

### Deterministic versus stochastic scenarios

### Bayes error and noise

## Chapter notes

