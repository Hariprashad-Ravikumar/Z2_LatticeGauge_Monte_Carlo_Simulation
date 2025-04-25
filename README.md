## Theoretical Background

### QCD (Quantum ChromoDynamics)

QCD is the quantum field theory describing the strong interaction. It involves two types of fields:
- **Quarks** (spin-½ Dirac fields): \(\psi^i_f\), where color \(i = 1, 2, 3 = N_c\), and flavor \(f = u, d, s, c, b, t\)
- **Gluons** (massless spin-1 gauge fields): \(A^a_\mu\), where \(a = 1, \dots, 8 = N_c^2 - 1\), with local \(SU(3)\) symmetry

The QCD Lagrangian is:
\[
\mathcal{L}_{\text{QCD}}(\psi_f, A_\mu) = -\frac{1}{4}F^a_{\mu\nu}F^{a\mu\nu} + \sum_f \bar{\psi}_f(i\gamma^\mu D_\mu - m_f)\psi_f
\]

Where:
- \(F^a_{\mu\nu} = \partial_\mu A^a_\nu - \partial_\nu A^a_\mu - gf^{abc}A^b_\mu A^c_\nu\)
- \(D_\mu = \partial_\mu + igA^a_\mu t^a\)
- \([t^a, t^b] = if^{abc} t^c\) defines the \(SU(3)\) algebra

---

### Lattice QCD

Lattice QCD discretizes space-time onto a 4D lattice \(\Lambda_4\). The pure gauge action is:
\[
S_{\text{gauge}} = \frac{2}{g^2} \sum_{x\in\Lambda_4} \sum_{\mu<\nu} \left(1 - \text{Re}\,\text{Tr}[P_{\mu\nu}(x)]\right)
\]

Where the plaquette is:
\[
P_{\mu\nu}(x) = U_\mu(x) U_\nu(x+\hat{\mu}) U^\dagger_\mu(x+\hat{\nu}) U^\dagger_\nu(x)
\]

Expectation values are computed as path integrals:
\[
\langle \mathcal{O} \rangle = \frac{\int \mathcal{D}[U] \mathcal{D}[\psi] \mathcal{D}[\bar{\psi}]\, \mathcal{O}\, e^{-S_{\text{gauge}} - \int \bar{\psi}\mathcal{M}\psi}}{\int \mathcal{D}[U] \mathcal{D}[\psi] \mathcal{D}[\bar{\psi}]\, e^{-S_{\text{gauge}} - \int \bar{\psi}\mathcal{M}\psi}}
\]

The fermionic integrals yield the determinant of the Dirac operator:
\[
\langle \mathcal{O} \rangle = \frac{\int \mathcal{D}[U]\, \tilde{\mathcal{O}}\, \det(\mathcal{M})^2\, e^{-S_{\text{gauge}}}}{\int \mathcal{D}[U]\, \det(\mathcal{M})^2\, e^{-S_{\text{gauge}}}}
\]

---

### Monte Carlo Simulation in Lattice QCD

The observable is approximated via importance sampling:
\[
\langle \mathcal{O} \rangle \approx \frac{1}{N} \sum_{n=1}^N \mathcal{O}[U_n], \quad P[U_n] \propto e^{-S[U_n]}
\]

![Monte Carlo steps for Z2 LGT](mcstepsz2.pdf)
