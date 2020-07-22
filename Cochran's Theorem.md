# Cochran's Theorem

To introduce **Cochran's Theorem**, discuss the following result firstly:

> If $\mathbf{A}_{1:k}$ is $n\times n$ symmetricand $\sum \mathbf{A_i=I_n}$, then the following statements are equivalent:
> 1. $A_i$ are idempotent
> 2. $\sum rank(\mathbf{A_i})=n$
> 3. $\forall i\neq j \ni \mathbf{A_iA_j=0}$

**Proof** $1\implies 2$ since $n=tr(\mathbf{I_n})=tr(\sum\mathbf{\mathbf{A_i}})=\sum tr(\mathbf{A_i})=\sum rank(\mathbf{A_i})$.
To show $1\implies 3$, recall that an symmetric idempotent matrix $\mathbf{A}$ can be written as $\mathbf{QQ'}$ where $\mathbf{Q'Q=I}_{rank(\mathbf{A})}$. Then cosider 

$$ \mathbf { Q } = \left[ \begin{array} { l l l } \mathbf { Q } _ { 1 } & \mathbf { Q } _ { 2 } & \ldots & \mathbf { Q } _ { k } \end{array} \right] $$

It's square since statement 2, then

$$ \mathbf{I_n}=\sum \mathbf{A_i}=\sum \mathbf{Q_i Q_i'}=\mathbf{QQ'} $$

hence $\mathbf{Q}$ is an orthogonal matrix, then

$$ \mathbf { Q } ^ { T } \mathbf { Q } = \left[ \begin{array} { l } \mathbf { Q } _ { 1 } ^ { T } \\ \mathbf { Q } _ { 2 } ^ { T } \\ \ldots \\ \mathbf { Q } _ { k } ^ { T } \end{array} \right] \left[ \mathbf { Q } _ { 1 } \mathbf { Q } _ { 2 } \ldots \mathbf { Q } _ { k } \right] = \mathbf { I } _ { N } = \left[ \begin{array} { c c c c } \mathbf { I } _ { r _ { 1 } } & \mathbf { 0 } & \mathbf { 0 } & \mathbf { 0 } \\ \mathbf { 0 } & \mathbf { I } _ { r _ { 2 } } & \mathbf { 0 } & \mathbf { 0 } \\ \ldots & \ldots & \ldots & \ldots \\ \mathbf { 0 } & \mathbf { 0 } & \mathbf { 0 } & \mathbf { I } _ { r _ { k } } \end{array} \right] $$

where $\mathbf{Q_i'Q_j}$ should be $\mathbf{0}$, Thus $\mathbf{A_iA_j}=\mathbf{Q_iQ_i'Q_jQ_j'=0}$.

$3\implies 1$ since $\mathbf{A_i}=\mathbf{A_iI}=\mathbf{A_i\sum A_j}=\mathbf{A_i^2}$. $\quad \blacksquare$

Hence we have Cochran's Theorem:

> Suppose $\mathbf{X}\sim N(\mu,\sigma^2\mathbf{I})$ and $A_{1:k}$ be symmetric idempotent $n\times n$ matrices and $\sum \mathbf{A_i}=\mathbf{I_n}$, then
> $$ \mathbf{X'X}=\sum \mathbf{X'A_i X}$$
> where $\frac{\mathbf{X'A_iX}}{\sigma^2}\sim\chi_{rank(A_i)}^2(\frac{\mu'\mathbf{A_i}\mu}{2\sigma^2})$ and each $\frac{\mathbf{X'A_iX}}{\sigma^2}$ are independent.

## Application in linear model

Consider GM model $\mathbf{y=Xb+e}$, additionaly assume that $\mathbf{e}\sim N(0,\sigma^2\mathbf{I})$. We partition the design matrix and parameter into $k+1$ parts:

$$ \mathbf { y } = \left( \mathbf { X } _ { 0 } \mathbf { X } _ { 1 } \ldots \mathbf { X } _ { k } \right) \left( \begin{array} { c } \mathbf{b} _ { 0 } \\ \mathbf{b} _ { 1 } \\ \vdots \\ \mathbf{b} _ { k }  \end{array} \right) $$

Then we add a new part into submodel start from $\mathbf{y=X_0b_0+e}$ each time, that is $\mathbf{y=X}_i^*\mathbf{b}_i^*+\mathbf{e}$ where $\mathbf{X}_{i+1}^*=[\mathbf{X}_i^*\quad \mathbf{X}_{i+1}]$ and $\mathbf{X}_0^*=\mathbf{X}_0$

Then we have

$$ \mathbf{y'y}=\sum_{i=0}^{k+1}\mathbf{y'A}_i\mathbf{y} $$ where 

$$ \begin{aligned} \mathbf { A } _ { 0 } & = \mathbf { P } _ { \mathbf { X } _ { 0 } ^ { * } } \\ \mathbf { A } _ { i } & = \mathbf { P } _ { \mathbf { X } _ { i } ^ { * } } - \mathbf { P } _ { \mathbf { X } _ { i - 1 } ^ { * } } i = 1,2 , \ldots , k - 1 \\ \mathbf { A } _ { k } & = \mathbf { P } _ { \mathbf { X } } - \mathbf { P } _ { \mathbf { X } _ { k - 1 } ^ { * } } \\ \mathbf { A } _ { k + 1 } & = \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \end{aligned} $$

It's easy to check that $\sum_{i=0}^{k+1}\mathbf{A}_i=\mathbf{I}$ and each of $\mathbf{A}_i$ is symmetric and idempotent.

Apply Cochran's theorem, we have

$$ \frac{\mathbf{y'A_iy}}{\sigma^2}\sim \chi_{r_i}^2(\frac{\mathbf{(Xb)'A_i(Xb)}}{2\sigma^2}) $$

Take $\mathbf{X_0=1}$ and $k=1$, then

$$ \begin{array} { l } \mathbf { A } _ { 0 } = \mathbf { P_1 } \\ \mathbf { A } _ { 1 } = \mathbf { P } _ { \mathbf { X } } - \mathbf { P } _ { \mathbf { 1 } } \\ \mathbf { A } _ { 2 } = \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \end{array} $$

Hence we have

$$ F = \frac { \mathbf { y } ^ { \prime } \left( \mathbf { P } _ { \mathbf { X } } - \mathbf { P } _ { \mathbf { 1 } } \right) \mathbf { y } / ( r - 1 ) } { \mathbf { y } ^ { \prime } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { y } / ( n - r ) } \sim F _ { r - 1 , n - r } \left( \frac{\mathbf{(Xb)'(P_X-P_1)(Xb)}}{2\sigma^2}  \right) $$

Which is the usual F statistic to test $H_0:\mathbf{b_1=0}$. If $H_0$ is true, the noncentrality is $0$ since $\mathbf{Xb}=\mathbf{1b}\in \mathcal{C}(\mathbf{1})$ and $\mathcal{C}(\mathbf{1})\sub \mathcal{C}(\mathbf{X})$.

















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