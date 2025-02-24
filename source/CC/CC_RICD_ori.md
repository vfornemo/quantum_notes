# CC-RICD

## Introduction

The electron-repulsion integral (ERI) in atomic orbital basis is a four-index tensor:

$$
(\mu\nu|\lambda\sigma) = \int \chi_\mu(\mathbf{r}_1) \chi_\nu(\mathbf{r}_1) \frac{1}{r_{12}} \chi_\lambda(\mathbf{r}_2) \chi_\sigma(\mathbf{r}_2) d\mathbf{r}_1 d\mathbf{r}_2
$$

The structure of ERI is sparse, and therefore a linear expansion over the products of particular one-electron functions, such as $\chi_\mu(\mathbf{r}_1) \chi_\nu(\mathbf{r}_1)$, is able to representing the "densities". The resolution-of-identity (RI) method is also called the density-fitting (DF) method.
 For both RI and Cholesky decomposition (CD) methods, the ERI is approximated by the following form:

$$
(\mu\nu|\lambda\sigma) \approx \sum_{P=1}^MB^P_{\mu\nu}B^P_{\lambda\sigma} 
$$

where $M$ is the rank of the decomposition, which depends on the target accuracy. RI and CD methods uses different decomposition matrices $B^P_{\mu\nu}$. The RI method uses the auxiliary basis set, while the CD method uses the Cholesky decomposition of the ERI tensor.

For RI method, it expands product densities $(\mu\nu|$ in an auxiliary basis set:

$$
(\mu\nu|\lambda\sigma) \approx\sum_{PQ}C^P_{\mu\nu}(P|Q)C^Q_{\lambda\sigma}\equiv\sum_{PQ}(\mu\nu|P)(P|Q)^{-1}(Q|\lambda\sigma)
$$

Indices P and Q denote auxiliary basis functions, and the $(P|Q)$ is the metric tensor:

$$
(P|Q) = \int \frac{P(\mathbf{r}_1)Q(\mathbf{r}_2)}{r_{12}}d\mathbf{r}_1\mathbf{r}_2
$$

The auxiliary basis expansion coefficients $C^L_{\mu\nu}$ are obtained by minimizing the difference between the actual and fitted product densities, leading to the following set of linear equations:

$$
\sum_{L}(K|L)C^{L}_{\mu\nu} = (K|\mu\nu)
$$

We define new auxiliary basis coefficients $B^K_{\mu\nu}$:

$$
B^K_{\mu\nu} \equiv \sum_{L}C^{L}_{\mu\nu}(L|K)^{1/2} = \sum_L (K|\mu\nu)(K|L)^{-1/2}
$$


## Cholesky Decomposition Coupled-Cluster (CD-CC)






## Resolution-of-Identity Coupled-Cluster (RI-CC) 

