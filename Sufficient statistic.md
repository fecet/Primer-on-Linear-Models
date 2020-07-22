A statistic forms a **partition** of $\mathcal{X}$, that is 

$$ A _ { t } = \{ \mathrm { x } \in \mathcal { X } : T ( \mathrm { x } ) = t \} $$

A statistic $T(\mathbf{X})$ is sufficient iff 

$$ f _ { \mathbf { X } \mid T } ( \mathbf { x } \mid t ) = \frac { f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) } { f _ { T } ( t \mid \theta ) } $$

is free of $\theta$

> A statistic $T(\mathbf{X})$ is sufficient iff $$ f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) = g ( t \mid \theta ) h ( \mathbf { x } ) $$

### Exponential family

Suppose $X_{1:n}$ are iid from the exponential family

$$ f _ { X } ( x \mid \boldsymbol { \theta } ) = h ( x ) c ( \boldsymbol { \theta } ) \exp \left\{ \sum _ { i = 1 } ^ { k } w _ { i } ( \boldsymbol { \theta } ) t _ { i } ( x ) \right\} $$

Then

$$ T=T(\mathbf{X})= \left( \sum _ { j = 1 } ^ { n } t _ { 1 } \left( X _ { j } \right) , \sum _ { j = 1 } ^ { n } t _ { 2 } \left( X _ { j } \right) , \ldots , \sum _ { j = 1 } ^ { n } t _ { k } \left( X _ { j } \right) \right)$$

is sufficient.

**Proof**
$$ f _ { \mathbf { X } } ( \mathbf { x } \mid \boldsymbol { \theta } ) = \prod _ { j = 1 } ^ { n } h \left( x _ { j } \right) c ( \boldsymbol { \theta } ) \exp \left\{ \sum _ { i = 1 } ^ { k } w _ { i } ( \boldsymbol { \theta } ) t _ { i } \left( x _ { j } \right) \right\} $$

where


$$ \underbrace{ \prod _ { j = 1 } ^ { n } h \left( x _ { j } \right)}_{h(x)} \underbrace{[ c ( \boldsymbol { \theta } ) ] ^ { n } \exp \left\{ \sum _ { i = 1 } ^ { k } w _ { i } ( \boldsymbol { \theta } ) \sum _ { j = 1 } ^ { n } t _ { i } \left( x _ { j } \right) \right\}}_{g(\mathbf{t|\theta})} $$

### Minimal sufficient statistic

A sufficient statistic $T(\mathbf{X})$ is called as **minimal sufficient statistic** iff for any other sufficient statistic $T'(\mathbf{X})$, $T(\mathbf{x})$ is a function of $T'(\mathbf{x})$, that is 

$$ T ' ( \mathbf { x } ) = T'( \mathbf { y } ) \Longrightarrow T ( \mathbf { x } ) = T ( \mathbf { y } ) $$










Suppose $\mathbf{X}\sim f_\mathbf{X}(\mathbf{X}|\theta)$, there is a statistic satisfy $\forall \mathbf{x,y}\in \mathcal{X}$:

$$ \frac { f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) } { f _ { \mathbf { X } } ( \mathbf { y } \mid \theta ) } \text { is free of } \theta \Longleftrightarrow T ( \mathbf { x } ) = T ( \mathbf { y } ) $$

Then $T(\mathbf{X})$ is a minimal sufficient statistic.

**Proof** 
1. We first prove that  $\frac { f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) } { f _ { \mathbf { X } } ( \mathbf { y } \mid \theta ) } \text { is free of } \theta \impliedby T ( \mathbf { x } ) = T ( \mathbf { y } )$, iff $T(\mathbf{X})$ is a sufficient statistic. Consider the partition $A_t$, for each $A_t$, take $X_t$ as a fixed element, that implies $X_t$ is some function of $t$. Then $$ f(\mathbf{x}|\theta)=\frac{f(\mathbf{x}_t|\theta)f(\mathbf{x}|\theta)}{f(\mathbf{x}_t|\theta)}=g(t|\theta)h(\mathbf{x}) $$ since $\frac{f(\mathbf{x}|\theta)}{f(\mathbf{x}_t|\theta)}=h(\mathbf{x})$ is free of $\theta$. For the necessity part, note $$ \frac{f(\mathbf{x}|\theta)}{f(\mathbf{y}|\theta)}=\frac{g(t|\theta)h(\mathbf{x})}{g(t|\theta)h(\mathbf{y})} = \frac{h(\mathbf{x})}{h(\mathbf{y})}$$ is free of $\theta$.

2. Then we prove the sufficiency (plus) implies minimal sufficient statistic. For any sufficient $T'(\mathbf{X})$, we have $$ T'(\mathbf{x})=T'(\mathbf{y})\implies\frac { f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) } { f _ { \mathbf { X } } ( \mathbf { y } \mid \theta ) } \text { is free of } \theta \implies T(\mathbf{x})=T(\mathbf{y}) $$ hence $T(\mathbf{X})$ is minimal sufficient statistic. $\quad \blacksquare$

## Ancilary statistic

A statistic $S=S(\mathbf{X})$ is an ancillary statistic if the distribution of $S$ doesn't depend on $\theta$

For any $c\in \Reals$, if $S$ satisfies $\forall \mathbf{x}\in \mathcal{X}$

$$ S(\mathbf{x+1c})=S(\mathbf{x}) $$

Then $S$ is called a **location-invariant statistic**, similarly if

$$ S(c\mathbf{x})=S(\mathbf{x}) $$

is called **scale-invariant statistic**.

Then we have, if $X_{1:n}$ are iid from a scale family, then $S$ is ancillary if it's scale invariant and should be location invariant for a location family.

## Complete statistic

A statistic is a complete statistic iff

$$ \forall \theta \in \Theta \ni E_\theta[g(T)]=0 \implies \forall\theta \in \Theta \ni P_\theta(g(T)=0)=1$$

If a sufficent statistic is complete, it's minimal.

> **Basu's Theorem** Suppose $T$ is sufficient statistic, if $T$ is also complete, then $T$ is independent of every ancilary statistic.

**Proof** Suppose $S$ is ancillary, $\phi$ and $\psi$ are arbitrary functions of $S$ and $T$:

$$ \begin{aligned} E _ { \theta } [ \phi ( S ) \psi ( T ) ] & = E _ { \theta } \{ E [ \phi ( S ) \psi ( T ) \mid T ] \} \\ & = E _ { \theta } \{ \psi ( T ) E [ \phi ( S ) \mid T ] \} \end{aligned} $$

Define

$$ g(T)=E[\phi(S)\mid T]- E_\theta[\phi(S)]$$

since $S$ is ancillary:

$$ E _ { \theta } [ g ( T ) ] = E _ { \theta } \{ E [ \phi ( S ) \mid T ] - E_\theta[\phi(S)] \} = E_\theta[\phi(S)]-E_\theta[\phi(S)]=0 $$

hence $g(T)\overset{a.s.}{=}0 \iff E_\theta[\phi(S)]\overset{a.s.}{=}E[\phi(S)\mid T]$, hence

$$ E _ { \theta } [ \phi ( S ) \psi ( T ) ] = E_\theta[\phi(S)]E_\theta[\psi(T)] $$

Take $\phi(S)=I(S\le s)$ and $\psi(T)=I(T\le t)$, then we have

$$ F_{T,S}(t,s)=F_S(s)F_T(t)\quad \blacksquare $$

### Completeness in exponential family

In a exponential family, the statisic 

$$ T=T(\mathbf{X})= \left( \sum _ { j = 1 } ^ { n } t _ { 1 } \left( X _ { j } \right) , \sum _ { j = 1 } ^ { n } t _ { 2 } \left( X _ { j } \right) , \ldots , \sum _ { j = 1 } ^ { n } t _ { k } \left( X _ { j } \right) \right)$$

is complete if the dimension $d=k$.

















<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>