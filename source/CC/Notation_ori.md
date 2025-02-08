# Notation

## Dirac Notation
One electron integrals
$$
\langle p | \hat{h} | q \rangle = \int \phi^*_p(\mathbf{r}) \hat{h} \phi_q(\mathbf{r}) d\mathbf{r}
$$

Dirac notation for two electron integrals
$$
\langle pq | rs \rangle = \int \phi^*_p(\mathbf{r}_1) \phi^*_q(\mathbf{r}_2) \frac{1}{r_{12}} \phi_r(\mathbf{r}_1) \phi_s(\mathbf{r}_2) d\mathbf{r}_1 d\mathbf{r}_2
$$

Mulliken notation

$$
\left(pr|qs\right) = \int \phi^*_p(\mathbf{r}_1)\phi_r(\mathbf{r}_1) \frac{1}{r_{12}}  \phi^*_q(\mathbf{r}_2) \phi_s(\mathbf{r}_2) d\mathbf{r}_1 d\mathbf{r}_2
$$

ERI
$$
\langle pq||rs \rangle = \langle pq | rs \rangle - \langle pq | sr \rangle = \left(pr|qs\right) - \left(ps|qr\right)
$$

## CC Notation

### Normal order

Normal ordered string
$$
\{a^\dagger_p a_q\}
$$

Examples:
$$
\begin{aligned}
& \{a^\dagger_p a_q\} = a^\dagger_p a_q \\
& \{a_q a^\dagger_p\} = -a^\dagger_p a_q \\
& \{a^\dagger_p a^\dagger_q a_r a_s\} = a^\dagger_p a^\dagger_q a_r a_s \\
& \{a^\dagger_p  a_sa^\dagger_q a_r\} = -a^\dagger_p a^\dagger_q a_r a_s = a^\dagger_p a^\dagger_q a_s a_r \\
\end{aligned}
$$

Determinant

$$
|\Phi_0\rangle = a^\dagger_p a_q |0\rangle
$$
