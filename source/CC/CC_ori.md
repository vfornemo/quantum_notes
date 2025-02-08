# Couple Cluster theory

## Ground state

The CC wavefunction can be written as:
$$
\begin{equation}
    \Psi_{\text{CC}} = e^T |\Phi_0\rangle
\end{equation}
$$

The cluster operator $T$ can be expressed as:
$$
\begin{equation}
    T = T_1 + T_2 + T_3 + \dots
\end{equation}
$$

where the $T_n$ operator is defined as:

$$
\begin{equation}
    T_n = \frac{1}{n!^2}\sum t_{ijk\dots}^{abc\dots} a^\dagger ib^\dagger jc^\dagger k\dots
\end{equation}
$$

For example, the single excitation operator $T_1$ is defined as:

$$
\begin{equation}
    T_1 = \sum_{ia} t_i^a a^\dagger i
\end{equation}
$$

and the double excitation operator $T_2$ is defined as:

$$
\begin{equation}
    T_2 = \frac{1}{4}\sum_{ijab} t_{ij}^{ab} a^\dagger ib^\dagger j
\end{equation}
$$

The exponential operator $e^T$ can be expanded as:

$$
\begin{equation}
\begin{aligned}
    e^T  = & 1 + T + \frac{1}{2}T^2 + \frac{1}{3!}T^3 + \dots \\
      = & 1 + T_1 + T_2 + \dots \\
     & + \frac{1}{2}T_1^2 + T_1T_2 + \frac{1}{2}T_2^2 + \dots \\
     & + \frac{1}{3!}T_1^3 + \frac{1}{2}T_1^2T_2 + \frac{1}{2}T_1T_2^2 + \frac{1}{3!}T_2^3 + \dots
\end{aligned}
\end{equation}
$$

The single excitation can be expressed as:

$$
\begin{equation}
    \Phi_1 = T_1 |\Phi_0\rangle
\end{equation}
$$

and the double excitation can be expressed as:

$$
\begin{equation}
    \Phi_2 = (T_2 + \frac{1}{2}T_1^2 )|\Phi_0\rangle
\end{equation}
$$

Return to the Schrödinger equation, we can obtain that:

$$
\begin{equation}
    \hat{H} \Psi_\text{CC} = \hat{H} e^T |\Phi_0\rangle = E e^T |\Phi_0\rangle
\end{equation}
$$

Multiplying the equation by $e^{-T}$ from the left, we can obtain:

$$
\begin{equation}
    e^{-T} \hat{H} e^T |\Phi_0\rangle = E |\Phi_0\rangle
\end{equation}
$$

We introduce the effective Hamiltonian (similarity transformed Hamiltonian):

$$
\begin{equation}
    \bar{H} = e^{-T}H e^T
\end{equation}
$$

Therefore, the equation can be rewritten as:

$$
\begin{equation}
    \bar{H} |\Phi_0\rangle = E |\Phi_0\rangle
\end{equation}
$$

By projecting onto excitation determinants, we can obtain:

$$
\begin{equation}
    \langle \Phi_{ij\dots}^{ab\dots} | \bar{H} | \Phi_0 \rangle = 0
\end{equation}
$$

where $\Phi_{ij\dots}^{ab\dots}$ is the excitation determinant.

The ground state energy can be expressed as:

$$
\begin{equation}
    E_{\text{CC}} = \langle \Phi_0 | \bar{H} | \Phi_0 \rangle
\end{equation}
$$

The electronic Hamiltonian operator can be expressed as:
$$
\begin{equation}
    \hat{H} = E_{\text{HF}} +  \sum_{pq} F_{pq} p^\dagger q + \frac{1}{4} \sum_{pqrs} \langle pq||rs \rangle p^\dagger q^\dagger s r
\end{equation}
$$

There are four terms in the one electron operator: OO, OV, VO, and VV. For the two-electron operator, there are 9 distinct terms: OOOO, OOOV, OVOO, OOVV, VVOO, OVOV, VOVV, VVVO, VVVV.

The effective Hamiltonian can be rewritten using Baker-Campbell-Hausdorff formula as:

$$
\begin{equation}
\begin{aligned}
    \bar{H} = & \hat{H} + \left[\hat{H}, T\right] + \frac{1}{2!}\left[\left[\hat{H}, T\right], T\right] + \dots  \\
    = & \hat{H} + \left[\hat{H}, T_1\right] + \left[\hat{H}, T_2\right] + \frac{1}{2}\left[\left[\hat{H}, T_1\right], T_1\right] \\
    & + \frac{1}{2}\left[\left[\hat{H}, T_2\right], T_2\right] + \left[\left[\hat{H}, T_1\right], T_2\right] + \dots
\end{aligned}
\end{equation}
$$

knowing that:

$$
\begin{equation}
\begin{aligned}
    \left[\left[\hat{H}, T_1\right], T_2\right]  = \left[\left[\hat{H}, T_2\right], T_1\right]
\end{aligned}
\end{equation}
$$

Only the single and double cluster amplitudes contribute to the CC energy (that means only consider the contribution of single and double), and therefore the energy can be expressed as:

$$
\begin{equation}
\begin{aligned}
     E_{\text{CC}} & =  \langle \Phi_0 | \bar{H} |\Phi_0 \rangle \\
    & = \langle \Phi_0 | \hat{H} | \Phi_0 \rangle + \sum_{ia} F_{ia} t_i^a + \frac{1}{2} \sum_{ijab} \langle ij||ab \rangle t_{i}^{a} t_{j}^{b} + \frac{1}{4} \sum_{ijab} \langle ij||ab \rangle t_{ij}^{ab} \\
    & = E_{\text{HF}} + \sum_{ia} F_{ia} t_i^a + \frac{1}{4} \sum_{ijab} \langle ij||ab \rangle(t_{ij}^{ab}+t_{i}^{a} t_{j}^{b} -t_{i}^{b} t_{j}^{a} )
\end{aligned}

\end{equation}
$$

where $F_{ia}$ is the Fock matrix element, and $\langle ij||ab \rangle$ is the two-electron integral.
The $\langle \Phi_0 | \hat{H} | \Phi_0 \rangle$ equals to the Hartree-Fock energy $E_{\text{HF}}$.

### CCSD

In CCSD, the cluster operator is truncated at the single and double excitation level:

$$
\begin{equation}
    T = T_1 + T_2
\end{equation}
$$

and the wavefunction can be expressed as:

$$
\begin{equation}
    |\Psi_{\text{CCSD}} \rangle = e^{T_1+T_2} |\Phi_0\rangle
\end{equation}
$$

Projecting onto singly and doubly excited determinants, we can obtain:

$$
\begin{equation}
    \langle \Phi_{i}^{a} | e^{-T_1}\hat{H}e^{T_1} + \left[e^{-T_1}\hat{H}e^{T_1}, T_2\right] | \Phi_0 \rangle = 0
\end{equation}
$$

$$
\begin{equation}
\begin{aligned}
    & \langle \Phi_{ij}^{ab} | e^{-T_2-T_1}\hat{H}e^{T_1+T_2} | \Phi_0 \rangle 
    = \langle \Phi_{ij}^{ab} | e^{-T_2}e^{-T_1}\hat{H}e^{T_1}e^{T_2} | \Phi_0 \rangle 
    \\
    & = \langle \Phi_{ij}^{ab} | e^{-T_1}\hat{H}e^{T_1} + \left[e^{-T_1}\hat{H}e^{T_1}, T_2\right] + \frac{1}{2}\left[\left[e^{-T_1}\hat{H}e^{T_1}, T_2\right], T_2\right] | \Phi_0 \rangle = 0
\end{aligned}
\end{equation}
$$

The energy can be expressed as:

$$
\begin{equation}
    E_{\text{CCSD}} = \sum_a\sum_i t_i^a f_{ia} + \frac{1}{4} \sum_{ab}\sum_{ij}\tau_{ij}^{ab} \langle ij||ab \rangle
\end{equation}
$$

### CC2

In the CC2 method, the projection onto the singly excited determinant
is the same as the CCSD method:
$$
\begin{equation}
    \langle \Phi_{i}^{a} | e^{-T_1}\hat{H}e^{T_1} + \left[e^{-T_1}\hat{H}e^{T_1}, T_2\right] | \Phi_0 \rangle = 0
\end{equation}
$$

and the projection onto the doubly excited determinant is:

$$
\begin{equation}
    \langle \Phi_{ij}^{ab} | e^{-T_1}\hat{H}e^{T_1} + \left[F, T_2\right] | \Phi_0 \rangle = 0
\end{equation}
$$

## EOM-CC

Excited state can be expressed as:
$$
\begin{equation}
    |\Psi_{\text{ex}}\rangle = \mathscr{R} |\Phi_\text{g}\rangle
\end{equation}
$$
where $|\Psi_{\text{ex}}\rangle$ is the excited state, and $|\Phi_\text{g}\rangle$ is the ground state.
$\mathscr{R}$ is the excitation operator, which can be expressed as:
$$
\begin{equation}
    \mathscr{R} = \sum_{n} \mathscr{R}_n
\end{equation}
$$

$$
\begin{equation}
    \mathscr{R}_n = \frac{1}{n!^2}\sum r_{ijk\dots}^{abc\dots} a^\dagger ib^\dagger jc^\dagger k\dots
\end{equation}
$$

The ground state is approximated by:

$$
\begin{equation}
    |\Phi_\text{g}\rangle = e^T |\Phi_0\rangle
\end{equation}
$$

where $|\Phi_0\rangle$ is an arbitrary Slater determinant, usually SCF solution.

Therefore, the excited state can be expressed as:

$$
\begin{equation}
    |\Psi_{\text{ex}}\rangle =\mathscr{R} e^T  |\Phi_0\rangle = e^T \mathscr{R} |\Phi_0\rangle
\end{equation}
$$

which means the right excitation operator $\mathscr{R}$ and the cluster operator $T$ are commutative.


Inserting the equation into the Schrödinger equation, we can obtain:

$$
\begin{equation}
    H \mathscr{R} e^T  |\Phi_0\rangle = E \mathscr{R} e^T  |\Phi_0\rangle
\end{equation}
$$

The $T$ operator and $\mathscr{R}$ operator are necessarily commutative, so we can rewrite the equation
using the effective Hamiltonian operator $\bar{H}= e^{-T}H e^T$:

$$
\begin{equation}
    e^{-T}H e^T \mathscr{R}  |\Phi_0\rangle = \bar{H} \mathscr{R} |\Phi_0\rangle =
     E  \mathscr{R}  |\Phi_0\rangle
\end{equation}
$$

and then we can obtain the equation:

$$
\begin{equation}
   (\bar{H}-E) \mathscr{R}  |\Phi_0\rangle = 0
\end{equation}
$$

the effective Hamiltonian can be expressed in spin-orbital basis as:

$$
\begin{equation}
    \bar{H} = \sum_{pq} \mathscr{F}_{pq} a^\dagger_p a_q + \frac{1}{4} \sum_{pqrs} \mathscr{W}_{pqsr} a^\dagger_p a^\dagger_q a_s a_r
\end{equation}
$$

Note that the CC wave operator $e^T$ is not unitary, so the effective Hamiltonian $\bar{H}$ is not Hermitian. As a result, each root of $\bar{H}$ is associated with two eigenvectors, which are the left and right eigenvectors. The left eigenvector is defined as:

$$
\begin{equation}
    \langle \tilde{\Psi} | = \langle \Psi_L | =
    \langle \Phi_0 | \mathscr{L} e^{-T}
\end{equation}
$$

and the right eigenvector is defined as:

$$
\begin{equation}
    | \Psi \rangle = | \Psi_R \rangle =
    e^T \mathscr{R} |\Phi_0 \rangle
\end{equation}
$$

Note that the left deexcitation operator $\mathscr{L}$ is not commutative
with the cluster operator $T$.

The left de-excitation operator $\mathscr{L}$ can be expressed as:

$$
\begin{equation}
    \mathscr{L} = \sum_{n} \mathscr{L}_n
\end{equation}
$$

$$
\begin{equation}
    \mathscr{L}_n = \frac{1}{n!^2}\sum l_{abc\dots}^{ijk\dots} i^\dagger aj^\dagger bk^\dagger c\dots
\end{equation}
$$

The left and right operators satisfy the biorthogonality condition:

$$
\begin{equation}
    \langle \mathscr{L}_i | \mathscr{R}_j \rangle = \delta_{ij}
\end{equation}
$$

The two sets of solutions satisfy the biorthogonality condition:

$$
\begin{equation}
    \langle \tilde{\Psi}^{(i)} | \Psi^{(j)} \rangle = 1
\end{equation}
$$

If the C is unity, we can rewrite the equation as:

$$
\begin{equation}
    \langle \tilde{\Psi} | \Psi \rangle = 1
\end{equation}
$$

and therefore the energy can be expressed as:

$$
\begin{equation}
    E = \langle \tilde{\Psi} | H | \Psi \rangle =
    \langle \Phi_0 |\mathscr{L} \bar{H} \mathscr{R}| \Phi_0 \rangle
\end{equation}
$$

Note that for ground state, we have $\mathscr{L} = \mathscr{R} = 1$, so the energy can be expressed as:

$$
\begin{equation}
    E_{\text{CC}} = \langle \Phi_0 | \bar{H} | \Phi_0 \rangle
\end{equation}
$$

## Derivative

### General

The asymmetrized, perturbation-independent, deexcitation operator
$\Lambda$ can be expressed as:

$$
\begin{align}
& \Lambda = \sum_{n} \Lambda_n \\

& \Lambda_1 = \sum_{ia} \lambda_i^a i^\dagger a \\

& \Lambda_2 = \frac{1}{4}\sum_{ijab} \lambda_{ij}^{ab} a_i^\dagger a_j^\dagger a_b a_a \\

& \Lambda_n = \frac{1}{n!^2}\sum \lambda_{abc\dots}^{ijk\dots} i^\dagger aj^\dagger bk^\dagger c\dots

\end{align}
$$

The $\lambda$ amplitude satisfies the condition:

$$
\begin{equation}
    \langle \Phi_0 | \Lambda | \Phi \rangle
    = - \langle \Phi_0 | (H_Ne^T)_c | \Phi \rangle
    \langle \Phi | (H_Ne^T)_c - \Delta E| \Phi \rangle ^{-1}
\end{equation}
$$

Therefore, we have:

$$
\begin{equation}
    \langle \Phi_0 | (H_N^\xi e^T)_c | \Phi_0 \rangle + \langle \Phi_0 | \Lambda | \Phi \rangle \langle \Phi | (H_N^\xi e^T)_c | \Phi_0 \rangle  = \Delta E^\xi
\end{equation}
$$

Finally the derivative of the energy can be expressed as:

$$
\begin{equation}
\begin{aligned}
    \Delta E^\xi = & \mathbf{D}_{ij}f_{ij}^\xi + \mathbf{D}_{ab}f_{ab}^\xi + \sum_{pqrs}\Gamma(pq,rs) \langle pq||rs \rangle^\xi \\
    = & \mathbf{D}_{ij}f_{ij}^\xi + \mathbf{D}_{ab}f_{ab}^\xi  \\
   & + \Gamma(ij,ab)\langle ij||ab\rangle^\xi
    + \Gamma(ab,cd)\langle ab||cd\rangle^\xi   \\
   & + \Gamma(kl,ij)\langle kl||ij\rangle^\xi
    + \Gamma(ja,bi)\langle ja||bi\rangle^\xi   \\
   & + \Gamma(ai,bc)\langle ai||bc\rangle^\xi
    + \Gamma(jk,ia)\langle jk||ia\rangle^\xi   \\
\end{aligned}
\end{equation}
$$

where the $D_{pq}$ is the relaxed density matrix, and the $\Gamma_{pq,rs}$ is the effective density matrix.

### CCSD Derivative

The CCSD gradient can be expressed as:

$$
\begin{equation}
    \frac{\partial E_{\text{CCSD}}}{\partial \xi} =
\sum_{pq} D_{pq}f_{pq}^{(\xi)} + \sum_{pqrs}\Gamma(pq,rs) \langle pq||rs \rangle^\xi
+ \sum_{pq}I_{pq}S_{pq}^{\xi}
\end{equation}
$$

### EOM-CC Derivative

The derivative of the EOM-CC energy can be expressed as:

$$
\begin{equation}
    \frac{\partial E_{\text{EOM-CC}}}{\partial \xi} =
D_{pq}f_{pq}^{(\xi)} + \frac{1}{4}\Gamma_{pqrs} \langle pq||rs \rangle^\xi
+ I_{pq}S_{pq}^{\xi}

\end{equation}
$$

where:
overlap derivative:
$$
\begin{equation}
S_{pq}^{\xi} = c_{\mu p} \frac{\partial S_{\mu\nu}}{\partial \xi} c_{\nu q}
= c_{\mu p} c_{\nu q} \left( \langle \frac{\partial\chi_\mu}{\partial\xi}|\chi_\nu \rangle + \langle \chi_\mu|\frac{\partial\chi_\nu}{\partial\xi} \rangle \right)
\end{equation}
$$

ERI derivative:
$$
\begin{equation}
\langle pq||rs \rangle^\xi = c_{\mu p} c_{\nu q} c_{\lambda r} c_{\sigma s} \frac{\partial \langle \mu\lambda||\nu\sigma \rangle}{\partial \xi}
\end{equation}
$$

$$
\begin{equation}
\phi_p = c_{\mu p} \xi_{\mu}
\end{equation}
$$

Fock matrix derivative:
$$
\begin{equation}
f_{pq}^{(\xi)} = c_{\mu p}c_{\nu q} \left(\frac{\partial h_{\mu\nu}}{\partial\xi}+ c_{\lambda i}c_{\sigma i}\frac{\partial\langle \mu\lambda||\nu\sigma \rangle}{\partial\xi} \right)
= h_{pq}^\xi + \sum_{m} \langle pm||qm \rangle^\xi
\end{equation}
$$

Derivative of the MO coefficients:

$$
\begin{equation}
\frac{\partial c_{\mu p}}{\partial \xi} = \sum_q U_{qp}^\xi c_{\mu q}
\end{equation}
$$

where $U_{qp}^\xi$ is the CPHF coefficient.

Relaxed density matrix:
$$
\begin{equation}
D_{pq} = \gamma_{pq} + z_{pq}
\end{equation}
$$

Effective density matrix:

$$
\begin{equation}
\gamma_{pq} = \langle \Phi_0 | \mathscr{L}[p^\dagger qe^T]_c\mathscr{R} |\Phi_0 \rangle
+ \langle \Phi_0 | \mathcal{Z}[p^\dagger qe^T]_c|\Phi_0 \rangle
\end{equation}
$$

$$
\begin{equation}
\Gamma_{pqrs}
= \langle \Phi_0 | \mathscr{L}[p^\dagger q^\dagger sr e^T]_c\mathscr{R} |\Phi_0 \rangle
+ \langle \Phi_0 | \mathcal{Z}[p^\dagger q^\dagger sr e^T]_c|\Phi_0 \rangle
\end{equation}
$$

where $c$ indicates the limitation to connected diagrams.

Auxiliary deexcitation operator $\mathcal{Z}$:

$$
\begin{equation}
\mathcal{Z} = \sum_{n} \mathcal{Z}_n
\end{equation}
$$

$$
\begin{equation}
\mathcal{Z}_n = \frac{1}{n!^2}\sum \zeta_{abc\dots}^{ijk\dots} i^\dagger aj^\dagger bk^\dagger c\dots
\end{equation}
$$

### Lagrangian of EOM-CC derivative

The EOM energy can be expressed as:



The full energy derivative can be expressed as:

$$
\begin{equation}
\frac{\mathrm{d} E }{\mathrm{d} \xi} = \frac{\partial E}{\partial \xi} +
\frac{\partial E}{\partial L}\frac{\partial L}{\partial \xi} + \frac{\partial E}{\partial R}\frac{\partial R}{\partial \xi} +
\frac{\partial E}{\partial T}\frac{\partial T}{\partial \xi} + \frac{\partial E}{\partial C}\frac{\partial C}{\partial \xi}
\end{equation}
$$

The first term is the Hellmann-Feynman contribution:

$$
\begin{align}
& \frac{\partial E}{\partial \xi} =  \sum_{pq} h_{pq}^\xi \gamma_{pq}' + \frac{1}{4}\sum_{pqrs}\langle pq||rs \rangle^\xi \Gamma_{pqrs}' 
\\
& h_{pq}^\xi = \frac{\partial h_{pq}}{\partial \xi} = \sum_{\mu\nu}C_{\mu p}h_{\mu\nu}^\xi C_{\nu q} 
\\
& h_{\mu\nu}^\xi = \langle \chi_\mu | \frac{\partial \hat{h}}{\partial \xi} | \chi_\nu \rangle + \langle \frac{\partial \chi_\mu}{\partial\xi} | \hat{h} | \chi_\nu \rangle + \langle \chi_\mu | \hat{h} | \frac{\partial \chi_\nu}{\partial\xi} \rangle
\\
& \langle pq||rs \rangle^\xi = \frac{\partial \langle pq||rs \rangle}{\partial \xi} = \sum_{\mu\nu\lambda\sigma}C_{\mu p}C_{\nu q}\langle \chi_\mu\chi_\nu||\chi_\lambda\chi_\sigma \rangle^\xi C_{\lambda r}C_{\sigma s} \\

\end{align}
$$

$$
\begin{equation}
\begin{aligned}
\langle \chi_\mu\chi_\nu||\chi_\lambda\chi_\sigma \rangle^\xi = &
\langle \frac{\partial \chi_\mu}{\partial\xi}\chi_\nu||\chi_\lambda\chi_\sigma \rangle +
\langle \chi_\mu\frac{\partial \chi_\nu}{\partial\xi}||\chi_\lambda\chi_\sigma \rangle  
\\
& + \langle \chi_\mu\chi_\nu||\frac{\partial \chi_\lambda}{\partial\xi}\chi_\sigma \rangle +
\langle \chi_\mu\chi_\nu||\chi_\lambda\frac{\partial \chi_\sigma}{\partial\xi} \rangle
\end{aligned}
\end{equation}
$$

The EOM energy is stationary with respect to the left and right eigenvectors, 
so the second and third terms are zero:

$$
\begin{equation}
\frac{\partial E}{\partial L} = \frac{\partial E}{\partial R} = 0
\end{equation}
$$

Then there is so-called amplitude response $\frac{\partial E}{\partial T}$ 
 and orbital response $\frac{\partial E}{\partial C}$.

The Lagrangian derivative can be expressed as:

$$
\begin{equation}
\begin{aligned}
\frac{\partial \mathcal{L}(L, R, T, C,Z, \Lambda, \Omega)}{\partial \xi} = & 
\langle \Phi_0 Le^{-T} | \frac{\partial H}{\partial\xi} | e^TR\Phi_0 \rangle 
\\
+ & \langle \Phi_0 Ze^{-T} | \frac{\partial H}{\partial\xi} | e^T\Phi_0 \rangle 
\\ 
+ & \frac{1}{2}\sum_{pq}\lambda_{pq}\frac{\partial f_{pq}}{\partial\xi} + 
\sum_{pq}\omega_{pq}\frac{\partial S_{pq}}{\partial\xi}
\\
= & \sum_{pq}h_{pq}^\xi\rho_{pq} + \frac{1}{4}\sum_{pqrs}\langle pq||rs \rangle^\xi \Pi_{pqrs} \\
+ & \sum_{pq}\omega_{pq}S_{pq}^{\xi}

\end{aligned}
\end{equation}
$$

The effective density matrices $\rho$ and $\Pi$ can be expressed as:

$$
\begin{align}
& \rho = \gamma' + \gamma'' + \gamma'''
\\
& \Pi = \Gamma' + \Gamma'' + \Gamma'''
\end{align}
$$

where the $\gamma'$ and $\Gamma'$ are the so-called non-relaxed density matrices:

$$
\begin{align}
& \gamma' = \frac{1}{2}\langle \Psi_L | p^\dagger q+q^\dagger p |\Psi_R \rangle
\\
& \Gamma' = \frac{1}{2}\langle \Psi_L | p^\dagger q^\dagger sr + s^\dagger r^\dagger pq |\Psi_R \rangle
\end{align}
$$

and $\gamma''$ and $\Gamma''$ are amplitude response contributions:

$$
\begin{align}
& \gamma'' = \frac{1}{2}\langle \Phi_0Ze^{-T} | p^\dagger q+q^\dagger p |e^T\Phi_0 \rangle
\\
& \Gamma'' = \frac{1}{2}\langle \Phi_0Ze^{-T} | p^\dagger q^\dagger sr + s^\dagger r^\dagger pq |e^T\Phi_0 \rangle
\end{align}
$$

and $\gamma'''$ and $\Gamma'''$ are orbital response contributions. $\gamma'''$
is related to the Lagrange multiplier $\lambda$, and $\Gamma'''$ is related to 
$\gamma'''$ and $\delta$.

## Properties

Different CC2 variants:

![IP](figures/IP.png)

