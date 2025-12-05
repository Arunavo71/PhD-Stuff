
## Individual Banzhaf Index

* Banzhaf Index was introduced in the context of <u>Voting Games</u>:
	* A game $(N,\mu)$ is classified as voting iff $ran(\mu)=\{0,1\}$. A coalition $S\subseteq N$ is winning iff $\mu(S)=1$, and losing otherwise.
	* A player $i$ for a coalition $S$ is *swing* iff $\mu(S)=1=1-\mu(S\setminus \{i\})$. 
	* If $\eta_i(\mu)$ denote the number of swings for $i$, then a *dummy* player $i$ would have $\eta_i(\mu)=0$.
	* Similarly, if $\bar{\eta}(\mu)$ denotes the total number of swings for then a *dictator* player $i$ has $\bar{\eta}(\mu)=\eta_i(\mu)$.
* Given a voting game $(N, \mu)$, the Banzhaf index is calculated as: $$B_i(\mu)=\frac{\eta_i(\mu)}{2^{|N|-1}}=\frac{1}{2^{|N|-1}}\sum_{S\subseteq N\setminus\{i\}} (v(S\cup\{i\})-v(S))$$
* In other words, the index counts the number of swings $\eta_i(\mu)$, corresponding to player $i$, and normalizes by $\frac{1}{2^{|N|-1}}$.
* Alternatively, Banzhaf index can be axiomatically characterizes by:
	* <u>Dummy players get no pay-off </u>: $B_i(\mu)=0$ for each dummy player $i$.
	* <u>Efficiency in swings</u>: $\sum_iB_i=\bar\eta(\mu).$
	* <u>Weak anonymity</u>: $B_i(\mu^\pi)=(B_i(\mu))^\pi$.
	* <u>Sum of games</u>: $B(\mu\lor \nu)+B(\nu\land \mu)=B(\mu)+B(\nu)$, where $$\mu \lor \nu(S)=max\{\mu(S),\nu(S)\}$$where $S\subseteq N$; the game $\mu\land \nu$ follows by changing max to min.
## Set Banzhaf

+ Pretty much self explanatory.