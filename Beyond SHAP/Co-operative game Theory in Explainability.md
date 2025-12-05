
## Overview of the idea

* The idea is to answer the problem(s) of *Explainability* using the concepts in [co-operative game theory](https://en.wikipedia.org/wiki/Cooperative_game_theory).
* Specifically, we start with
	* A set of features $\mathcal{F}=\{x_1,\dots,x_{n}\}$, and sets $\mathbb{D}_{i}$ corresponding to each feature $x_i$. These sets are understood to be *all* possible values a feature can take on. 
	* A set $\mathbb{F}=\mathbb{D}_{1}\times \dots\times\mathbb{D}_{n}$, dubbed as the data-set. 
	* A classification set $\cal K$, along with a classifier $\kappa:\mathbb{F}\rightarrow\cal K$.
	Together, there is a *trained* ML algorithm $\mathcal {M}=(\mathcal{F},\mathbb{F}, \mathcal{K}, \kappa)$, which accepts a datapoint $\mathbf{v}\in \mathbb{F}$ and returns $\kappa(\mathbf{v})$.
* Problem(s) of *explainability*, or explainability (of an instance), are questions about the input-output instances of $\cal M$. The answers are (generally) provided as subsets of the features, namely $\cal F.$ 
* For instance, given a data-point $\mathbf{v}\in \mathbb{F}$, the question "Why on input $\mathbf{v}$, the algorithm $\cal M$ outputs $\kappa(\mathbf{v})$?" falls under the problem of explainability. 
* If the feature set $\cal F$ is interpreted as a set of "players", and there is an assignment of "value",  $$v:\mathcal{P}(\mathbb{F})\rightarrow \mathbb{R}$$to every coalition of players, we have a co-operative game $(\mathcal {F}, v)$. 
* To use co-op game theory in explainability, we make the implicit assumption: "The best explanation, of any instance, is the set of *all* features". 
  This is an adaptation of the central principle in co-op game theory: "The grand coalition will form". 
* The fundamental challenge in co-op game theory is to assign some *payoff* to each player, after the grand coalition forms. To this end, various [power-indices](https://www.jstor.org/stable/41798016) have been proposed.
* Ideally, we want to harness these power-indices to grasp the extent to which individual features influence the input-output behavior. 
* Such attempts have been criticized, as in [[Explainability is NOT a Game]]. It has been proposed that for certain cases, the use of Shapley values lead to breakdown of explainability.
* This negative viewpoint on co-op game theory methods have been scrutinized as well, as in **insert references**. 

## Our standpoint

* Though we agree with the authors in [[Explainability is NOT a Game]], to the extent that sufficiency should be better represented in the explanations, we still retain our faith in power indices. 
* We propose the extensive study of well-known and certain marginal power indices. In particular, we apply them to the example provided in [[Explainability is NOT a Game]], and some others to check their applicability to various use-cases. 
* We check for different Power Indices and notice that:
	* All the indices are *player* based, i.e. it distributes the final payoff based on one-individual's initial contribution function.
	* There are approaches that extend Shapley to *set* based (see [[Set-Shapley values]]) and *cardinality* based approaches, (see [[Upsilon Values]]).
* Our motivation is to do the above for the well-known power indices, namely [[Banzhaf Index]], [[Shapley-Shubik]], [[Owen values]] and [[Public Good index]]. 