# The Linear Least Squares Problem

Target function:

$$ Q(b)=( \mathbf { y } - \mathbf { X } \mathbf { b } ) ^ { T } ( \mathbf { y } - \mathbf { X } \mathbf { b } ) = \mathbf { y } ^ { T } \mathbf { y } - 2 \mathbf { y } ^ { T } \mathbf { X } \mathbf { b } + \mathbf { b } ^ { T } \mathbf { X } ^ { T } \mathbf { X } \mathbf { b } $$
let the gradient to zero, we get:

Normal equations(NEs):
$$ \mathbf { X } ^ { T } \mathbf { X } \mathbf { b } = \mathbf { X } ^ { T } \mathbf { y } $$

Then we have the following important results:

1. $\hat{b}$ is a solution of NEs iff $\hat{b}$ minimizes $Q(b)$.

2. $\mathbf{\hat{y}=X\hat{b}}$ is free of the choice of solution $\hat{b}$

3. $ \mathbf { X } ^ { T } \mathbf { X } \mathbf { A } = \mathbf { X } ^ { T } \mathbf { X B } \iff \mathbf { X A } = \mathbf { X B } $


4. $\left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T }$ is one of the generalized inverse of $\mathbf{X}$

Above results lead to(since $P_X$ below can be written as $XX^g$):

**Theorem 1** $\mathbf { P } _ { \mathbf { X } } = \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T }$ is the proj matrix onto $\mathcal{C}(X)$
Thus have

1. $\mathbf{I-P_X}$ is the proj matrix onto $\mathcal{N}(\mathbf{X^T})$

2. The solutions for the NEs are solutions for $\mathbf { X b } = \mathbf { P } _ { \mathbf { X }  }\mathbf{y}$

3. $\mathbf{y}$ can be decomposed uniquely as $\mathbf { y } = \hat { \mathbf { y } } + \hat { \mathbf { e } } = \mathbf { P } _ { \mathbf { X } \mathbf { y } } + \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { y }$ where $\hat { \mathbf { y } } \in \mathcal { C } ( \mathbf { X } )$ and $\hat { \mathbf { e } } \in \mathcal { N } \left( \mathbf { X } ^ { T } \right)$. Hence $$ \| \mathbf { y } \| ^ { 2 } = \| \hat { \mathbf { y } } \| ^ { 2 } + \| \hat { \mathbf { e } } \| ^ { 2 } $$

4. All the solutions of NEs can be given by:
   $$
   \hat { \mathbf { b } } ( \mathbf { z } ) = \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y } + \left( \mathbf { I } - \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { X } \right) \mathbf { z }
   $$

**Theorem 2** If $
\mathcal { C } ( \mathbf { W } ) \subseteq \mathcal { C } ( \mathbf { X } )$, then $\mathbf { P } _{ \mathbf { X } } - \mathbf { P }_ { \mathbf { W } }$ is the proj onto $\mathcal { C } \left( \left( \mathbf { I } - \mathbf { P } _{ \mathbf { W } } \right) \mathbf { X } \right)
$
Note $$(\mathbf { P }_ { \mathbf { X } } - \mathbf { P } _{ \mathbf { W } })\mathbf{b}=\mathbf{P_Xb}-\mathbf{P_Wb}=\mathbf{Xb'-P_WP_Xb}=\mathbf{(I-P_W)Xb'} $$

## Reparameterization

Linear models $\mathbf{y=Xb+e}$ and $\mathbf{y=Wc+e}$ are **equivalent** or **reparameterizations** iff $\mathcal{C}(\mathbf{X})=\mathcal{C}\mathbf{(W)}$. Recall that if $\mathcal{C}(\mathbf{X})=\mathcal{C}\mathbf{(W)}$, then there exist $\mathbf{S}$ and $\mathbf{T}$, s.t. $\mathbf{W=XT}$ and $\mathbf{X=WS}$.
We now show some important results:

1. If $\mathcal{C}(\mathbf{X})=\mathcal{C}\mathbf{(W)}$, then $\mathbf{P_X=P_W}$, which implies $\mathbf{\hat{y}=P_Xy=P_Wy}$ and $\mathbf{\hat{e}=(I-P_X)y=(I-P_W)y}$.

2. If $\mathbf{\hat{c}}$ solves the NEs in $\mathbf{W}$, then $\mathbf{\hat{b}=T\hat{c}}$ solves the NEs in $\mathbf{X}$ since $$ \mathbf { X } ^ { T } \mathbf { X } \mathbf { T } \hat { \mathbf { c } } = \mathbf { X } ^ { T } \mathbf { W } \hat { \mathbf { c } } = \mathbf { X } ^ { T } \mathbf { P } _ { \mathbf { W } } \mathbf { y } = \mathbf { X } ^ { T } \mathbf { P } _ { \mathbf { X } } \mathbf { y } = \mathbf { X } ^ { T } \mathbf { y } $$.

## Gram-Schmidt Orthonormalization

For any matrix $X$, it can be decomposed as a unitary matrix and a upper triangle matrix, i.e.
$$ \mathbf{X=QR} $$ Such QR factorization also related to the Cholesky factorization:
$$ \mathbf { X } ^ { T } \mathbf { X } = \mathbf { L } \mathbf { L } ^ { T } = ( \mathbf { Q } \mathbf { R } ) ^ { T } ( \mathbf { Q } \mathbf { R } ) = \mathbf{R^TQ^TQR}=\mathbf { R } ^ { T } \mathbf { R } $$ So $\mathbf{R}$ is the transpose of $\mathbf{L}$.