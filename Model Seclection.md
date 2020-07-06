# Implications of Model Selection

## Underfitting or Misspecification

If we omit some varibale in the model:$$ \mathbf{y=Xb+\eta+e} $$

Assume $E(\mathbf{e})=0$ and $\operatorname{Var}(\mathbf{e})=\sigma^2\mathbf{I_N}$ as before. Then the estimator becomes$$ E \left( \lambda ^ { T } \hat { \mathbf { b } } \right) = \lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } E ( \mathbf { y } ) = \lambda ^ { T } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { g } \mathbf { X } ^ { T } ( \mathbf { X } \mathbf { b } + \eta ) = \lambda ^ { T } \mathbf { b } + \mathbf { a } ^ { T } \mathbf { P } _ { \mathbf { X } } \eta $$

The estimation of the variance is $$ \begin{aligned} E \left( \mathbf { y } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { y } \right) & = ( \mathbf { X } \mathbf { b } + \eta ) ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) ( \mathbf { X } \mathbf { b } + \eta ) + \operatorname { tr } \left( \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \left( \sigma ^ { 2 } \mathbf { I } _ { N } \right) \right) \\ & = \eta ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \eta + \sigma ^ { 2 } ( N - r ) \end{aligned} $$

In fact, partitioned $\eta$ into:$$ \mathbf { y } = \mathbf { X } \mathbf { b } + \eta + \mathbf { e } = \mathbf { P } _ { \mathbf { X } \mathbf { y } } + \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) \mathbf { y } = \left( \mathbf { X } \mathbf { b } + \mathbf { P } _ { \mathbf { X } } \eta + \mathbf { P } _ { \mathbf { X } } \mathbf { e } \right) + \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } } \right) ( \eta + \mathbf { e } ) $$

$\mathbf{P_X\eta}\in\mathcal{\mathbf{X}}$ affects the estimation of $\lambda^T\mathbf{b}$ and the other part $\mathbf{I-P_X}\eta$ affects the estimation of the variance.

## Overfitting and Multicollinearity

The case of overfitting can be viewed as: $$ \mathbf{y=X_1b_1+X_2b_2+e} $$

where the second grop is not needed, that is, $\mathbf{b_2=0}$. Denoted $\mathbf { X } = \left[ \mathbf { X } _ { 1 } \mathbf { X } _ { 2 } \right]$ and assume $\mathbf{X_1}$ and $\mathbf{X}$ have full-column rank. 
In the original model, we have show that $\tilde { \mathbf { b } } _ { 1 } = \left( \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } \right) ^ { - 1 } \mathbf { X } _ { 1 } ^ { T } \mathbf { y }$ and $\operatorname { Cov } \left( \tilde { \mathbf { b } } _ { 1 } \right) = \sigma ^ { 2 } \left( \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } \right) ^ { - 1 }$.

For the overfit model:$$ \left[ \begin{array} { c } \hat { \mathbf { b } } _ { 1 } \\ \hat { \mathbf { b } } _ { 2 } \end{array} \right] = \left[ \begin{array} { c c } \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } & \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 2 } \\ \mathbf { X } _ { 2 } ^ { T } \mathbf { X } _ { 1 } & \mathbf { X } _ { 2 } ^ { T } \mathbf { X } _ { 2 } \end{array} \right] ^ { - 1 } \left[ \begin{array} { c } \mathbf { X } _ { 1 } ^ { T } \mathbf { y } \\ \mathbf { X } _ { 2 } ^ { T } \mathbf { y } \end{array} \right] $$

which leads to $$ E \left( \left[ \begin{array} { l } \hat { \mathbf { b } } _ { 1 } \\ \hat { \mathbf { b } } _ { 2 } \end{array} \right] \right) = \left[ \begin{array} { l } \mathbf { b } _ { 1 } \\ \mathbf { 0 } \end{array} \right] \quad \text { and } \quad \operatorname { Cov } \left( \left[ \begin{array} { l } \hat { \mathbf { b } } _ { 1 } \\ \hat { \mathbf { b } } _ { 2 } \end{array} \right] \right) = \sigma ^ { 2 } \left[ \begin{array} { l l } \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } & \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 2 } \\ \mathbf { X } _ { 2 } ^ { T } \mathbf { X } _ { 1 } & \mathbf { X } _ { 2 } ^ { T } \mathbf { X } _ { 2 } \end{array} \right] ^ { - 1 } $$

Recall the inverse of partitioned matrix is $$ \begin{aligned} \left[ \begin{array} { c c } \mathbf { A } & \mathbf { B } \\ \mathbf { C } & \mathbf { D } \end{array} \right] ^ { - 1 } & = \left[ \begin{array} { c c } \mathbf { A } ^ { - 1 } + \mathbf { A } ^ { - 1 } \mathbf { B } \mathbf { E } ^ { - 1 } \mathbf { C A } ^ { - 1 } & - \mathbf { A } ^ { - 1 } \mathbf { B } \mathbf { E } ^ { - 1 } \\ - \mathbf { E } ^ { - 1 } \mathbf { C A } ^ { - 1 } & \mathbf { E } ^ { - 1 } \end{array} \right] \\ & = \left[ \begin{array} { c c } \mathbf { F } ^ { - 1 } & - \mathbf { F } ^ { - 1 } \mathbf { B D } ^ { - 1 } \\ - \mathbf { D } ^ { - 1 } \mathbf { C F } ^ { - 1 } & \mathbf { D } ^ { - 1 } + \mathbf { D } ^ { - 1 } \mathbf { C F } ^ { - 1 } \mathbf { B D } ^ { - 1 } \end{array} \right] \\ & \end{aligned} $$

where $\mathbf { E } = \mathbf { D } - \mathbf { C A } ^ { - 1 } \mathbf { B }$ and $\mathbf { F } = \mathbf { A } - \mathbf { B } \mathbf { D } ^ { - 1 } \mathbf { C }$.

hence $\operatorname { Cov } \left( \hat { \mathbf { b } } _ { 1 } \right) = \sigma ^ { 2 } \left( \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } \right) ^ { - 1 } + \sigma ^ { 2 } \left( \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } \right) ^ { - 1 } \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 2 } \left[ \mathbf { X } _ { 2 } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } _ { 1 } } \right) \mathbf { X } _ { 2 } \right] ^ { - 1 } \mathbf { X } _ { 2 } ^ { T } \mathbf { X } _ { 1 } \left( \mathbf { X } _ { 1 } ^ { T } \mathbf { X } _ { 1 } \right) ^ { - }$

If the second block is orthogonal to the first, that is, $\mathbf{X_1}^T\mathbf{X_2}=0$, then the estimation have the same exception and variance. In this case, take $\mathbf{X_1}=\mathbf{[1\quad x_j]}$, then we have $$ \operatorname { Var } \left( \hat { \mathbf { b } } _ { j } \right) = \sigma ^ { 2 } / S _ { x x } $$

where $S _ { x x } = \sum _ { i } \left( X _ { i j } - \bar { x } _ { . j } \right) ^ { 2 }$. Otherwise, this covariance would be larger, say it's equal to $$ \operatorname { Var } \left( \hat { \mathbf { b } } _ { j } \right) = \operatorname{VIF} \times \sigma ^ { 2 } / S _ { x x } $$

where VIF means **variance inflation factor**. With another form of partition inverse and take $\mathbf{X_1=[x_j]}$, we have $$ \operatorname { Cov } \left( \hat { \mathbf { b } } _ { j } \right) = \sigma ^ { 2 } \left[ \mathbf { X } _ { 1 } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } _ { 2 } } \right) \mathbf { X } _ { 1 } \right] ^ { - 1 } $$

Putting together, we find

$$ \operatorname{VIF} = \frac { S _ { x x } } { \mathbf { X } _ { 1 } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } _ { 2 } } \right) \mathbf { X } _ { 1 } } $$

Suppose we are regression $\mathbf{x_j}$ employed other variables with intercept. Then $S_{xx}$ is SST and $\mathbf { X } _ { 1 } ^ { T } \left( \mathbf { I } - \mathbf { P } _ { \mathbf { X } _ { 2 } } \right) \mathbf { X } _ { 1 }$ is SSE, recall that $R^2=\frac{SSR}{SSL}$, we have $$ \operatorname{VIF}=\frac{1}{1-R^2_j} $$

Another measurment of multicollinearity is MSE. Suppose the estimators of $\sigma$ is $\hat{\sigma}$ then the MSE is $E(\|\hat{\sigma}-\sigma\|^2)$. Take $\hat{b}$ as an example:

$$ \begin{aligned} E \left\{ \| \hat { \mathbf { b } } - \mathbf { b } \| ^ { 2 } \right\} & = E \left\{ ( \hat { \mathbf { b } } - \mathbf { b } ) ^ { T } ( \hat { \mathbf { b } } - \mathbf { b } ) \right\} = \operatorname { tr } E \{ ( \hat { \mathbf { b } } - \mathbf { b } ) ( \hat { \mathbf { b } } - \mathbf { b } ) \\ & = \text {trace } \operatorname { Cov } ( \hat { \mathbf { b } } ) = \sigma ^ { 2 } \operatorname { tr } \left( \mathbf { X } ^ { T } \mathbf { X } \right) ^ { - 1 } \end{aligned} $$

Empolyed SVD leads to $ \sigma \operatorname{tr}(\mathbf{X}^T\mathbf{X})=\sigma\operatorname{tr}(\mathbf{V\mathbf{\Lambda}^T\Lambda }\mathbf{V}^T)^{-1}=\sigma\operatorname{tr}(\mathbf{\Lambda}^T\mathbf{\Lambda})^{-1}=\sum_{i}{\frac{\sigma}{e_i}}$ where $e_i$ is eigenvalues.