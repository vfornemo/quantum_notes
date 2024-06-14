# DecoAD

## Decodense

## Decomposition

### Atomic

The energy of molecule can be decomposed into atomic contributions in the following way. First, the mean-field (MF) functional shared between HF and KS-DFT can be written as:

$$
E_{\text{MF}}(\bold{D}) = \sum_{\sigma=\alpha,\beta}\left(\text{Tr}[\bold{h}_\text{core}\bold{D}_\sigma]+\frac{1}{2}\text{Tr}[\bold{G}_\sigma(\bold{D})\bold{D}_\sigma]\right)
$$

where $\bold{D}_\sigma$ is the one-electron reduced density matrix (RDM1) for spin $\sigma$, $\bold{D}_\sigma = \bold{C}_\sigma\bold{C}_\sigma^\dagger$, $\bold{C}_\sigma$ is the coefficient matrix for spin $\sigma$. When written without a spin subscript, $\bold{D}$ is the sum of the RDM1s for both spins: $\bold{D} = \bold{D}_\alpha + \bold{D}_\beta$. $\bold{h}_\text{core}$ is the core Hamiltonian matrix, $\bold{h}_\text{core} = \bold{T}_\text{kin} + \bold{V}_\text{nuc}$. $\bold{G}_\sigma(\bold{D})$ denotes an effective Fock potential, $\bold{G}_\sigma(\bold{D}) = \bold{J}(\bold{D}_\alpha) + \bold{J}(\bold{D}_\beta) - \alpha\bold{K}_\sigma(\bold{D}_\sigma)$. In HF method, the exchange ratio $\alpha = 1.0$.

The Hatree-Fock energy can be written as:

$$
E_{\text{HF}} = \sum_K^{N_{\text{atom}}}E_K(\bold{D}, \delta_K)=\sum_K^{N_{\text{atom}}}E_{\text{elec}, K}(\bold{D}, \delta_K)+E_{\text{nuc}, K}
$$

where the $\delta_K$ is the atom-specific RDM1s (atom-RDM1s):

$$
\delta_K = \sum_{\sigma=\alpha,\beta}\delta_{K,\sigma} = \sum_{\sigma=\alpha,\beta}\sum_{i}^{N_\sigma}\bold{d}_{i,\sigma}\bold{p}_{i,\sigma}^K
$$

where the $\bold{d}_{i,\sigma}$ is the orbital-specific RDM1s (orb-RDM1s), $\bold{d}_{i,\sigma} = \bold{C}_{i,\sigma}\bold{C}_{i,\sigma}^\dagger$, and the $\bold{p}_{i,\sigma}^K$ is the population weight of an underlying $i$-th MO on a given atom $K$.

The nuclear contributions to the energy of atom $K$ are:

$$
E_{\text{nuc}, K} = Z_K\sum_{K< L}^{N_{\text{atom}}}\frac{Z_L}{|\bold{r}_K-\bold{r}_L|}
$$

where $Z_L$ and $\bold{r}_L$ denote the nuclear charge and position of atom $L$, respectively.

and the electronic contributions are:

$$
E_{\text{elec}, K} = \text{Tr}[\bold{T}_\text{kin}\delta_K] + \frac{1}{2}(\text{Tr}[\bold{V}_\text{K}\bold{D}] + \text{Tr}[\bold{V}_\text{nuc}\delta_K]) + \frac{1}{2}\sum_\sigma\text{Tr}[\bold{G}_{\text{HF},\sigma}(\bold{D})\delta_{K,\sigma}]
$$

The population weight of an underlying $i$-th MO on a given atom $K$ can be calculated using Mulliken population analysis:

$$
\bold{p}_{i}^K = \mathop{\text{Tr}}\limits_{\mu\in K}[\bold{d}_{i}\bold{S}]
$$

where the $\bold{S}$ is the overlap matrix of the basis functions.

Also, we can use IAO population analysis to calculate the population weight.

## Molecular Orbitals

### Canonical

In Hartree-Fock theory, the pseudo-eigenvalue equation is:

$$
\bold{F}_i\phi_i' = \varepsilon_i\phi_i'
$$

where $\bold{F}_i$ is the Fock matrix:

$$
\bold{F}_i = \bold{h}_i + \sum_{j}^{N_{\text{elec}}}\left(J_{ij} - K_{ij}\right)
$$

and the $\phi_i'$ is the canonical MOs. The canonical MOs are orthonormal and delocalized over the entire molecule.

### Localized

A single Slater determinant composed of a set of canonical MOs can be written as:

$$
\Phi = \frac{1}{\sqrt{N!}}
\begin{vmatrix}
\phi_1(1) & \phi_2(1) & \cdots & \phi_N(1) \\
\phi_1(2) & \phi_2(2) & \cdots & \phi_N(2) \\
\vdots & \vdots & \ddots & \vdots \\
\phi_1(N) & \phi_2(N) & \cdots & \phi_N(N) \notag
\end{vmatrix}
$$

Other sets of orbitals can be chosen by forming linear combinations of the canonical MOs:

$$
\Phi' = \Phi\bold{U}
$$
$$
\phi_i' = \sum_{j=1}^{N_{\text{orb}}}u_{ij}\phi_j
$$

The goal of *Localized Molecular Orbitals* (LMOs) is to find a set of localized orbitals that are spatially confined to a relatively small volume, and therefore clearly display which atoms are bonded and have the property of being approximately constant between structurally similar units in different molecules.

A set of LMOs may be obtained by optimizing the expectation value of a two-electron operator $\bold{\Omega}$:

$$
\bold{\Omega} = \sum_{i}^{N_{\text{orb}}}\left(\phi_i'\phi_i'|\bold{\Omega}|\phi_i'\phi_i'\right)
$$

#### Foster-Boys

The *Foster–Boys* localization scheme uses the square of the distance between two electrons as the operator and minimizes the expectation value:

$$
\langle\bold{\Omega}\rangle_{\text{FB}} = \sum_{i=1}^{N_{\text{orb}}}\langle\phi_i'\phi_i'|(\bold{r}_1 - \bold{r}_2)^2|\phi_i'\phi_i'\rangle
$$

The minimization of $\langle\bold{\Omega}\rangle_{\text{FB}}$ is equivalent to minimizing the sum of orbital contributions, each measuring the spatial extent of the orbital relative to the orbital centroid:

$$
\langle\bold{\Omega}'\rangle_{\text{FB}} = \sum_{i=1}^{N_{\text{orb}}}\langle\phi_i'|(\bold{r} - \langle\phi_i'|\bold{r}|\phi_i'\rangle)^2|\phi_i'\rangle
$$

#### Pipek-Mezey

The *Pipek-Mezey* localization scheme corresponds to maximizing the sum of Mulliken atomic charges:

$$
\langle\bold{\Omega}\rangle_{\text{PM}} = \sum_{A=1}^{N_{\text{atom}}}Q_A^2
$$

The contribution to atom A is given in:

$$
Q_A = Z_A - \sum_{i=1}^{N_{\text{orb}}}\sum_{\alpha\in A}^{M_{\text{basis}}}\sum_{\beta}^{M_{\text{basis}}}c_{\alpha i}c_{\beta i}S_{\alpha\beta}
$$

## Population Analysis

### Mulliken Population

The electron density $\rho$ at a certain position $\bold{r}$ from a single molecular orbital $\phi$ containing one electron can be written as:

$$
\rho_i(\bold{r}) = \phi_i^2(\bold{r})
$$

The $i$-th MO $\phi$ can be expanded in a set of normalized but non-orthogonal basis functions $\chi$, like:

$$
\phi_i = \sum^{M_{\text{basis}}}_\alpha c_{\alpha i}\chi_\alpha
$$

And the square of the MO will be like:

$$
\phi_i^2 = \sum^{M_{\text{basis}}}_{\alpha\beta} c_{\alpha i}c_{\beta i}\chi_\alpha\chi_\beta
$$

The total number of electrons can be obtained via integrating and summing over all occupied MOs:

$$
N_{\text{elec}} = \sum^{N_{\text{occ}}}_{i}\int\phi_i^2d\bold{r} =
\sum^{N_{\text{occ}}}_{i}\sum^{M_{\text{basis}}}_{\alpha\beta} c_{\alpha i}c_{\beta i}\int\chi_\alpha\chi_\beta d\bold{r} = \sum^{N_{\text{occ}}}_{i}\sum^{M_{\text{basis}}}_{\alpha\beta} c_{\alpha i}c_{\beta i}S_{\alpha\beta}
$$
where the $S_{\alpha\beta}$ is the overlap integral of basis functions $\chi_\alpha$ and $\chi_\beta$

$$
S_{\alpha\beta} = \int\chi_\alpha\chi_\beta d\bold{r}
$$

Now we introduce an occupation number $n$ for each MO:

$$
N_{\text{elec}} = \sum^{N_{\text{orb}}}_{i}n_i\int\phi_i^2d\bold{r} = \sum^{M_{\text{basis}}}_{\alpha\beta}\left(\sum^{N_{\text{orb}}}_{i}n_ic_{\alpha i}c_{\beta i}\right)S_{\alpha\beta} = \sum^{M_{\text{basis}}}_{\alpha\beta}D_{\alpha\beta}S_{\alpha\beta}
$$

where $D_{\alpha\beta}$ is the density matrix, which sums over the product of occupation number $n_i$ and MO coefficients $c_{\alpha i}c_{\beta i}$:

$$
D_{\alpha\beta} = \sum^{N_{\text{orb}}}_{i}n_ic_{\alpha i}c_{\beta i}
$$

The *Mulliken Population Analysis* uses the $\bold{D}\cdot\bold{S}$ matrix to distribute the electrons into atomic contributions. In the matrix, the diagonal element $D_{\alpha\alpha}S_{\alpha\alpha}$ is the number of electrons on the $\alpha$-th atomic orbital, and the off-diagonal element $D_{\alpha\beta}S_{\alpha\beta}$ is half the number of electrons shared by the $\alpha$-th and $\beta$-th AOs (another half is $D_{\beta\alpha}S_{\beta\alpha}$). The contributions from all AOs located on a given atom $A$ may be summed up to give the number of electrons on that atom. However, the contribution of basis functions located on different atoms also need to be determined.

For Mulliken population analysis, the atomic contributions are partitioned equally between the atoms to which the basis functions are attached. Therefore, the Mulliken electron population of atom $A$ is given by:

$$
\rho_A = \sum_{\alpha\in A}\sum_{\beta}D_{\alpha\beta}S_{\alpha\beta} =
\sum_{\alpha\in A}D_{\alpha\alpha} + \sum_{\alpha\in A}\sum_{\beta\notin A}D_{\alpha\beta}S_{\alpha\beta}
$$

The gross charge of atom $A$ is then:

$$
Q_A = Z_A - \rho_A
$$

where $Z_A$ is the nuclear charge of atom $A$.

### IAO

The MO $\phi$ can be expanded in a set of normalized but non-orthogonal basis functions, like:

$$
|\phi_i\rangle = \sum_\mu|\mu\rangle c^\mu_i
$$

where $\mu\in B_1$ are basis functions from a large basis set $B_1$. However, the basis functions $|\mu\rangle$ cannot be clearly associated with any atom, also it's often not on the atom it is placed on due to the $B_1$'s high variational freedom.

Also, we can expand the MOs over a minimal basis set $B_2$ of free-atom AOs:

$$
|\phi_i\rangle = \sum_\rho|\rho\rangle c^\rho_i
$$

where $\rho\in B_2$ are basis functions from a minimal basis set $B_2$. The basis functions $|\rho\rangle$ are clearly associated with the atoms they are placed on. However, the wave function would be inaccurate, even qualitatively incorrect, since free-atom AOs contain no polarization due to the molecular environment.

Therefore, we propose to first calculate an accurate wave function $|\Phi\rangle$, and then to form a set of polarized AOs $|\tilde{\rho}\rangle\notin B_2$ that can exactly express $|\Phi\rangle$s occupied MOs $|\phi_i\rangle$.

For this, we first split the free-atom AOs $|\tilde{\rho}\rangle\in B_2$ into contributions corresponding to a depolarized occupied space $\tilde{O} = \sum_{\tilde{i}}|\tilde{i}\rangle\langle\tilde{i}|$ and its complement $1-\tilde{O}$.
Let

$$
P_{12} = \sum_{\mu\nu\in B_1}|\mu\rangle S^{\mu\nu}\langle\nu|
$$
$$
P_{21} = \sum_{\rho\sigma\in B_2}|\rho\rangle S^{\rho\sigma}\langle\sigma|
$$

denote the projectors onto the bases $B_1$ and $B_2$, respectively, the $S^{\mu\nu}$ and $S^{\rho\sigma}$ are the inverse overlap matrices of the basis functions in $B_1$ and $B_2$, respectively.

The depolarized MOs $|\tilde{i}\rangle$ are obtained by projecting the accurate MOs $|i\rangle$ from the main basis set $B_1$ onto the minimal basis set $B_2$ and back.

$$
\lbrace|\tilde{i}\rangle\rbrace = \text{orth}\lbrace P_{12}P_{21}|i\rangle\rbrace
$$

Therefore, $|\tilde{i}\rangle$ lies completely within the space spanned by $\lbrace P_{12}|\tilde{\rho}\rangle, |\tilde{\rho}\rangle\in B_2\rbrace$, and thus the free-atom AOs $P_{12}|\tilde{\rho}\rangle$ can be exactly split into one subspace corresponding to the occupied orbitals span$\lbrace\tilde{O}P_{12}|\tilde{\rho}\rangle\rbrace$ and a second subspace corresponding to the unoccupied orbitals (virtual valence orbitals) span$\lbrace(1-\tilde{O})P_{12}|\tilde{\rho}\rangle\rbrace$. To obtain the polarized AOs $|\rho\rangle$ from the free-atom AOs $|\tilde{\rho}\rangle$, we simply project their contributions in $\tilde{O}$ and $1-\tilde{O}$ onto their polarized counterparts $O = \sum_{i}|i\rangle\langle i|$ and $1-O$:

$$
|\rho\rangle = \left[O\tilde{O}+(1-O)(1-\tilde{O})\right]P_{12}|\tilde{\rho}\rangle
$$

Using polarized AOs $|\rho\rangle$, we can define atomic charges:

$$
q_A = Z_A - \sum_{\rho\in A}\langle\rho|\gamma|\rho\rangle
$$

where $\gamma$ is the close-shell SCF density matrix:

$$
\gamma = 2\sum_{i}|i\rangle\langle i|
$$

$Z_A$ is the nuclear charge of atom $A$ and $\rho$ represents the polarized AOs (IAO).
