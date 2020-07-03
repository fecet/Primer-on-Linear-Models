# Gauss–Markov Model

## Definition of G-M Model

The Gauss-Markov model takes the form $$ \mathbf{y=Xb+e} $$ Then we assume
$$\begin{array}{cc}
E ( \mathbf { e } ) = \mathbf { 0 } \text{ or } E(\mathbf{y})=\mathbf{Xb} \\
Cov(\mathbf{e})=\sigma^2 \mathbf{I_N}
\end{array}$$Hence we have
$$ \begin{aligned}
\operatorname { Var } \left( \lambda ^ { T } \hat { \mathbf { b } } \right) &= \operatorname { Var } \left( \lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y } \right)
\\&= \lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \operatorname { Cov } ( \mathbf { y } ) \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \lambda
\\&=\lambda ^ { T } \left( \mathbf { X } ^ { T }\mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \left( \sigma ^ { 2 } \mathbf { I }_ { N } \right) \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \lambda
\\&=\sigma ^ { 2 } \lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \lambda
\end{aligned} $$

The last equality is since $ \mathbf { X } ^ { T } \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } $ is a proj matrix onto $\mathcal{C}(\mathbf{X}\mathbf{X}^T)=\mathcal{C}(\mathbf{X}^T)$ 

## Gauss-Markov Theorem

Suppose another unbiased estimator $\mathbf{d}^T\mathbf{y}$ then

$$ \begin{aligned}
\text{Var}(\mathbf{d}^T\mathbf{y})&=\operatorname { Var } \left( \lambda ^ { T } \hat { \mathbf { b } } + \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right)
\\&=\operatorname { Var } \left( \lambda ^ { T } \hat { \mathbf { b } } \right) + \operatorname { Var } \left( \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right) + 2 \operatorname { Cov } \left( \lambda ^ { T } \hat { \mathbf { b } } , \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right)
\end{aligned} $$

Where

$$ \begin{aligned}
\operatorname { Cov } \left( \lambda ^ { T } \hat { \mathbf { b } } , \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right)&=\operatorname{Cov}\left( \lambda ^ { T }( \mathbf{X}^T\mathbf{X})^g\mathbf{X}^T\mathbf{y} , (\mathbf{d}^T-\lambda^T(\mathbf{X}^T\mathbf{X})^g\mathbf{X}^T)\mathbf{y} \right)
\\&=\lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \left( \sigma ^ { 2 } \mathbf { I } _ { N } \right) \left( \mathbf { d } - \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \lambda \right)
\\&=\sigma ^ { 2 } \lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \left( \mathbf { X } ^ { T } \mathbf { d } - \mathbf { X } ^ { T } \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \lambda \right)
\end{aligned} $$

Note $ \left( \mathbf { X } ^ { T } \mathbf { d } - \mathbf { X } ^ { T } \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \lambda \right)  =\lambda-\lambda=0$ hence $\operatorname { Cov } \left( \lambda ^ { T } \hat { \mathbf { b } } , \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right)=0$ and hence $\operatorname { Var } \left( \mathbf { d } ^ { T } \mathbf { y } \right)=\operatorname { Var } \left( \lambda ^ { T } \hat { \mathbf { b } } \right) + \operatorname { Var } \left( \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right)$. (In fact we can show that BLUE is uncorrelated with all unbiased estimators of zero.) Thus we have:

> **Gauss-Markov Theorem** $ \lambda^T \mathbf{\hat{b}} $ is the best linear unbiased estimator (BLUE) of $\lambda^T\mathbf{b}$.

We can extended Gauss-Markov theorem to the vector space, that is, suppose we have another estimatos $\mathbf{C}^T\mathbf{y}$ for $\mathbf{\Lambda}^T\mathbf{b}$, then $\operatorname { Cov } ( \mathbf { C } ^ { T } \mathbf { y }) - \operatorname { Cov } ( \mathbf { \Lambda } ^ { T } \hat { \mathbf { b } } )$ is semi posdef.

**Proof**:
$$\begin{aligned}
    \operatorname { Cov } ( \mathbf { C } ^ { T } \mathbf { y }) - \operatorname { Cov } ( \mathbf { \Lambda } ^ { T } \hat { \mathbf { b } } )&=\mathbf{C}^T\operatorname{Cov}(\mathbf{y})\mathbf{C}-\operatorname { Cov } \left( \boldsymbol { \Lambda } ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y } \right)
\\&=\sigma^2\mathbf{C}^T\mathbf{C}-\sigma ^ { 2 } \boldsymbol { \Lambda } ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \boldsymbol { \Lambda }
\\&=\sigma^2\left(\mathbf{C}^T\mathbf{C}-\mathbf{C}^T\mathbf{X}(\mathbf{X}^T\mathbf{X})^g\mathbf{X}^T\mathbf{C}\right)
\\&=\sigma^2(\mathbf{C}^C\mathbf{C}-\mathbf{C}^T\mathbf{P_X}\mathbf{C})
\end{aligned}$$

Then we show that $\mathbf{C}^C\mathbf{C}-\mathbf{C}^T\mathbf{P_X}\mathbf{C}$ is semi posdef:

$$\begin{aligned}
 \mathbf{x}^T(\mathbf{C}^T\mathbf{C}-\mathbf{C}^T\mathbf{P_X}\mathbf{C})\mathbf{x}&=\mathbf{x}^T\mathbf{C}^T\mathbf{C}\mathbf{x}-\mathbf{x}^T\mathbf{C}^T\mathbf{P_X}\mathbf{C}\mathbf{x}
 \\&=\mathbf{x}^T\mathbf{C}^T\mathbf{C}\mathbf{x}-\mathbf{x}^T\mathbf{C}^T\mathbf{P_X}^T\mathbf{P_X}\mathbf{C}\mathbf{x}
 \\&=\|\mathbf{C}x\|-\|\mathbf{P_XC}x\|\ge 0
\end{aligned}$$

Equality occures iff $\mathbf{P_XC=C}$, that is, there exist some matrix $\mathbf{A}$ s.t. $\mathbf{C}=\mathbf{P_XA}$. Recheck this in the 1D case: the equality of $\operatorname { Var } \left( \mathbf { d } ^ { T } \mathbf { y } \right)=\operatorname { Var } \left( \lambda ^ { T } \hat { \mathbf { b } } \right)$ occurs iff $\operatorname { Var } \left( \mathbf { d } ^ { T } \mathbf { y } - \lambda ^ { T } \hat { \mathbf { b } } \right)=0$, hence $\mathbf { d } = \mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \lambda=\mathbf { X } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g T } \mathbf{X}^T\mathbf{a}=\mathbf{P_Xa}$, that is exactly what we get in the extended case.  $\ \ \blacksquare$



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