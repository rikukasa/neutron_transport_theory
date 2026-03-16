
## 1 Derivation of the Neutron Transport Equation

### 1.1 Representation of Neutrons

The number of neutrons located at time $t$, within a spatial volume $dV$ around position $\vec{r}$, traveling in directions within a solid angle $d\Omega$ around $\vec{\Omega}$, and having energies within an interval $dE$ around energy $E$, can be expressed as

$$
N(\vec{r}, \vec{\Omega}, E, t)\, dV\, d\Omega\, dE
$$

> (1.1)

where $N(\vec{r}, \vec{\Omega}, E, t)$ is the neutron density with energy $E$ traveling in direction $\vec{\Omega}$ at position $\vec{r}$ and time $t$.

In reactor physics, the number of neutrons passing through a unit area per unit time is an important quantity. Therefore, the neutron flux $\phi$ is commonly used, which is defined by multiplying the neutron density by the neutron speed $v$. The neutron flux can be written as

$$
\phi(\vec{r}, \vec{\Omega}, E, t) = v\, N(\vec{r}, \vec{\Omega}, E, t).
$$

> (1.2)

Since $\phi(\vec{r}, \vec{\Omega}, E, t)$ depends on the direction $\vec{\Omega}$, it is referred to as the angular neutron flux.

The scalar neutron flux is obtained by integrating the angular neutron flux over all directions:

$$
\phi(\vec{r}, E, t) = \int_{4\pi} d\Omega \, \phi(\vec{r}, \vec{\Omega}, E, t).
$$

> (1.3)

Because $\phi(\vec{r}, E, t)$ still depends on the energy $E$, it represents the energy-dependent neutron flux, also referred to as the neutron spectrum. By integrating the neutron spectrum over energy, the total neutron flux can be obtained as

$$
\phi(\vec{r}, t) = \int dE \, \phi(\vec{r}, E, t).
$$

> (1.4)
