
+ [Paper Link](https://link.springer.com/chapter/10.1007/978-3-642-82453-1_15).
+ **Motivation:** Classical Logic is inherently Monotonic, this can be attributed to the only inference rule that it possesses---Modus Ponens. In other information based inference situations, for example in Knowledge bases (KB), we can expect additional inference-rules: $$A \text{ is a literal \& not a head}\Rightarrow \neg A $$ In such cases, monotonicity principle is easily violated and hence we need to proceed *cautiously*. 
+ **Scope:** The paper justifies *non-monotonic* inference systems. To that extent, it provides the inference rule and presents certain derivation not possible within the classical framework. Building upon this idea, the author proposes certain *properties* every *causal expert system*, for instance KB, must satisfy: 
	+ Classical derivations hold.
	+ Non-classical derivations are consistent.
	+ conjunction rule: $$A\vdash X\;\&\; A\vdash Y\hspace{1 em} \Rightarrow\hspace{1em} A\vdash X\land Y$$
+ **Scope (Contd.):** Based to the above rules, a *weak deduction* system is proposed. Furthermore, it is proven that weak deduction is the only system having the following properties:
	+ $A\vdash X$ whenever $A\in X$.
	+ $A\vdash X\land Y$ iff $A\vdash X$ and $A\vdash Y$
	+ $A\vdash X$ and $A\vdash Y$ implies $A\cup \{X\}\vdash Y$
	+ $A$ is consistent and $A\vdash X$, then $A\cup \{X\}$ is consistent.
+ **Conclusion:** Using the above characterization a definition is proposed for non-monotonic logic for casual expert systems: Any relation $\vdash$ that satisfies, 
	+ Reflexivity: $A\vdash x$ whenever $x\in A$.
	+ Cut: If $A\vdash x$ and $A\cup\{x\}\vdash y$, then $A\vdash y$.
	+ Cautious Monotonicity: If $A\vdash y$ and $A\vdash x$, then $A\cup \{x\}\vdash y$.