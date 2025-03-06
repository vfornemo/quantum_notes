# CC Amplitude

## CC ground state lambda amplitudes

The CC ground state lambda Lagrangian is given by

$$
L = \langle \Phi_0|(1+\Lambda) \bar{H} | \Phi_0 \rangle = 0
$$

The CC lambda equations are given by

$l_1$:
$$
\lambda_{a}^{i} = \frac{\partial L}{\partial t_i^a} = \frac{\partial E_\text{CC}}{\partial t_i^a} + \sum_{ck}\lambda_{c}^{k}\frac{\partial \Omega_{kc}}{\partial t_i^a} + \sum_{klcd}\lambda_{cd}^{kl}\frac{\partial \Omega_{klcd}}{\partial t_i^a} = 0
$$

$l_2$:
$$
\lambda_{ab}^{ij} = \frac{\partial L}{\partial t_{ij}^{ab}} = \frac{\partial E_\text{CC}}{\partial t_{ij}^{ab}} + \sum_{ck}\lambda_{c}^{k}\frac{\partial \Omega_{ck}}{\partial t_{ij}^{ab}} + \sum_{klcd}\lambda_{cd}^{kl}\frac{\partial \Omega_{klcd}}{\partial t_{ij}^{ab}} = 0
$$

we define:

$$
A_{\mu_i\nu_j} = \frac{\partial\Omega_i}{\partial t_j}
$$

For CC2 $l_1$, we have:

$$
A_{\mu_1\nu_1} = \langle\Phi_i^a|[\bar{H}_1+[\bar{H}_1,T_2],a^\dagger i]|0\rangle
$$
$$
A_{\mu_2\nu_1} = \langle\Phi_{ij}^{ab}|[\bar{H}_1,a^\dagger i]|0\rangle
$$

and for $l_2$:

$$
A_{\mu_1\nu_2} = \langle\Phi_{i}^{a}|[\bar{H}_1,a^\dagger b^\dagger ij]|0\rangle
$$

$$
A_{\mu_2\nu_2} = \langle\Phi_{ij}^{ab}|[F,a^\dagger b^\dagger ij]|0\rangle
$$

where:

$$
\bar{H}_1 = e^{-T_1}\hat{H}e^{T_1}
$$

Compared to CCSD lambda amplitudes, all terms containing $t_2l_2$ are missing in the CC2 $\lambda_1$ equations. All terms containing $t_2$ and $l_2\langle pq||rs\rangle$ are missing in the CC2 $\lambda_2$ equations. Therefore, we can write the full expression for CC2 lambda amplitudes as:

$l_1$:
$$
\begin{aligned}
l_a^i\Delta_i^a = &
F^{(2)}_{ia} + \sum_c l_c^i F^{(2)}_{ca} - \sum_k l_a^k F^{(2)}_{ki}  \\
& - \frac{1}{2}\sum_{jbc} l_{bc}^{ij} I^{(3a)}_{jabc} - \sum_{kc} l_{c}^{k} I^{(1)}_{kaic} - \frac{1}{2}\sum_{jkb} l_{ab}^{jk} I^{(2b)}_{jkib}
\end{aligned}
$$

$l_2$:
$$
\begin{aligned}
l_{ab}^{ij}\Delta_{ij}^{ab} = &
\langle ij||ab\rangle + P(ab)\sum_k I^{(6)}_{ijka}l_{b}^{k} + P(ab)\sum_{c} l_{ac}^{ij}F^{(2a)}_{cb} \\
&+ P(ij)\sum_c I^{(7)}_{icab}l_{c}^{j} + P(ij)\sum_{k} l_{ab}^{jk}F^{(2a)}_{ki} + P(ab)P(ij)l_a^iF^{(2)}_{jb} \\
\end{aligned}
$$

The intermediates are defined as:
$$
\begin{aligned}
& F^{(1)}_{ca} = f_{ca} + \sum_{kd}\langle kc||da\rangle-\frac{1}{2}\sum_{kld}\langle kl||ad\rangle  t_{kl}^{cd}
\\
& F^{(2)}_{ia} = f_{ia} + \sum_{jb}\langle ij||ab\rangle t_j^b
\\
& F^{(2)}_{ca} = F^{(1)}_{ca} - f_{ca} - \sum_{k}f_{ka}t_k^c - \sum_{kld}\langle kl||ad\rangle t_k^ct_l^d
\\
& F^{(2)}_{ik} = f_{ik} + \sum_af_{ka}t_i^a + \sum_{la}\langle kl||ia\rangle t_l^a + \sum_{lab}\langle kl||ab\rangle t_i^at_l^b + \frac{1}{2}\sum_{lab}\langle kl||ab\rangle t_{il}^{ab}
\\
&F^{(2a)}_{ki} = f_{ki} + \sum_a f_{ia}t_k^a
\\
&F^{(2a)}_{cb} = f_{cb} - \sum_k f_{kb}t_k^c
\\
&I^{(1)}_{kaic}= \langle ka||ic\rangle - \sum_{d}\langle ic||ad\rangle t_{k}^{d} - \sum_{ld}\langle il||ad\rangle t_{kl}^{cd} + \sum_{ld}\langle il||ad\rangle t_{k}^{d}t_l^c-\sum_l\langle il||ka\rangle t_l^c
\\
&I^{(2b)}_{jkib} = \langle jk||ib\rangle - \sum_l I^{(4)}_{jkil}t_l^b - P(jk)\sum_c\langle ib||kc\rangle t_j^c + \frac{1}{2}\sum_{cd}\langle ib || cd\rangle \tilde{t}_{jk}^{cd}\\
\\
&I^{(3a)}_{jabc} = \langle ja||bc\rangle - \sum_d I^{(5)}_{bcad}t_j^d + P(bc)\sum_k[\langle kb||ja\rangle -\frac{1}{2}\sum_l\langle kl || ja\rangle t_l^b]t_k^c\\
\\
&I^{(6)}_{ijka} = \langle ij||ka\rangle - \sum_{d}\langle ij||ad\rangle t_k^d
\\
&I^{(7)}_{icab} = \langle ic||ab\rangle - \sum_{k}\langle ik||ab\rangle t_c^k
\\
&\tilde{t}_{ij}^{ab} = \frac{1}{2}P(ij)P(ab)t_i^at_j^b
\end{aligned}
$$

For RI-CC2, the lambda equations are given by:

$l_1$:
$$
\begin{aligned}
l_a^i\Delta_i^a = &
F^{(2)}_{ia} + \sum_c l_c^i F^{(2)}_{ca} - \sum_k l_a^k F^{(2)}_{ki} -\sum_{jbcP} l_{bc}^{ij}M_{ac}^PM_{jbP}^{2}
\\
& - \sum_{kc} l_{c}^{k} \left\{\sum_PM_{ik}^PM_{ac}^P-\sum_PM_{kc}^PB_{ia}^P+\sum_{ld}t_{kl}^{cd}\left(\sum_PB_{id}^PB_{la}^P\right)\right\}
\\
& - \frac{1}{2}\sum_{jkb} l_{ab}^{jk} I^{(2b)}_{jkib}
\end{aligned}
$$

$l_2$:
$$
\begin{aligned}
l_{ab}^{ij}\Delta_{ij}^{ab} = &
P(ab)\left\{\sum_PB_{ia}^PB_{jb}^P+\sum_c F_{cb}^{(2a)}l_{ac}^{ij}\right\} + P(ij)\left\{\sum_kF_{ki}^{(2a)}l_{ab}^{jk}+F_{jb}^{(2)}l_a^i\right\} \\
& + P(ab)\left\{\sum_PB_{ia}^P\left(\sum_cM_{bc}^Pl_c^j-\sum_kM^P_{jk}l_b^k\right)\right\}
\end{aligned}
$$

The intermediates are defined as:
$$
\begin{aligned}
&F^{(2)}_{ia}=f_{ia}+\sum_{P}B_{ia}^PM^P - \sum_{jP}B_{ja}^P(M_{ij}^P - B_{ij}^P)
\\
&F^{(2)}_{bc}=f_{bc}-\sum_{kP}B_{kc}^P(M^{2T}_{kbP}+M^{3T}_{kbP}-M^{2TT}_{kbP})+\sum_P M^PM^P_{cb}-\sum_k f_{kc}t_k^b
\\
&F^{(2)}_{jk}=f_{jk}+\sum_c f_k^ct_j^c + \sum_PM_{kj}^PM^P - \sum_{lP}M_{lj}^P(M_{kl}^P-B_{kl}^P) + \sum_{cP}B_{kc}^PM_{jcP}^{2T}
\\
&F_{bc}^{(2a)}=f_{bc}-\sum_k f_{kc}t_k^b
\\
&F_{jk}^{(2a)}=f_{jk}+\sum_c f_k^ct_j^c
\\
&F_{ia}^{(2)} = f_{ia}+\sum_PB_{ia}^PM^P - \sum_{jP}B_{ja}^P(M_{ij}^P - B_{ij}^P)
\\
&I^{(2b)}_{ijka} = P(ij)\sum_P M_{kj}^P\left\{M_{iaP}^{1T}+ M_{iaP}^{2TT}-B_{ia}^P-M^{3T}_{iaP}\right\}
\\
&M_{ij}^P = B_{ij}^P + \sum_cB_{ic}^Pt_j^c
\\
&M_{ab}^P = B_{ab}^P - \sum_iB_{ia}^Pt_i^b
\\
&M_{ia}^P = \sum_c B_{ac}^P t_i^c - \sum_k B_{ik}^P t_k^a - \sum_k t_k^a(M_{ki}^P - B_{ki}^P) + B_{ia}^P + \sum_{ld}B_{ld}^Pt_{il}^{ad}
\\
&M_{iaP}^{2} = \sum_c B_{ac}^P t_i^c - \sum_k B_{ik}^P t_k^a - \sum_k t_k^a(M_{ki}^P - B_{ki}^P) + B_{ia}^P 
\\
&M^P = \sum_{ia}B_{ia}^Pt_i^a
\\
&M_{iaP}^{1T}=\sum_{k}B_{ik}^Pt_{k}^{a}
\\
&M_{iaP}^{2T}=\sum_{ld}B_{ld}^Pt_{il}^{ad}
\\
&M_{iaP}^{3T}=\sum_{c}B_{ac}^Pt_{i}^{c}
\\
&M_{iaP}^{2TT}=\sum_kt_k^a(M_{ki}^P - B_{ki}^P)
\\
\end{aligned}
$$