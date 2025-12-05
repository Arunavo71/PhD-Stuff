+ In certain settings, the atoms might form independent coalitions to play the co-operative game $(N,\mu)$ .
+ Such coalitions are understood to be *partitions* of $N$, i.e. a set $P=\{N_1,\dots,N_n\}$ s.t. $\bigcup_{1\leq i\leq n}N_i=N$.  
+ In such settings, the final-payoff of an atom $i$ is determined by the value it brings to each coalition within the partition $P$. 
+ This can be understood as a *game within a game*.
## Game within a Game.

+ For calculating the Owen value of $i\in N_j$, first we consider the subsets of $N_j\setminus\{i\}$ and ask the question "How much value does $i$ bring to $N_j$?"
+ This is answered in the Shapley-esque style $$O_i(\mu)=\sum_{S\subseteq N_j\setminus \{i\}}\frac{|S|!\cdot(|N_j|-|S|-1)!}{|N_j|!}\Bigl[w_j(S\cup \{i\})-w_j(S)\Bigr],$$ where $w_j(S\cup{\{i}\})$ is the Shapley value of player $N_j$, when $N_j$ gets replaced by $S\cup \{i\}$. Similar is the definition of $w_j(S)$.
+ Spelling it out, we get $$w_j(S\cup \{i\})=\sum_{T\subseteq P\setminus \{j\}}\frac{|T|!\cdot(|P|-|T|-1)!}{|P|!}\Bigl[\mu(\bigcup T\cup S\cup \{i\})-\mu(\bigcup T)\Bigr],$$ and $$w_j(S)=\sum_{T\subseteq P\setminus \{N_j\}}\frac{|T|!\cdot(|P|-|T|-1)!}{|P|!}\Bigl[\mu(\bigcup T\cup S)-\mu(\bigcup T)\Bigr].$$
+ Putting them together, we arrive at: $$O_i(\mu)=\sum_{T\subseteq P\setminus \{N_k\}}\sum_{S\subseteq N_k\setminus\{i\}} \frac{|T|!(n-|T|-1)!}{n!}\frac{|S|!(|N_j|-|S|-1)!}{|N_j|!}\mu(Q\cup S\cup\{i\})-\mu(Q\cup S).$$
## Axiomatic Characterization

+ Owen values can be axiomatically characterized via 4 properties.
+ Fix an arbitrary game $(N, \mu)$, and players $P$ (formally, $P$ is a partition of $N$). 
	+ Efficiency: $\sum_{i\in N}f_i(\mu)=\mu(N)$.
	+ Dummy player: An atom $i$ is dummy iff $\mu (S\cup \{i\})=\mu (S)+\mu (\{i\})$ for each $S\subseteq N\setminus \{i\}$. If $f_i(\mu)=\mu(i)$ for all dummy atoms, then $f$ satisfies dummy property.
	+ Symmetry within atoms: Atoms $i,j$ are symmetrical iff $\mu(S\cup \{i\})=\mu(S\cup\{j\})$ for every $S\subseteq N\setminus \{i,j\}$. If $f_i(\mu)=f_j(\mu)$ for every symmetric pair of atoms $i\&j$, then $f$ satisfies symmetry within atoms property.
	+ Symmetry within coalitions: Players $i,j$ are symmetrical iff $\mu(\bigcup S\cup \{i\})=\mu(\bigcup S\cup\{j\})$ for every $S\subseteq P\setminus \{i,j\}$. If $f_i(\mu)=f_j(\mu)$ then $f$ satisfies symmetry within coalitions property.