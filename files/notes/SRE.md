# Symmetry-Resolved Entanglement

Hope I can make a few concepts clear.

## Coarse-graining and entropy
For a macrostate with lots of microstates, entropy is defined to be
$$
S = -\sum_{i}p_i\log p_i,
$$
with $p_i$ being probability of being in the $i$-th microstate.

However, if the "microstate" is not truly the final description, it will be a *macrostate* from the POV of finer structure, with also lots of "more-micro-states". This description is natural, because we can do coarse-graining more than once. We can divide all the microstates in a macrostate into various sets according to, say, some charge. But having the same charge doesn't mean two states are the same. They can still be different due to some other quantum number. Therefore, there can still be many states in a charge subset.

Now, knowing that there is more uncertainty, how would entropy be changed? Every "used-to-be-micro-state" will now have entropy $S_i$, together with probability of being in that state, they contribute "additional" entropy $\sum_i p_i S_i$. Then the entropy related to the current understanding of the micro-structure should be 
$$
S = -\sum_{i}p_i\log p_i + \sum_i p_i S_i. \tag{*}
$$

This can be proved. Assume that $N_i$ more-micro-states are in the $i$-th microstate with probability $p_{i,a} = p_i\cdot p_{a|i}$, where $p_{a|i}$ is the conditional probability of finding more-micro-state $a$ in the $i$-th microstate, 

$$
S = -\sum_{i,a}p_{i,a}\log p_{i,a} = -\sum_{i}p_i\log p_i + \sum_i p_i S_i.
$$

in which we will focus on $S_i$, the entropy of a microstate with finer structure:
$$
S_i = -\sum_{a=1}^{N_i} p_{a|i} \log p_{a|i}.
$$

Notice that the real entropy consists of two parts. Because there is uncertainty due to different subsets (or sectors), as well as uncertainty due to different states within a sector.

Furthermore, in *quantum* cases on which we'll focus in this note, Eq. (*) is also valid! Then $S_i$ and $S$ can be entanglement entropy while $-\sum_{i}p_i\log p_i$ is still Shannon entropy of classical probability.


## Symmetry-Resolved Entanglement Entropy
Consider a bipartite system and its charge operators, $Q_A$, $Q_B$, and $Q = Q_A+Q_B$, or more formally, $Q = Q_A \otimes I_B + I_A \otimes Q_B$. A generic state would be
$$
\Ket{\psi} = \sum_{i,\alpha}c_{i,\alpha} \Ket{i_A,\alpha_B},
$$
where $i$ and $\alpha$ are labels of charge. For eigenstate of $Q$, i.e. state with total charge $q$, the sum would not really be a double sum because of constraint $i+\alpha=q$. Here's entanglement! The state of total system is pure state, but the total charge $q_A+q_B$ must be the known number $q$. Then if we find subsystem $A$ has charge $q_i$, then we immediately know subsystem $B$ has charge $q-q_i$. That's because of entanglement. That is entanglement.

Furthermore, we can prove that $\rho_A$ is block-diagonal in bases of $Q_A$.

What does that mean? $\rho_A\Ket{i}$ would not in another eigenspace of $Q_A$ (charge sector). Won't go into details of the proof. But here's an explanation. (UNDER CONSTRUCTION)

It's only block-diagonal but not necessarily diagonal because there are other quantum number labels which are not written explicitly.

Now block-diagonal $\rho_A$ can be decomposed into a sum
$$
\rho_A = \oplus_q \rho_A(q).
$$

Probability of finding eigenvalue $q$ is
$$
P(q) = \mathrm{tr}_q[\rho_A(q)].
$$
To get intuition of this, we can write $\rho_A$ in a diagonal form, where diagonal elements truly represent probabilities. Then this trace is a partial sum of those probabilities.

Furthermore, $\rho_A^n$ would also be block-diagonal.
$$
\rho_A^n = \oplus_q \rho^n_A(q)
$$
Similarly, can define 
$$
P_n(q) = \frac{\mathrm{tr}[\rho^n_A(q)]}{\mathrm{tr}[\rho^n_A]}
$$
(Shouldn't call this probability, even though they add up to one.)

To simplify future formulas, we can use normalized sector density matrix
$$
\tilde{\rho}(q) := \frac{\rho(q)}{P(q)},
$$
whose trace is 1.

Sometimes I will omit the subscript $A$ for simplicity. Hope it doesn't cause confusion because discussion from now on doesn't really depend on the whole system.

Then symmetry-resolved entanglement entropy can be defined as
$$
S(q) := - \mathrm{tr}\left[ \tilde{\rho}(q) \log \tilde{\rho}(q) \right].
$$
Also symmetry-resolved Renyi entropy
$$
S_n(q) := \frac{1}{1-n}\log \mathrm{tr}\left[ \tilde{\rho}^n(q) \right] = \frac{1}{1-n} \log\left(\frac{Z_n(q)}{Z_1^n(q)}\right),
$$
where we denote
$$
Z_n(q) = \mathrm{tr}_q[\rho(q)^n]
$$

As I promised before, total entanglemen entropy can be shown to be
$$
S = -\sum_{q}P(q)\log P(q) + \sum_q P(q) S(q).
$$
And $S$ and $S(q)$ are now of entangled nature.




<!-- <span style='color:red'></span> -->


<style>
body {
    font-family: sans-serif, Century, Cambria Math; 
    font-size: 15px;
}
h1, h2, h3 {
    font-family: Century;
    font-weight: bold;
}
</style>

<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
<script type="text/x-mathjax-config">
        MathJax.Hub.Config({ tex2jax: {inlineMath: [['$', '$']]}, messageStyle: "none" });
</script>