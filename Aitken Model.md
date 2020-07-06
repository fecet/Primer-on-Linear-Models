# Aitken Model and Generalized Least Squares

The Aitken model relax the assumption of Gauss-Markov model in covariance, that is $\operatorname{Cov}(\mathbf{e})=\sigma^2\mathbf{V}$ where $\mathbf{V}$ is posdef.

Then we should find $\mathbf{R}$, s.t. $\mathbf{RVR}^T=\mathbf{I}$. We can approch this by two ways: Cholesky factorization ($\mathbf{V}=\mathbf{LL}^T\implies \mathbf{R}=\mathbf{L}^{-1}$) and spectral decomposition ($\mathbf{V}=\mathbf{Q\Lambda Q}^T\implies \mathbf { R } = \mathbf { Q } \mathbf { \Lambda } ^ { - 1 / 2 } \mathbf { Q } ^ { T }$)

Then we can transform Aitken model into $$ \mathbf{z=Ry=RXb+Re=Ub+f} $$ where $E(\mathbf{f})=\mathbf{R}E(\mathbf{e})=0$ and $\operatorname{Cov}(\mathbf{z})=\mathbf{R}\operatorname{Cov}(\mathbf{y})\mathbf{R}^T=\sigma^2\mathbf{RVR}^T=\sigma^2\mathbf{I}$, that is why we should find $\mathbf{R}$ with such form.

## Estimability

$\lambda^T\mathbf{b}$ is estimable if $\lambda\in\mathcal{C}(\mathbf{U})^T=\mathcal { C } \left( \mathbf { X } ^ { T } \mathbf { R } ^ { T } \right) = \mathcal { C } \left( \mathbf { X } ^ { T } \right)$ since $\mathbf{R}$ is nonsingular. That is what we expected since estimability has nothing to do with second moment, so it's doesn't care wheather $\mathbf{V}$ is constant diagonal.

## Linear Estimator

It's claear that the linear estimators in $\mathbf{y}$ is also linear in $\mathbf{z}$ and vice versa.

## Generalized Least Squares Estimators

The solution of $\mathbf { U } ^ { T } \mathbf { U b } = \mathbf { U } ^ { T } \mathbf { z }$ or $\mathbf { X } ^ { T } \mathbf { V } ^ { - 1 } \mathbf { X } \mathbf { b } = \mathbf { X } ^ { T } \mathbf { V } ^ { - 1 } \mathbf { y }$ will be denoted as $\hat{b}_{GLS}$, for clarity the solution to the NEs is $\mathbf{\hat{b}}_{OLS}$, it minimizes 

$$ \| \mathbf { z } - \mathbf { U b } \| ^ { 2 } = \| \mathbf { R } ( \mathbf { y } - \mathbf { X } \mathbf { b } ) \| ^ { 2 } = ( \mathbf { y } - \mathbf { X } \mathbf { b } ) \mathbf { V } ^ { - 1 } ( \mathbf { y } - \mathbf { X } \mathbf { b } ) $$

The estimation of $\sigma^2$ is:

$$ \begin{aligned} \hat { \sigma } _ { G L S } ^ { 2 } & = \left( \mathbf { z } - \mathbf { U } \hat { \mathbf { b } } _ { G L S } \right) ^ { T } \left( \mathbf { z } - \mathbf { U } \hat { \mathbf { b } } _ { G L S } \right) / ( N - r ) \\ & = \left( \mathbf { y } - \mathbf { X } \hat { \mathbf { b } } _ { G L S } \right) \mathbf { V } ^ { - 1 } \left( \mathbf { y } - \mathbf { X } \hat { \mathbf { b } } _ { G L S } \right) / ( N - r ) \end{aligned} $$

And we have

> **Aitken's Theorem** $\lambda^T\mathbf{\hat{b}_{GLS}}$ is the BLUE for $\lambda^T\mathbf{b}$.

We can extended it to vector space then prove as before. And so we have $\mathbf{a}^T\mathbf{y}=\mathbf{a}^T\mathbf{R^{-1}z}$ is BLUE iff $(\mathbf{R}^{-1})^T\mathbf{a}\in \mathcal{C}(\mathbf{U})$, i.e., there exist some $\mathbf{w}$ s.t. $(\mathbf{R}^{-1})^T\mathbf{a}=\mathbf{Uw=RXw}\iff \mathbf{a}=\mathbf{R}^T\mathbf{RXw}=\mathbf{V}^{-1}\mathbf{Xw}\iff \mathbf{V}\mathbf{a}=\mathbf{Xw}\iff \mathbf{Va}\in\mathcal{C}(\mathbf{X})$.

> Under the Aitken model, estimator $\mathbf{a}^T\mathbf{y}$ is BLUE iff $\mathbf{Va}\in \mathcal{C}(\mathbf{X})$.

Then we consider when $\hat{b}_{OLS}$ is BLUE under the Aitken model. Since $\lambda^T \hat{b}_{OLS}=\lambda^T (\mathbf{X}^T\mathbf{X})^g\mathbf{X}^T\mathbf{y}$, to make it be BLUE for all $\lambda$, we have for all $\mathbf{a}$, $\mathbf{VP_Xa} \in \mathcal{C}(\mathbf{X})$ where $\lambda=\mathbf{X}^T\mathbf{a}$ That is, 

> Under the Aitken model, all OLS estimator are BLUE iff there exist some matrix $\mathbf{Q}$, s.t. $\mathbf{VX=XQ}$