
* Following the steps mentioned in [[Upsilon Values]], we do the following:
	* Rewrite the Banzhaf index in terms of sequences: $$B_i(\mu)=\frac{1}{2^{|N|-1}}\sum_{{\cal C\in M}(N)}\frac{\mu(\mathcal{C}_{x_i}\cup\{x_i\})-\mu(\mathcal{C}_{x_i})}{{|N|-1\choose |\mathcal{C}_{x_i}|}}$$ where ${\cal C}_{x_i}$ is the largest possible subset in the chain $\cal C$ without the element $x_i$. 
	* Exchange the occurrences of $C_{x_i}$ by $C_i$ to obtain: $$B_i(\mu)=\frac{1}{2^{|N|-1}}\sum_{{\cal C\in M}(N)}\frac{\mu(\mathcal{C}_{i})-\mu(\mathcal{C}_{i-1})}{{|N|-1\choose |i-1|}}$$