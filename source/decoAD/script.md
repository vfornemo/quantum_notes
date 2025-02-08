# Auto Differentiation in Atomic Properties Decomposition

Script

## Abstract

Molecular properties are essential for understanding the behavior of molecules in various environments. By decomposing molecular properties into atomic contributions, a deeper understanding of the local environment within molecules can be gained. Our work introduces auto differentiation approach into molecular properties decomposition, allowing a high-order property, polarizability, to be decomposed into atomic contributions. Although there are currently limitations in the high-order differentiation process, the results obtained mostly align with our chemical intuition.

## Slide 1

Motivation

Molecular properties, such as dipole moment, polarizability and magnetizability, are essential for understanding the behavior of molecules in various environments. The exploration of local properties of molecules can elucidate the underlying mechanisms of chemical reactions, and provide insights into the design of new molecules with desired properties. By decomposing the molecular properties into atomic contributions, we can gain a deeper understanding of the local environment, such as functional groups, of atoms within molecules, as well as know how these findings align with our chemical intuition.

There are already many theories focusing on the decomposition of energy and some first-order properties, such as the electrostatic potential. However, the decomposition of second-order properties, such as polarizability, is also important for understanding the behavior of molecules.

## Slide 2

Theory - Atomic decomposition

The atomic-RDM1s can be obtained by population analysis methods. Therefore, we can obtain the atomic contributions to the molecular properties by evaluating these terms. Many molecular properties are derivatives of the energy, so they can also be decomposed into atomic contributions by the chain rule. In this work, we explore the atomic contributions to the molecular polarizability, which is the second derivative of energy and the first derivative of the dipole moment. We use auto differentiation (AD) to calculate the derivatives, and thus obtain the atomic contributions to the molecular properties.

## Slide 3

Theory - Population analysis

In this work we use two population analysis methods: the Mulliken population analysis and the intrinsic atomic orbitals (IAOs) method. The Mulliken population analysis is a simple and intuitive method, but it has some drawbacks, such as the basis set dependence. The IAOs method is a more advanced method, which takes the polarization of the atomic orbitals into account, and provides a more accurate description of the atomic contributions to the molecular properties.

## Slide 4

Theory - Molecular Orbitals

In this work we use two kinds of molecular orbitals: the delocalized molecular orbitals (also called canonical molecular orbitals) and the localized molecular orbitals. The localized molecular orbitals include Pipek-Mezey (PM) orbitals and Foster-Boys (FB) orbitals. The PM orbitals are obtained by maximizing the sum of Mulliken atomic charges, and the FB orbitals are obtained by minimizing the sum of orbital contributions. The localized molecular orbitals can provide a more accurate description of the atomic contributions to the molecular properties, because they are more localized on the atoms instead of the whole molecule.

## Slide 5

Methodology

Decodense-AD

In this work we will calculate the atomic contributions to molecular polarizability. We apply auto differentiation (AD) package JAX into the Decodense code to calculate the atomic contributions to the molecular properties. The Decodense code is a Python code that can calculate the atomic and bond contributions to the molecular properties such as energy and dipole moment. Since the polarizability is the second-order derivative of the energy to the external field as well as first-order derivative of the dipole moment to the external field, we can apply auto differentiation to calculate the atomic contributions to the molecular polarizability, starting from the decomposition of energy and dipole moment.
Parameters:

- Molecule: CH4, H2O
- Basis set: aug-pcseg-1, 6-311++G**
- Molecular orbitals: canonical, PM, FB
- Population analysis: Mulliken, IAOs

## Slide 6

Results - H2O

This is the decomposition of polarizability of water into atomic contributions calculated by first derivatives of the dipole moment. In both Figure (a) and (b), we could see that there is little difference among the results calculated by these methods, except the results calculated by PM/Mulliken. Still, the results are intuitive because the polarizability of water is mainly determined by the oxygen atom. The change of basis set and molecular orbitals has little effect on the results, which indicates that the results are stable and reliable.

## Slide 8

Results - H2O

When using the second derivatives of the energy to calculate the atomic contributions to the polarizability, the results seems different. Not only the change of methods, but also basis sets can affect the results. The contribution of hydrogen atoms calculated by some methods appears negative. That implies the instability of the second order differentiation process, which is currently the bottleneck of applying AD to the property decomposition of atomic contributions. Despite this, the results are still intuitive, and the polarizability of water is mainly determined by the oxygen atom.

## Slide 9

Results - CH4

This is the decomposition of polarizability of methane into atomic contributions calculated by first derivatives of the dipole moment. We could see that compared to the polar molecule of water, the results of this non-polar molecule is very unstable. The results calculated by PM/IAO are removed due to obvious numerical errors. The results calculated by FB/Mulliken are completely opposite to the results calculated by other methods. For basis set aug-pcseg-1, we could find that the contribution of four hydrogen atoms are different with some methods. This indicates that the decomposition of polarizability of methane is more difficult than that of water, and the results are less reliable. In fact, the non-polar molecule does not have a constant dipole moment, so the differentiation process is more complex and unstable.

## Slide 10

Results - CH4

When using the second derivatives of the energy to calculate the atomic contributions to the polarizability, the results seems more unstable. The results calculated by canonical orbitals contradict the results calculated by localized orbitals. This can be explained that the canonical orbitals are located all over the molecule, so the atomic contributions may not be accurate. The results calculated by PM/IAO are removed due to obvious numerical errors. The results calculated by basis set of aug-pcseg-1 have the worst performance, which indicates that the selection of basis set has a great influence on the results.

## Slide 11

Conclusions

By decomposing the polarizability of water and methane into atomic contributions, we find that the decomposition results mostly align with our chemical intuition. The polarizability of water is mainly determined by the oxygen atom, and the polarizability of methane is mainly determined by the carbon atom. However, due to the characteristics of JAX differentiation, the results obtained by certain methods, such as PM/IAO can be inaccurate, or even absurd, which requires further understanding of the differentiation process. Also, the selection of basis set and molecular orbitals also affect the results, which requires careful selection of these parameters.
Despite this, we can still gain knowledge of the atomic contributions to the molecular polarizability by current results.

## Slide 12

Outlook

Since many molecular properties are the high-order derivatives of the energy, we can apply the auto differentiation method to calculate the atomic contributions to these properties, such as magnetizability, nuclear spin-spin coupling constants, harmonic vibrational frequencies, etc. To achieve this, a better understanding of the differentiation process is required to avoid the instability during the high-order differentiation. In addition, a better-optimized set of localized orbitals can provide more accurate atomic contributions to the molecular properties, which is related to the initial guess. Therefore the initial guess can be adjusted to improve the quality of the localized orbitals.
