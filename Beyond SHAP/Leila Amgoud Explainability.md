
## Overview of the paper

+ The paper focuses on explanability of classifier models. As suggested by the author, the literature can be categorized into three parts:
	+ The first kind makes a distinction between *local* and *global explanations*: focusing on explanations of a single instance (local) vs explanations of classes independently of the instances (global), respectively.   
	+ The second kind consider the whole feature set, or certain subsets of it, while providing explanations.
	+ The third kind distinguishes between the methods that look inside the models vs the ones that consider the process a black-box.
+ The author classifies the work aligned with the second case, as given above. However, this present work bridges the gap between individual explanations of instances, and explanations of classifications.
+ Furthermore, it expresses the cases when the entire set of data is unavailable, or it is unreasonable to account for it.

## Abstract (and Formal) treatment of classifiers 

+ The formal part is in line with [[Co-operative game theory in Explanations]], where the authors talks about a theory $\mathtt{T}=\langle \cal F,\mathtt{dom}, C\rangle$. 
	+ $\cal F$ is the set of features, denoted by $\{f_1,\dots f_n\}$
	+ $\mathtt{dom}$ is the a function on $\cal F$.
	+ $\cal C$ is a set of classifiers, $\{c_1,\dots,c_m\}$.
+ Every theory $\mathtt{T}$ gives rise to a set of *instances* :
	+ Any f feature-datapoint pair $\langle f,v\rangle$ is called a literal. The set of all literals is referred to as $\mathtt{Lit}$.
	+ Any set $S\subseteq \mathtt{Lit}$, s.t. $\langle f,v\rangle$ and $\langle f,v'\rangle\in S$ implies $v=v'$, is called consistent.
	+ Any consistent set $S$ of literals, s.t. each $f\in \cal F$ occurs as a pair $\langle f,v\rangle$ in $S$, is called an instance. 
	+ The set of all instances is referred to as $\mathtt{Inst}$.
+ Instances are classified according to a classifier $\mathtt{F}: \mathtt{Inst}\rightarrow \cal C$, which assigns a classification to each instance. 
+ Moving forward, we talk about an arbitrary but fixed theory $\mathtt{T}$, and a classifier $\mathtt{F}$ over it.

## Explanation Functions

+ Explains in this paper is understood to a subset of $\mathtt{Lit}$.
+ Two classes of explanation functions are discussed:
	+ Class explanation (function): In this case, we consider a function $\tt L$ with $\cal C$ as its domain, and returns a set of explanations as its output for each input $c\in \cal C$
	+ Instance explanation (function): In this case, we consider a function $\tt G$ with instance-classification pairs $\langle x, {\tt F}(x)\rangle$ as its domain, and returns a set of explanations as its output for each ${x\in \tt Inst}\times \text{ran}({\tt F})$.
	+ This distinction is solely on the domain of the explanation: either classes $\cal C$, or instance-class pairs ${\tt Inst}\times \text{ran}({\tt F})$. 
+ The interaction between Instance and Class explanations (functions) are *compatible* iff ${\tt G}(c)=\bigcup_{\{\langle x,{\tt F}(x)\rangle:{\tt F}(x)=c\}} {\tt F}(x,c)$.
+ Any class explanation $\tt G$ that can explain each class $c\in \cal C$, i.e. ${\tt G}(c)=\varnothing$, for every $c\in \cal C$, is said to be *successful*. 
+ This part only talks about the distinction, without producing explicit examples.
## Explanations based on complete information

+ In this section, the author assumes the entire $\tt Inst$ set is available for explanation.
+ based on this assumption, two kinds of explanations are proposed: Global and Local.
### Global Explanations

+ Global explanations are simply class explanations as defined above.
+ In this part, the author provides examples for class explanations using argument pros and cons. 
+ An argument support $c\in \cal C$, also called argument pro, is a pair $\langle H,c\rangle$, where 
	+ $H\subseteq \tt Lit$ is consistent.
	+ For any $x\in \tt Inst$, if $H\subseteq x$, ${\tt F}(x)=c$.
	+ $H$ is the smallest $\subseteq$-set that satisfies the above condition.
+ Let $Pros(c)$ denote the set of all argument pros for $c$, and $$\text{arg}^+({\tt T})=\bigcup_{c\in \cal C}Pros (c)$$
+ We can define a class explainer based on argument pros: $${\tt G}_{pro}(c)=\{H:\langle H,c\rangle \text{ is an argument pro for }c\}.$$ which is an example absent from above.
+ If $\tt F$ is surjective, then ${\tt G}_{pro}$ satisfies success; furthermore, ${\tt G}_{pro}$ satisfies coherence.
+ Similar to Argument pro, one can define Argument con: For any $c\in \cal C$, the pair $\langle H,c\rangle$ satisfies argument con iff: 
	+ $H\subseteq \tt Lit$ is consistent.
	+ For any $x\in \tt Inst$, if $H\subseteq x$, ${\tt F}(x)\not=c$.
	+ $H$ is the smallest $\subseteq$-set that satisfies the above condition.
+ Define $Cons(c)$ to be the set of all argument cons w.r.t. $c$, and $$\text{arg}^-({\tt T})=\bigcup_{c\in \cal C}Cons(c)$$
+ Again, a class explainer can be defined: $${\tt G}_{con}(c)=\{H:\langle H,c\rangle \text{ is an argument con for }c\}.$$
+  If $\tt F$ is surjective, then ${\tt G}_{con}$ satisfies success; however, ${\tt G}_{con}$ is not necessarily coherent.
### Local Explanations

+ Local explanations are understood to be instance explanations.
+ Aligned with the previous literature, the author proposes three kinds of local explanations: Abductive, Contrastive and Counter-factual.
+ Abductive explanations for an instance-class pair $\langle x,c\rangle \in \tt Inst\times \cal C$ are the set of argument pros for $c$ that are contained in $x$. $${\tt L}_{ae}(x,c)=\{H:H\in Pros(c)\;\&\; H\subseteq x\}.$$
+ ${\tt L}_{ae}$ satisfies coherence and success. Furthermore, ${\tt L}_{ae}$ and ${\tt G}_{pro}$ are compatible.
+ Counter-factual explanations are defined in the same way: $${\tt L}_{cf}=\{H\setminus x: \langle H,c\rangle\in Cons(c)\}$$
+ ${\tt L}_{cf}$ satisfies success if $\tt F$ is surjective; however, ${\tt L}_{cf}$ violates coherence.
+ Contrastive explanations for $x\in \tt Inst$ with ${\tt F}(x)\not=c$ consist of consistent set $H\subseteq\tt Lit$ s.t. 
	+ $\exists y\in \tt Inst$ s.t. ${\tt F }(y)=c$ and $y= x_{\downarrow H}$.
	+ $H$ is the $\subseteq-$minimal set satisfying the property above. 
+ In binary classification theories, contrastive and counterfactual explanations coincide. 

### Explanations with incomplete information

+ This section is based on the assumption that we have $\cal Y\subseteq \tt Inst$ available for explanations. 
+ Under these assumptions, explanations are *arguments*. 
+ An argument for $c$ is a pair  $\langle H,c\rangle$ s.t. $H\subseteq \tt Lit$ is consistent and:
	+ there exists $x\in \cal Y$ s.t. $H\subseteq x$.
	+ $\forall y\in \cal Y$ with $H\subseteq y$, we have ${\tt F}(y)=c$.
	+ $H$ is $\subseteq-$minimal that satisfies the above two conditions.
	+ We call the set of all argument pairs $\arg(\cal Y)$
+ For example a *plausible explainer* for $\langle x,{\tt F}(x)\rangle$ is a restriction of abductive explanations. $${\tt L}_{pe}=\{H: \langle H,c\rangle\in \text{arg}({\cal Y})\;\&\; H\subseteq x\}.$$
+ An argumentation based explanation is also possible. 
### Argumentation based Explanations

+ The idea is philosophically well-motivated: when we have incomplete information, we any "explanation" is an argument for why we believe some instance will have the classification $c$. 
+ It can be said there are two stable (meta-)arguments: "We believe this given the information....." and "We do not know what can happen since we lack complete information.....". 
+ The following framework falls under the first umbrella, extending what we can believe given the information. 
+ We say $\langle H,c\rangle$ attacks $\langle H',c'\rangle$ iff $H\cup H'$ is consistent but $c\not=c'$.
+ An argumentation based framework would have the pair $\langle \arg({\cal Y}),\cal R\rangle$ where $a,b\in \cal R$ iff $a$ attacks b in the above sense.
+ In this setting, the following can be an explanation:$${\tt L}^{*}=\{H: H\subseteq {\tt Lit}: \langle H, {\tt F}(x)\rangle\text{ is present in all stable extensions of }\langle \arg({\cal Y}),\cal R\rangle \}.$$
+ Notice that the attack relation in the above framework is bi-directional. it can be fixed with weighted argumentation.
+ Suppose there is a set function ${\cal V: P}({\cal F})\rightarrow [0,1]$ called *capacity*, then we can define strength of $\langle H,c\rangle$ as ${\sf St}(H,c)={\cal V}\{f_i: \langle f_i,v_i\rangle \in H\}$
+ We can have the following modification to the attack relation: 
	+ $a{\cal R}b$ iff $a$ attacks $b$, and
	+ ${\sf St}(a)\geq {\sf St}(b)$.
+ We can define $\tt wL^*$ analogously. 