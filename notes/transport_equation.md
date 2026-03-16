
## 1 Derivation of the Neutron Transport Equation

### 1.1 Representation of Neutrons

The number of neutrons located at time $t$, within a spatial volume $dV$ around position $\vec{r}$, traveling in directions within a solid angle $d\Omega$ around $\vec{\Omega}$, and having energies within an interval $dE$ around energy $E$, can be expressed as

$$
N(\vec{r}, \vec{\Omega}, E, t)dVd\Omega dE
$$

> (1.1)

where $N(\vec{r}, \vec{\Omega}, E, t)$ is the neutron density with energy $E$ traveling in direction $\vec{\Omega}$ at position $\vec{r}$ and time $t$.

In reactor physics, the number of neutrons passing through a unit area per unit time is an important quantity. Therefore, the neutron flux $\phi$ is commonly used, which is defined by multiplying the neutron density by the neutron speed $v$. The neutron flux can be written as

$$
\phi(\vec{r}, \vec{\Omega}, E, t) = vN(\vec{r}, \vec{\Omega}, E, t).
$$

> (1.2)

Since $\phi(\vec{r}, \vec{\Omega}, E, t)$ depends on the direction $\vec{\Omega}$, it is referred to as the angular neutron flux.

The scalar neutron flux is obtained by integrating the angular neutron flux over all directions:

$$
\phi(\vec{r}, E, t) = \int_{4\pi} d\Omega\phi(\vec{r}, \vec{\Omega}, E, t).
$$

> (1.3)

Because $\phi(\vec{r}, E, t)$ still depends on the energy $E$, it represents the energy-dependent neutron flux, also referred to as the neutron spectrum. By integrating the scalar flux over energy, the total neutron flux can be obtained as

$$
\phi(\vec{r}, t) = \int dE \phi(\vec{r}, E, t).
$$

> (1.4)



### 1.2 Neutron Balance

Consider the neutron balance within a differential volume during the time interval between $t$ and $t+\Delta t$.

A neutron located at time $t$ within a spatial volume $dV$ around position $\vec{r}$, traveling in directions within a solid angle $d\Omega$ around $\vec{\Omega}$, and having energy within an interval $dE$ around $E$, will move during the time interval $\Delta t$ to a new position

$$
\vec{r}' = \vec{r} + v \Delta t \vec{\Omega}
$$

while remaining within the same directional and energy intervals.

> (1.5)

Therefore, the number of neutrons located at $\vec{r}'$ at time $t+\Delta t$ consists of the following four contributions:

1. Neutrons that were located at $\vec{r}$ at time $t$ and reach $\vec{r}'$ at $t+\Delta t$ without interaction.
2. Neutrons produced by scattering events occurring between $\vec{r}$ and $\vec{r}'$ during the interval $t \sim t+\Delta t$.
3. Neutrons produced by fission events occurring between $\vec{r}$ and $\vec{r}'$ during the interval $t \sim t+\Delta t$.
4. Neutrons produced by external neutron sources located between $\vec{r}$ and $\vec{r}'$.

---

### 1.2.1 Collision Contribution

The probability that a neutron experiences a collision while traveling from $\vec{r}$ to $\vec{r}'$ is

$$
\Sigma_t(\vec{r}'',E,t) v \Delta t
$$

where

$$
\vec{r}'' = \vec{r}' - \vec{r}.
$$

> (1.6)

Therefore, the contribution of neutrons that reach $\vec{r}'$ without collision is

$$
N(\vec{r},\vec{\Omega},E,t)
\left(
1 - \Sigma_t(\vec{r}'',E,t) v \Delta t
\right)
dV d\Omega dE
$$

> (1.7)

where $\Sigma_t$ is the macroscopic total cross section.
The macroscopic cross section may depend on position, energy, and time, but it is assumed to be independent of the neutron flight direction.

---

### 1.2.2 Scattering Contribution

The contribution from neutrons scattered at time $t'$ from position $\vec{r}''$, direction $\vec{\Omega}'$, and energy $E'$ is

$$
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t')
dV' d\Omega' dE'
\Sigma_s(\vec{r}'',\vec{\Omega}' \rightarrow \vec{\Omega},E' \rightarrow E,t')
d\Omega dE
$$

> (1.8)

where $\Sigma_s$ is the macroscopic scattering cross section.

The total contribution from all incoming directions and energies becomes

$$
\int d\Omega'
\int dE'
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t')
dV'
\Sigma_s(\vec{r}'',\vec{\Omega}' \rightarrow \vec{\Omega},E' \rightarrow E,t')
d\Omega dE
$$

> (1.9)

---

### 1.2.3 Fission Contribution

The contribution from neutrons produced by fission at time $t'$ from position $\vec{r}''$, direction $\vec{\Omega}'$, and energy $E'$ is

$$
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t')
dV' d\Omega' dE'
\nu \Sigma_f(\vec{r}'',\vec{\Omega}',E',t')
d\Omega dE
\chi(E)
$$

> (1.10)

where

- $\nu$ is the average number of neutrons produced per fission,
- $\Sigma_f$ is the macroscopic fission cross section,
- $\chi(E)$ is the fission neutron spectrum.

If fission neutrons are emitted isotropically, the following relation holds:

$$
\Sigma_f(\vec{r}'',E',t')=\frac{1}{4\pi}\int d\Omega \,\Sigma_f(\vec{r}'',\vec{\Omega}',E',t')
$$

> (1.11)

Thus, the fission contribution becomes

$$
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t')
dV'
\frac{\nu \Sigma_f(\vec{r}'',E',t')}{4\pi}
\chi(E)
d\Omega dE
$$

> (1.12)

The total contribution from all directions and energies is

$$
\int d\Omega'
\int dE'
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t')
dV'
\frac{\nu \Sigma_f(\vec{r}'',E',t')}{4\pi}
\chi(E)
d\Omega dE
$$

> (1.13)

---

### 1.2.4 External Source Contribution

The contribution from an external neutron source during the time interval $\Delta t$ is

$$
\Delta t
S(\vec{r}',\vec{\Omega},E,t)
dV d\Omega dE
$$

> (1.14)

where $S$ denotes the number of neutrons produced per unit time by an external source.


### 1.3 Time-Dependent Neutron Transport Equation

From the collision contribution in Eq. (1.7), the scattering contribution in Eq. (1.9), the fission contribution in Eq. (1.12), and the external source contribution in Eq. (1.14), the number of neutrons at time $t+\Delta t$ within the spatial volume $dV$ around $\vec{r}+v\Delta t \vec{\Omega}$, traveling in directions within the solid angle $d\Omega$ around $\vec{\Omega}$, and having energies within the interval $dE$ around $E$ can be written as

$$
\begin{aligned}
&N(\vec{r}+v\Delta t\vec{\Omega},\vec{\Omega},E,t+\Delta t)dV d\Omega dE \\
&= N(\vec{r},\vec{\Omega},E,t)
\left(
1-\Sigma_t(\vec{r}'',E,t)v\Delta t
\right)
dV d\Omega dE \\
&+ \int d\Omega' \int dE'
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t)
dV'
\Sigma_s(\vec{r}'',\vec{\Omega}' \rightarrow \vec{\Omega},E' \rightarrow E,t)
d\Omega dE \\
&+ \int d\Omega' \int dE'
v' \Delta t
N(\vec{r}'',\vec{\Omega}',E',t)
dV'
\frac{\nu \Sigma_f(\vec{r}'',E',t)}{4\pi}
\chi(E)
d\Omega dE \\
&+ \Delta t
S(\vec{r}',\vec{\Omega},E,t)
dV d\Omega dE .
\end{aligned}
$$

> (1.15)

When $\Delta t \rightarrow 0$, we have

$$
\vec{r}=\vec{r}'=\vec{r}'', \quad dV=dV', \quad t'=t .
$$

Thus Eq. (1.15) can be rewritten as

$$
\begin{aligned}
\frac{
N(\vec{r}+v\Delta t\vec{\Omega},\vec{\Omega},E,t+\Delta t)-
N(\vec{r},\vec{\Omega},E,t)
}{\Delta t}
&+
v N(\vec{r},\vec{\Omega},E,t)\Sigma_t(\vec{r},E,t) \\
&=
\int d\Omega' \int dE'
v' N(\vec{r},\vec{\Omega}',E',t)
\Sigma_s(\vec{r},\vec{\Omega}' \rightarrow \vec{\Omega},E' \rightarrow E,t) \\
&+
\chi(E)
\int d\Omega' \int dE'
v' N(\vec{r},\vec{\Omega}',E',t)
\frac{\nu \Sigma_f(\vec{r},E',t)}{4\pi}.
\end{aligned}
$$

> (1.16)

Using the neutron flux

$$
\phi(\vec{r},\vec{\Omega},E,t)=vN(\vec{r},\vec{\Omega},E,t),
$$

Eq. (1.16) becomes

$$
\begin{aligned}\frac{
N(\vec{r}+v\Delta t\vec{\Omega},\vec{\Omega},E,t+\Delta t)-N(\vec{r},\vec{\Omega},E,t)}{\Delta t}
&+
\phi(\vec{r},\vec{\Omega},E,t)
\Sigma_t(\vec{r},E,t) \\
&=
\int d\Omega' \int dE'
\phi(\vec{r},\vec{\Omega}',E',t)
\Sigma_s(\vec{r},\vec{\Omega}' \rightarrow \vec{\Omega},E' \rightarrow E,t) \\
&+
\chi(E)
\int d\Omega' \int dE'
\phi(\vec{r},\vec{\Omega}',E',t)
\frac{\nu \Sigma_f(\vec{r},E',t)}{4\pi} \\
&+
S(\vec{r},\vec{\Omega},E,t).
\end{aligned}
$$

> (1.17)

For $\Delta t \rightarrow 0$, the first term on the left-hand side becomes

$$
\frac{N(\vec{r}+v\Delta t\vec{\Omega},\vec{\Omega},E,t+\Delta t)
-
N(\vec{r},\vec{\Omega},E,t)
}{\Delta t}
=
\vec{\Omega}\cdot\nabla
\phi(\vec{r},\vec{\Omega},E,t)
+
\frac{1}{v}
\frac{\partial
\phi(\vec{r},\vec{\Omega},E,t)
}{\partial t}.
$$

> (1.18)

Substituting Eq. (1.18) into Eq. (1.17), the **time-dependent neutron transport equation** is obtained:

$$
\begin{aligned}
\vec{\Omega}\cdot\nabla
\phi(\vec{r},\vec{\Omega},E,t)
+
\frac{1}{v}
\frac{\partial
\phi(\vec{r},\vec{\Omega},E,t)
}{\partial t}
+
\Sigma_t(\vec{r},E,t)
\phi(\vec{r},\vec{\Omega},E,t)
&=
\int d\Omega' \int dE'
\phi(\vec{r},\vec{\Omega}',E',t)
\Sigma_s(\vec{r},\vec{\Omega}' \rightarrow \vec{\Omega},E' \rightarrow E,t) \\
&+
\chi(E)
\int d\Omega' \int dE'
\phi(\vec{r},\vec{\Omega}',E',t)
\frac{\nu \Sigma_f(\vec{r},E',t)}{4\pi} \\
&+
S(\vec{r},\vec{\Omega},E,t).
\end{aligned}
$$

> (1.19)
>
