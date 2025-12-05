
## Overview of the paper

* The authors propose a binary example of an explanation problem as described in [[Co-operative game Theory in Explainability]].
      * The authors use a feature set of 4 features $\{x_1,x_{2},x_{3},x_{4}\}$,  each of which can take on binary values. Consequently, the data-set is $\mathbb{F}=\{0,1\}^4$. The classifier is also binary, i.e. $\kappa(\mathbf{v})\in \{0,1\}$ for each data-point $\mathbf{v}$. 
	  * The classifier chart returns 0 for every case other than $(0,0,0,1),(0,0,1,0),(0,1,0,0)$.
	The task of explanation is to explanation the instance of $(0,0,0,0),\kappa(0,0,0,0)=0$
* To this end, they choose two questions: 
	* **Abductive Explanation:** Why on input $(0,0,0,0)$, the algorithm $\cal M$ outputs $0$?
	* **Contrastive Explanation:** Why on input $(0,0,0,0)$, the algorithm $\cal M$ doesn't output $1$?
* A set of logical rules are laid out that the answers, which in the these cases are subsets, should follow. It is additionally proven that abductive and contrastive explanations coincide.
* To express their viewpoint, the authors use a non super-additive assignment function:  $$\phi (S;\mathcal{M},\mathbf{v})=\frac{1}{2^{|\mathcal{F}\setminus S|}}\sum_{\mathbf{x}\in \Upsilon(S,\mathbf{v})}\kappa(\mathbf{x})$$where $\Upsilon$ is the similarity set: $\Upsilon(S,\mathbf{v})=\{\mathbf{x}\in \mathbb{F}: \wedge_{i\in S}\mathbf{x}_i =\mathbf{v}_i\}$. For this case, $\mathbf{v}=(0,0,0,0)$.
* Adopting Shapley value for the final payout produces $x_1$ as the most "influential" feature. Hence, $x_1$ should be included in the explanations. However, none of the explanations do so.
* The authors dub the feature $x_1$ as irrelevant, and propose a irrelevancy predicate $\mathsf{irrelevant}(i)$. A list of logical sentences, based on the irrelevancy predicate, are shown to be violated.  
* Through this path of reasoning, the authors conclude their viewpoint.

## Our proposal

* The idea of Abductive and Contrastive explanations are indeed novel, however just restricting ourselves to Shapley values leads to an one-dimensional analysis.
* perhaps we can reached a more nuanced viewpoint through other power indices. To this end, we can use:
	* [[Shapley-Shubik]]:
	* [[Upsilon Values]]:
	* [[Banzhaf Index]]:
	* [[Public Good index]]: 
	* [[Owen values]]: