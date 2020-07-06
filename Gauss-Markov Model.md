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

Suppose another unbiased estimator of $\lambda^T\mathbf{b}$ is $\mathbf{a}^T\mathbf{y}$ then

$$ \begin{aligned}
    \operatorname { Var } ( \mathbf { a } ^ { T } \mathbf { y }) - \operatorname { Var } ( \mathbf { \lambda } ^ { T } \hat { \mathbf { b } } )&=\mathbf{a}^T\operatorname{Var}(\mathbf{y})\mathbf{a}-\operatorname { Var } \left( \boldsymbol { \lambda } ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y } \right)
\\&=\sigma^2\mathbf{a}^T\mathbf{a}-\sigma ^ { 2 } \boldsymbol { \lambda } ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \boldsymbol { \lambda }
\\&=\sigma^2\left(\mathbf{a}^T\mathbf{a}-\mathbf{a}^T\mathbf{X}(\mathbf{X}^T\mathbf{X})^g\mathbf{X}^T\mathbf{a}\right)
\\&=\sigma^2(\mathbf{a}^C\mathbf{a}-\mathbf{a}^T\mathbf{P_X}\mathbf{a})
\\&=\sigma^2\mathbf{a}^T(\mathbf{I}-\mathbf{P_X})\mathbf{a}
\\&=\sigma^2\|\mathbf{(I-P_X)a}\|^2\ge0
\end{aligned} $$

Clearly this equality holds iff $\mathbf{P_Xa}=\mathbf{a}\iff\mathbf{a}\in \mathcal{C}(X)$, or $\mathbf{a}^T\mathbf{y}=\lambda^T\mathbf{\hat{b}}$ since $\lambda^T\mathbf{b}=\lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y } = \mathbf{a}^T\mathbf{X}\left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y }=\mathbf{a}^T\mathbf{P_Xy}=\mathbf{a}^T\mathbf{y} $. In fact, we can show that $\operatorname { Var } ( \mathbf { a } ^ { T } \mathbf { y }) - \operatorname { Var } ( \mathbf { \lambda } ^ { T } \hat { \mathbf { b } } )=\operatorname{Var}(\mathbf{a}^T\mathbf{y}-\lambda^T\mathbf{\hat{b}})$

Thus we have:

> **Gauss-Markov Theorem** $ \lambda^T \mathbf{\hat{b}} $ is the best linear unbiased estimator (BLUE) of $\lambda^T\mathbf{b}$.

Consider the estimator of $\mathbf{0}$, that is $E(\mathbf{t}^T\mathbf{y})=\mathbf{t}^T\mathbf{Xb}=0$ for all $\mathbf{b}$ thus $\mathbf{t}^T\mathbf{X=0}$, that is, $\mathbf{t} \perp \mathcal{C}(\mathbf{X})$, hence we have

> The estimator $\mathbf{a}^T\mathbf{y}$ is BLUE iff it's uncorrelated with all unbiased estimator of zero.

We can extended Gauss-Markov theorem to the vector space, that is, suppose we have another estimatos $\mathbf{C}^T\mathbf{y}$ for $\mathbf{\Lambda}^T\mathbf{b}$, then $\operatorname { Cov } ( \mathbf { C } ^ { T } \mathbf { y }) - \operatorname { Cov } ( \mathbf { \Lambda } ^ { T } \hat { \mathbf { b } } )$ is semi posdef.

**Proof**:
Similar to the proof in original version:
$$\begin{aligned}
    \operatorname { Cov } ( \mathbf { C } ^ { T } \mathbf { y }) - \operatorname { Cov } ( \mathbf { \Lambda } ^ { T } \hat { \mathbf { b } } )&=\mathbf{C}^T\operatorname{Cov}(\mathbf{y})\mathbf{C}-\operatorname { Cov } \left( \boldsymbol { \Lambda } ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } \mathbf { y } \right)
\\&=\sigma^2\mathbf{C}^T\mathbf{C}-\sigma ^ { 2 } \boldsymbol { \Lambda } ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \boldsymbol { \Lambda }
\\&=\sigma^2\left(\mathbf{C}^T\mathbf{C}-\mathbf{C}^T\mathbf{X}(\mathbf{X}^T\mathbf{X})^g\mathbf{X}^T\mathbf{C}\right)
\\&=\sigma^2(\mathbf{C}^C\mathbf{C}-\mathbf{C}^T\mathbf{P_X}\mathbf{C})
\\&=\sigma^2\mathbf{C}^T(\mathbf{I}-\mathbf{P_X})\mathbf{C}
\end{aligned}$$

Then we show that $\mathbf{C}^T(\mathbf{I}-\mathbf{P_X})\mathbf{C}$ is semi posdef, $\forall \mathbf{x}\in \reals^n$:

$$\begin{aligned}
 \mathbf{x}^T\mathbf{C}^T(\mathbf{I}-\mathbf{P_X})\mathbf{C}\mathbf{x}&=\|(\mathbf{I-P_X})\mathbf{Cx}\|^2\ge0
\end{aligned}$$

Equality occures iff $\mathbf{(I-P_X)C=0}$, or componet of $\mathbf{C}$ is in $\mathcal{C}(\mathcal{\mathbf{X}})$, that is exactly what we get in the unextended case.  $\ \ \blacksquare$

## Variance Estimation

To estimate $\sigma^2$, we need the following lemma:

> **Lemma1** Let $\mathbf{Z}$ be a random vector with mean $\mu$ and covariance $\mathbf{\Sigma}$, then $E \left( \mathbf { Z } ^ { T } \mathbf { A } \mathbf { Z } \right) = \mu ^ { T } \mathbf { A } \mu + \operatorname { tr } ( \mathbf { A } \mathbf { \Sigma } )$

Then we have an estimator of $\sigma^2$ by SSE:

$$ \hat { \sigma } ^ { 2 } = \frac{\hat { \mathbf { e } } ^ { T } \hat { \mathbf { e } } }{N-r}=\frac{\mathbf { y } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { y }}{N-r} $$

since $$ E \left( \mathbf { y } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { y } \right) = ( \mathbf { X } \mathbf { b } ) ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { X } \mathbf { b } + \operatorname { tr } \left( \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \left( \sigma ^ { 2 } \mathbf { I } _ { N } \right) \right) = \sigma ^ { 2 } ( N - r ) $$

Moreover, we also have 
$$ \begin{aligned}
E (\|\mathbf{\hat{y}}\|^2) &= E \left( \mathbf { y } ^ { T } \mathbf { P } _ { \mathbf { X } } \mathbf { y } \right) = \mathbf { b } ^ { T } \mathbf { X } ^ { T } \mathbf { P } _ { \mathbf { X } } \mathbf { X } \mathbf { b } + \operatorname { tr } \left( \mathbf { P } _ { \mathbf { X } } \sigma ^ { 2 } \mathbf { I } _ { N } \right) = \| \mathbf { X } \mathbf { b } \| ^ { 2 } + r \sigma ^ { 2 } 
\\
E(\|\mathbf{y}\|^2)&=E(\mathbf{y}^T\mathbf{I}\mathbf{y})=\|\mathbf{Xb}\|^2+N\sigma^2
\end{aligned} $$

## Revisited Constrained Parameter Space

Recall the constrained model with constrains $\mathbf{P}^T\mathbf{b}=\delta$, which lead RNEs

$$  \left[ \begin{array} { c c } \mathbf { X } ^ { T } \mathbf { X } & \mathbf { P } \\ \mathbf { P } ^ { T } & \mathbf { 0 } \end{array} \right] \left[ \begin{array} { l } \mathbf { b } \\ \theta \end{array} \right] = \left[ \begin{array} { c } \mathbf { X } ^ { T } \mathbf { y } \\ \delta \end{array} \right]  $$

> **Lemma 1** If $\lambda^T\mathbf{b}$ is estimable, then following euqations are consistent. $$ \left[ \begin{array} { c c } \mathbf { X } ^ { T } \mathbf { X } & \mathbf { P } \\ \mathbf { P } ^ { T } & \mathbf { 0 } \end{array} \right] \left[ \begin{array} { l } \mathbf { v } _ { 1 } \\ \mathbf { v } _ { 2 } \end{array} \right] = \left[ \begin{array} { l } \lambda \\ \mathbf { 0 } \end{array} \right] $$

> **Lemma 2** If $\lambda^T\mathbf{b}$ is estimable, then $\lambda^T\mathbf{\hat{b}_H}$ is its unbiasd estimator.

**Proof** Employed lemma 1, we have

$$ \lambda ^ { T } \hat { \mathbf { b } } _ { H } = \left[ \begin{array} { l l } \lambda ^ { T } & \mathbf { 0 } \end{array} \right] \left[ \begin{array} { l } \hat { \mathbf { b } } _ { H } \\ \hat { \theta } _ { H } \end{array} \right] = \left[ \begin{array} { l l } \mathbf { v } _ { 1 } \\ \mathbf { v } _ { 2 } \end{array} \right] ^ { T } \left[ \begin{array} { c c } \mathbf { X } ^ { T } \mathbf { X } & \mathbf { P } \\ \mathbf { P } ^ { T } & \mathbf { 0 } \end{array} \right] \left[ \begin{array} { l } \hat { \mathbf { b } } _ { H } \\ \hat { \theta } _ { H } \end{array} \right]= \left[ \begin{array} { l l } \mathbf { v } _ { 1 } \\ \mathbf { v } _ { 2 } \end{array} \right] ^ { T } \left[ \begin{array} { c } \mathbf { X } ^ { T } \mathbf { y } \\ \delta \end{array} \right] $$

so that $$ E \left( \lambda ^ { T } \hat { \mathbf { b } } _ { H } \right) = E \left( \mathbf { v } _ { 1 } ^ { T } \mathbf { X } ^ { T } \mathbf { y } + \mathbf { v } _ { 2 } ^ { T } \delta \right) = \mathbf { v } _ { 1 } ^ { T } \mathbf { X } ^ { T } \mathbf { X } \mathbf { b } + \mathbf { v } _ { 2 } ^ { T } \delta = \left( \lambda - \mathbf { P } \mathbf { v } _ { 2 } \right) ^ { T } \mathbf { b } + \mathbf { v } _ { 2 } ^ { T } \delta = \lambda ^ { T } \mathbf { b }\quad\blacksquare $$

Then we show that such estimator is BLUE. 
**Proof** Suppose $\mathbf { a } ^ { T } \mathbf { y } + \mathbf { d } ^ { T } \delta$ be another estimator of $\lambda^T\mathbf{b}$ where $\lambda=\mathbf{X}^T\mathbf{a}+\mathbf{Pd}$.

$$\begin{aligned}
\operatorname{Var}(\mathbf { a } ^ { T } \mathbf { y } + \mathbf { d } ^ { T } \delta) - \operatorname{Var}(\lambda^T\mathbf{\hat{b}_H})&=\operatorname{Var}(\mathbf { a } ^ { T } \mathbf { y } + \mathbf { d } ^ { T } \delta) -\operatorname{Var}(\mathbf { v } _ { 1 } ^ { T } \mathbf { X } ^ { T } \mathbf { y } + \mathbf { v } _ { 2 } ^ { T } \delta)
\\&=\operatorname{Var}(\mathbf{a}^T\mathbf{y})-\operatorname{Var}(\mathbf { v } _ { 1 } ^ { T } \mathbf { X } ^ { T } \mathbf { y })
\\&=\sigma^2(\mathbf{a}^T\mathbf{a}-\mathbf{v_1}^T\mathbf{X}^T\mathbf{X}\mathbf{v_1})
\end{aligned} $$

Note that $$ \operatorname { Var } ( \lambda ^ { T } \hat { \mathbf { b } } _ { H } - \mathbf { a } ^ { T } \mathbf { y } )= \operatorname{Var}(\mathbf { v } _ { 1 } ^ { T } \mathbf { X } ^ { T } \mathbf { y }-\mathbf{a}^T\mathbf{y})=\sigma^2(\mathbf{Xv_1-a})^T(\mathbf{Xv_1-a})=\sigma^2(\mathbf{a}^T\mathbf{a}-\mathbf{v_1}^T\mathbf{X}^T\mathbf{X}\mathbf{v_1})$$

since $$\mathbf{v_1}^T\mathbf{X}^T\mathbf{X}\mathbf{v_1}=\mathbf{v_1}^T(\lambda-\mathbf{Pv_2})=\mathbf{v_1}^T\lambda=\mathbf{v_1}^T\lambda=\mathbf{v_1}^T(\mathbf{X}^T\mathbf{a}+\mathbf{Pd})=\mathbf{v_1}^T\mathbf{X}^T\mathbf{a}=\mathbf{a}^T\mathbf{Xv_1}$$

Hence we have $$ \operatorname{Var}(\mathbf { a } ^ { T } \mathbf { y } + \mathbf { d } ^ { T } \delta) - \operatorname{Var}(\lambda^T\mathbf{\hat{b}_H}) = \operatorname { Var } ( \lambda ^ { T } \hat { \mathbf { b } } _ { H } - \mathbf { a } ^ { T } \mathbf { y } )\ge 0\quad \blacksquare$$