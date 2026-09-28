<!-- omit in toc -->
# Solutions to Quiz 01

*Last updated 28 September 2026*

- [Part I](#part-i)
  - [Scenario 01](#scenario-01)
  - [Scenario 02](#scenario-02)
  - [Scenario 03](#scenario-03)
- [Part II](#part-ii)
  - [Scenario 04](#scenario-04)
  - [Scenario 05](#scenario-05)
  - [Scenario 06](#scenario-06)

For the computations,
see [`oqz-01-soln.ipynb`](./oqz-01-soln.ipynb).

## Part I

Balancing forces at $E$,

$$2T = m_{c} g \Longrightarrow T = \frac{m_{c} g}{2}$$

For convenience,
yet without loss of generality,
assume that

- $R_{A}$ only has a rightward component $A_{x}$,
  and
- $R_{O}$ has a leftward component $O_{x}$ and an upward component $O_{y}$.

Balancing moments about $O$,

$$T \left(\frac{2L}{3} \right) \sin 60 + A_{x} \left(L\right) \sin 30  = m_{b} g \left(\frac{L}{2}\right) \sin 60$$

Balancing horizontal forces acting on the bar,

$$A_{x} + T \cos 30 = O_{x}$$

Balancing vertical forces acting on the bar,

$$T \sin 30 + O_{y} = m_{b} g$$

The above four equations encode the static equilibrium conditions for the cylinder-cable-pulley-bar system.
The latter three pertains to the bar.
Scenarios 1 - 3 are solved by judicious analyses of these equilibrium equations.

Because of our direction assumptions,
$R_{A} = \langle A_{x}, 0 \rangle$
and
$R_{O} = \langle -O_{x}, O_{y} \rangle$.

### Scenario 01

The bar is not a three-force member under the given conditions.

### Scenario 02

The limiting condition is when the bar no longer rests on the wall,
*i.e.*, $R_{A}$ is zero.
From the moment-balance equation about $O$,
this occurs when $m_{c} = 0.5 m_{b}$.

In this particular setting,
where rotation about the hinge does not occur yet,
the bar is a three-force member.

### Scenario 03

This is similar to Scenario 2,
but with the additional checking for when $T$ reaches the limit $\overline{T}$.
In other words, there are two candidates for the maximum allowable values:

1. $0.5 m_{b}$, based solely on impending rotation about $O$,
  and
2. $\frac{2 \overline{T}}{g}$, based solely on cable limit.

The lesser of these two is the maximum allowable value of $m_{c}$.

## Part II

Concerning stability and determinacy,
see
https://engineeringstatics.org/Chapter_05-stability-and-determinacy.html.

### Scenario 04

The roof truss, under the given loading,
is statically determinate and stable.

We can safely assume that

- $R_{F}$ only has an upward component $F_{y}$,
  and
- $R_{A}$ has a leftward component $A_{x}$ and an upward component $A_{y}$,

whence
$R_{F} = \langle 0, F_{y} \rangle$
and
$R_{A} = \langle -A_{x}, A_{y} \rangle$.

Balancing moments about $A$,

$$10 F_{y} = 500 \left(7.5\right) + 500 \left(5\right) + 500 \left(2.5\right) + 500 \left(2.5\right)$$

Balancing horizontal forces acting on the truss,

$$A_{x} = 400 \cos 30$$

Balancing vertical forces acting on the truss,

$$A_{y} + F_{y} = 250 + 400 \sin 30 + 500 + 500 + 500 + 250$$

### Scenario 05

Note well that what is asked to find an force-couple equivalent of
are the applied loads *only*,
and so the support reactions are not needed.

By inspection,
$R$ will have a rightward component $R_{x}$ and a downward component $R_{y}$,
so that
$R = \langle R_{x}, -R_{y} \rangle$.
Computing these components should be elementary:

$$R_{x} = 400 \cos 30$$
$$R_{y} = 250 + 400 \sin 30 + 500 + 500 + 500 + 250$$

Obviously,
$C_{G} = \langle 0, 0, C \rangle$,
where $C$ is the resultant moment
of the applied loads about $G$,
obtained by Varignon's theorem:

$$500 \left(2.5\right) + 250 \left(5\right) + 400 \left(0\right) + 500 \left(0\right) - 500 \left(2.5\right) - 250 \left(5\right)$$

### Scenario 06

The roof truss, under the modified loading,
is still statically determinate.

Solving for $R_{F}$ and $R_{A}$ is similar to that of Scenario 04,
we just need to negate every appearance of the 400-N force.

Checking for stability under the modified loading is now more involved.
Observe that the truss model allows rotation about $A$,
at the cusp of which event
$F_{y}$ is no longer positive
as the roller starts to lose contact.
The computed value $F_{y}$ is positive,
so the truss is still stable under the modified loading.
