
+ Introduced as a replacement for Shapley, in the case of Voting Games. 
+ Formally, it can be defined as follows: 
	+ Suppose $(N,\mu)$ is a voting games, as discussed in [[Banzhaf Index]]. 
	+ Let ${\cal M}(N)$ denote the set of all chains over $N$, as in [[Upsilon Values]].
	+ Shapley-Shubik power index is then defined as: $${\tt SS}_i(\mu)=\frac{1}{n!}\sum_{C\in {\cal M}(N)}\mu(C_i\cup \{i\})-\mu(C_i). $$ where $C_i$ denotes the largest subset in the chain that doesn't contain $i$. 
+ It can be formally characterized by:
	+ Efficiency: $\sum_{i\in N}{\tt SS}_i(\mu)=\mu(N)=1$.
	+ Symmetry: if two players have the same swinging power, then they have the have the same Shapley index.
	+ Additivity: if $\mu,\nu$ are two games, then ${\tt SS}_i(\mu+\nu)={\tt SS}_i(\mu)+{\tt SS}_i (\nu)$ for every player $i\in N$.
	+ Dummy: If a player cannot swing any coalition then the payoff of the player is zero.
+ Cardinality based Shapley-Shubik is just $\Upsilon$-values for max. of unanimity measures. In other words, it checks whether a coalition $T$  contain nay of the coalitions $\{S_1,\dots ,S_n\}$. 