# Week One

## the ab initio way
It means to describe the experiment results from the mathematics way, formulating a equation.

In the macro world, Newton laws are these equations, while quantum mechanics dominates in the micro world. Thus, both of them can be called the ab initio way.

## What is solid?
Solid is the combination of electrons and nuclei, the motion of which both obey the quantum mechanics.

**If we can solve the Schrödinger equation of the solid,we can get any properties of it. this is the ab initio solid physics.**

## What is the problem?
Physics can be divided into these:

- The axioms are known and the equations can be solved.

  *e.g.* classical mechanics, classical eletromagnetism, thermodynamics,......

- The axioms are known, but the equations cannot be solved

  *e.g.* condensed matter physics, materials science, chemistry

- The axioms are not known

  *e.g.* nuclear physics

## Mathematics concept
- Function:$\mathbb{C} \Rightarrow  \mathbb{C}$
- Functionals:$\mathcal{F}[f] \Rightarrow \mathbb{C}$ 

## Schrödinger equation of the Hydrogen atom

$$
\begin{aligned}
\\
\hat{\mathcal{H}}\Psi =& E\Psi
\\
\hat{\mathcal{H}}=& \sum_{A}-\frac{\hbar^{2} \nabla_{\vec{R}_{A}}^{2}}{2 M_{A}} \\
&+\sum_{i}-\frac{\hbar^{2} \nabla_{\vec{r}_{i}}^{2}}{2 m_{i}} \\
&+\frac{1}{2} \frac{1}{4 \pi \epsilon_{0}} \sum_{A \neq B} \frac{+e^{2} Z_{A} Z_{B}}{\left|\vec{R}_{A}-\vec{R}_{B}\right|} \\
&+\frac{1}{2} \frac{1}{4 \pi \epsilon_{0}} \sum_{i \neq j} \frac{e^{2}}{\left|\vec{r}_{i}-\vec{r}_{j}\right|} \\
&+\frac{1}{4 \pi \epsilon_{0}} \sum_{i, A} \frac{-e^{2} Z_{A}}{\left|\vec{r}_{i}-\vec{R}_{A}\right|}
\end{aligned}
$$

**Noted: the wave function $\Psi$ is antisymmetric, which can be expressed in mathematics way.**

$$\Psi(\vec{r_1}, {\bar{ \sigma _1 }}, \vec{r_2}, \bar{ \sigma _2 }) = -\Psi(\vec{r_2}, {\bar{ \sigma _2 }}, \vec{r_1}, \bar{ \sigma _1 })$$

## Aproximation of Schrödinger equation.

``` dot
digraph G {
	node[shape="box"]
	"Schrödinger equation" -> "Born-Oppenheimer approximation" -> {"Hartree-Fock", "DFT"} -> "solution techniques" -> prediction
}
```

## (Post-) Hartree-Fock methods
A way to try to solve the many bodies Schrödinger equation and get the ground state energy.

**Noted: the exact ground state energy is out of the Slater determinants.**

The HF algorithm is to find the nearest point around the ground state point.
``` mermaid
flowchart TB
	subgraph "space of all possible wave functions"
		subgraph "all antisymmetric ones"
			subgraph "all Slater determinants"
			end
			A["exact ground state"]
		end
	end
```

## the Density Function Theory
### External Potential
The system can be described by: 
- number of the electrons
- position of the nuclei 
Actually, the last item of the operator $\hat{\mathcal{H}}$ contains the both information.
$$ +\frac{1}{4 \pi \epsilon_{0}} \sum_{i, A} \frac{-e^{2} Z_{A}}{\left|\vec{r}_{i}-\vec{R}_{A}\right|}$$

This item is also called external potential($V_{ext}(\vec{v})$), which is **"energy of N electrons in the electric potential provided by a given set of nuclei at $\bar{R_A}$"**

### Electron Density
The electron density operator for one electron: 
$$ \hat{\rho}(\vec{r}) = \delta(\vec{r^{\prime}}-\vec{r})$$

The electron density for one electron: 

$$
\begin{aligned}
    \rho(\vec{r}) &= \langle\Psi|\vec{\hat{\rho}}(\vec{r})|\Psi\rangle \\
    &= \int{\Psi^{\star}(\vec{r^{\prime}})\Psi(\vec{r^{\prime}})\delta(\vec{r^{\prime}}-\vec{r})d\vec{r^{\prime}}} \\
    &= \Psi^{\star}(\vec{r^{\prime}})\Psi(\vec{r}) \\
    &= {\lvert\Psi(\vec{r})\rvert}^2
\end{aligned}
$$

Tranlate to English: probability to find the electron at $\vec{r}$, regardless where the other (N-1) electrons are.

### First Hohenberg-Kohn theorem

It shows that the electron density uniquely determines the Hamilton operator and thus all properties of the system.

