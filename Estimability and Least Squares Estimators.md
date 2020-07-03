# Estimability and Least Squares Estimators

## Assumptions for the Linear Mean Model

For the linear model $$ \mathbf{y=Xb+e} $$ We now assume that the error have zero mean: $$ E\mathbf{e}=0 $$ Such Assumption is also equivalent to assume $E(\mathbf{y})=\mathbf{Xb}$

## Estimator and Estimability

**Definition**:

1. An estimator $t(\mathbf{y})$ is **unbiased** for $\lambda^T \mathbf{b}$ iff $E ( t ( \mathbf { y } ) ) = \lambda ^ { T } \mathbf { b }$ for all $\mathbf{b}$.
2. An estimator $t(\mathbf{y})$ is **linear** iff $t(\mathbf{y})=c+\mathbf{a}^Ty$ for some $c$ and $\mathbf{a}^T$.
3. $\lambda^T \mathbf{b}$ is linearly **estimable** iff there exists a linear unbiased estimator for it, otherwise the function is called **nonestimabel**.

The following statements are equivalent:

1. $\lambda^T \mathbf{b}$ is linearly estimable.
There exists a vector $\mathbf{a}$ s.t. 
2. $E(\mathbf{a}^T\mathbf{y})=\lambda^T\mathbf{b}$
3. $\lambda^T=\mathbf{a^TX}$
4. $\lambda=\mathbf{X^Ta}$

We can prove this follow: $4\to 2 \to 1$ and $1\to 3\to 4$.

Thus when $\lambda \in \mathcal{C}\mathbf(X^T)$, $\lambda^T \mathcal{b}$ is estimable. That is, if $\mathbf{X}$ has full column rank, all of components of $\mathbf{b}$ are estimable.

1. $\lambda^T\mathbf{b}$ is estimable $\iff \lambda^T\mathbf{\hat{b}}$ are free of the choice of $\mathbf{\hat{b}}$
2. $\lambda^T \mathbf{\hat{b}}$ is a linear unbiased estimator of $\lambda^T\mathbf{b}$

## Reparameterization Revisited

Suppose $\mathbf{W}$ and $\mathbf{X}$ are equivalent with $\mathbf{W=XT}$ and $\mathbf{X=WS}$.

1. If $\lambda^T\mathbf{b}$ is estimable in $\mathbf{X}$ and $\mathbf{\hat{c}}$ solves the NEs in $\mathbf{W}$, then $\lambda^T(\mathbf{T\hat{c}})$ is the least squares estimator of $\lambda^T \mathbf{b}$ since $\lambda ^ { T } \hat { \mathbf { b } } = \lambda ^ { T } \mathbf { T } \hat { \mathbf { c } }$.
2. If $\mathbf{q}^T\mathbf{c}$ is estimable in $\mathbf{W}$  and $\mathbf{\hat{c}}$ solves the NEs in $\mathbf{W}$, then $\mathbf{q}^T\mathbf{Sb}$ is estimable in $\mathbf{X}$ and $\mathbf{q}^T\mathbf{\hat{c}}$ is its least squares estimator.


We often choose $\mathbf{W}$ to be full-column rank so that the solution to the NEs is unique and any components of $\mathbf{c}$ is estimable. Another important advantage is interpretation of the new parameters will be more clear or make $\mathbf{W}^T\mathbf{W}$ diagonal or block diagonal.

## Conditions for a Unique Solution

Suppose we impose a condition on the solution to NEs: $$ \mathbf{CB=0} $$now the NEs become:$$ \left[ \begin{array} { c } \mathbf { X } ^ { T } \mathbf { X } \\ \mathbf { C } \end{array} \right] \mathbf { b } = \left[ \begin{array} { c } \mathbf { X } ^ { T } \mathbf { y } \\ \mathbf { 0 } \end{array} \right] $$where $\mathbf{X}$ is $N\times p$, $r=rank(\mathbf{X})$ and $\mathbf{C}$ is $s\times p$, $s=p-r$, $rank(\mathbf{C})=s$(so that we may have a unique solution). To achieve this purpose, below equation should be hold:$$ \mathcal { C } \left( \left[ \mathbf { X } ^ { T } \quad \mathbf { C } ^ { T } \right] \right) = R ^ { p } $$ Thus have $$ \mathcal { C } \left( \mathbf { X } ^ { T } \right) \cap \mathcal { C } \left( \mathbf { C } ^ { T } \right) = \{ \mathbf { 0 } \} $$ And the system of equations above is equivalent to $$ \left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) \mathbf { b } = \mathbf { X } ^ { T } \mathbf { y } $$ since $\mathbf { C } ^ { T } \mathbf { C b } = \mathbf { X } ^ { T } \mathbf { y } - \mathbf { X } ^ { T } \mathbf { X } \mathbf { b }$ iff both side is zero.

Then we have the following important results:

1. $\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right)$ is nonsingular
2. $\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { X } ^ { T } \mathbf { y }$ is the unique solution of above system.
3. $\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 }$ is a generalized inverse of $\mathbf{X}^T\mathbf{X}$.
4. $\mathbf { C } \left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { X } ^ { T } = \mathbf { 0 } $
5. $\mathbf { C } \left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { C } ^ { T } = \mathbf { I }$

**Proof** We only prove 5, consider $\mathbf { Z } = \left[ \begin{array} { l } \mathbf { X } \\ \mathbf { C } \end{array} \right]$, then $$\mathbf{P_Z}=\mathbf{Z}(\mathbf{Z}^T\mathbf{Z})^g\mathbf{Z}^T=\left[ \begin{array} { l } \mathbf { P_X }&\mathbf{0} \\ \mathbf { 0 }&{\mathbf { C } \left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { C } ^ { T }} \end{array} \right]$$ Note that for idempotent matrix $\mathbf{A}$, $rank(\mathbf{A})=tr(\mathbf{A})$ holds:
$$\begin{aligned}
rank(\mathbf { C } \left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { C } ^ { T })&=tr(\mathbf { C } \left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { C } ^ { T })
\\&=tr(\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf { C } ^ { T }\mathbf{C})
\\&= tr(\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } (\mathbf { C } ^ { T }\mathbf{C}+\mathbf{X}^T\mathbf{X}))
\\&= tr(\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } (\mathbf { C } ^ { T }\mathbf{C}+\mathbf{X}^T\mathbf{X})-\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf{X}^T\mathbf{X})
\\&= tr(\mathbf{I})-tr\left( \mathbf { X } ^ { T } \mathbf { X } + \mathbf { C } ^ { T } \mathbf { C } \right) ^ { - 1 } \mathbf{X}^T\mathbf{X})
\\&= p-tr(\mathbf{P_X})
\\&= p-rank(\mathbf{X})=p-(p-s)=s
\end{aligned}  $$ The proof is finished since invertible idempotent matrix is identity. $\quad\blacksquare$

## Constrained Parameter Space

Consider general constrained case that $\mathbf{b}$ is restricted to a subset $\mathcal{T}\subset \Reals^p$ where $\mathbf{P}^T\mathbf{b}=\delta$,i.e.$$ \mathcal { T } = \left\{ \mathbf { b } : \mathbf { P } ^ { T } \mathbf { b } = \delta \right\} $$ Here we assert $\mathbf{P}$ is $p\times q$ with full-column rank.

$\lambda^T \mathbf{b}$ in the restricted model is linear estimable iff $\lambda-\mathbf{X}^T\mathbf{a}\in\mathcal{C}(\mathbf{P})$. That is $\lambda \in \mathcal { C } \left( \left[ \mathbf { X } ^ { T }\  \mathbf { P } \right] \right)$

Minimizing the target function $Q(\mathbf{y})$ subject to constraints with Lagrange multipliers gives: $$ L ( \mathbf { b } , \theta ) = ( \mathbf { y } - \mathbf { X } \mathbf { b } ) ^ { T } ( \mathbf { y } - \mathbf { X } \mathbf { b } ) + 2 \theta ^ { T } \left( \mathbf { P } ^ { T } \mathbf { b } - \delta \right) $$Taking the derivatives and setting them to zero leads to restricted normal equations(RNEs): $$ \left[ \begin{array} { c c } \mathbf { X } ^ { T } \mathbf { X } & \mathbf { P } \\ \mathbf { P } ^ { T } & \mathbf { 0 } \end{array} \right] \left[ \begin{array} { l } \mathbf { b } \\ \theta \end{array} \right] = \left[ \begin{array} { c } \mathbf { X } ^ { T } \mathbf { y } \\ \delta \end{array} \right] $$ RNEs are always consistent since$$ RHS\in \mathcal { C } \left( \left[ \begin{array} { c c } \mathbf { X } ^ { T } & \mathbf { 0 } \\ \mathbf { 0 } & \mathbf { P } ^ { T } \end{array} \right] \right)\in \mathcal { C } \left( \left[ \begin{array} { c c } \mathbf { X } ^ { T } \mathbf { X } & \mathbf { P } \\ \mathbf { P } ^ { T } & \mathbf { 0 } \end{array} \right] \right) $$ 

Iff $\mathbf{\hat{b}}$ is the first component of a solution to the RNEs, $\mathbf{\hat{b}}$ minimize $Q(y)$