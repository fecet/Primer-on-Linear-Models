# Point Estimation

Suppose a parametric model for $\mathbf{X}=(X_1,X_2,\cdots,X_n)'$:

$$ \mathbf{X}\sim f_{\mathbf{X}}(\mathbf{x\mid \theta}) $$

where $\theta \in \Theta \subseteq \Reals^k$

A **point estimator** $ W(\mathbf{X})$ is any function of $\mathbf{X}$, a realization $W(\mathbf{x})$ is called a **point estimate**.

## Finding Estimators

### Menthod of Moments(MOM)

Recall the $j$th sample moment is $m_j=\frac{\sum X_i^j}{n}$ and the $j$th population moment is $\mu_j=E(X^j)$

Then we can stack the equation to form system $ \mathbf{m}=\mathbf{\mu} $ and solve for $\theta$. Such solution is called a **method of moments(MOM) estimator**.

### Maximum likelihood estimation

Suppose $\mathbf{X=x}$ is observed, the function 

$$ L(\theta\mid\mathbf{x})=f_{\mathbf{X}}(\mathbf{x}\mid \theta) $$

is called **likelihood function**

Any maximizer $\hat{\theta}=\hat{\theta}(\mathbf{x})=\argmax_\theta L(\theta\mid \mathbf{x})$ of the likelihood function is called a **maximum likelihood estimate**

For any function $f(\theta)$, the MLE of $f(\theta)$ is $f(\hat{\theta})$. This is called as invariance property of MLEs.

## Bayesian estimation

Bayesians regard $\theta$ as a random variable. We often use the Bayesian estimation follows:
1. **Prior distribution** $\theta \sim \pi(\theta)$
2. **Conditional distribution** $$ X|\theta \sim f_{\mathbf{X}}(\mathbf{x}\mid \theta)=L(\theta\mid \mathbf{x}) $$
3. **Joint distribution** $$f_{\mathbf{X},\theta}(\mathbf{x},\theta)= \underbrace{f_{\mathbf{X\mid\theta}}(\mathbf{x}\mid \theta)}_{\text{likelihood}}\underbrace{\pi(\theta)}_{\text{prior}} $$
4. **Marginal distribution** $$ \begin{aligned} f _ { \mathbf { X } } ( \mathbf { x } ) & = \int _ { \Theta } f _ { \mathbf { X } , \theta } ( \mathbf { x } , \theta ) d \theta \\ & = \int _ { \Theta } f _ { \mathbf { X } \mid \theta } ( \mathbf { x } \mid \theta ) \pi ( \theta ) d \theta \end{aligned} $$
5. **Posterior distribution** $$ \begin{aligned} \pi ( \theta \mid \mathbf { x } ) & = \frac { f _ { \mathbf { X } , \theta } ( \mathbf { x } , \theta ) } { f_ { \mathbf { X } } ( \mathbf { x } ) } \\ & = \frac { f _ { \mathbf { X } \mid \theta } ( \mathbf { x } \mid \theta ) \pi ( \theta ) } { \int _ { \Theta } f _ { \mathbf { X } \mid \theta } ( \mathbf { x } \mid \theta ) \pi ( \theta ) d \theta } \end{aligned} $$

We can skip step 4 in practice since $f_{\mathbf{X}}(\mathbf{x})$ does not depend on $\theta$, that is 

$$ \begin{aligned} \pi ( \theta \mid \mathbf { x } ) & \propto f _ { \mathbf { X } \mid \theta } ( \mathbf { x } \mid \theta ) \pi ( \theta ) \\ & = L ( \theta \mid \mathbf { x } ) \pi ( \theta ) \end{aligned} $$

if $T=T(\mathbf{X})$ is sufficient, we can write $f _ { \mathbf { X } \mid \theta } ( x \mid \theta ) = g ( t \mid \theta ) h ( \mathbf { x } )$, since $ f _ { \mathbf { X } \mid T } ( \mathbf { x } \mid t ) = \frac { f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) } { f _ { T } ( t \mid \theta ) } $ is free of $\theta$, hence $f_{T\mid\theta}(t\mid \theta) \propto g(t\mid \theta)$. Therefore $$ \pi ( \theta \mid t ) \propto f _ { T \mid \theta } ( t \mid \theta ) \pi ( \theta ) $$

## Evaluating Estimators

### Bias, variance and MSE

Suppose $W=W(\mathbf{X})$ is a point estimator, we call $W$ **unbiased** of $\tau ( \theta )$ if 

$$ \forall \theta \in \Theta \ni E_{\theta}(W)=\tau ( \theta ) $$

The MSE of $W$ is

$$ \begin{aligned} \operatorname { MSE } _ { \theta } ( W ) & = E _ { \theta } \left[ ( W - \tau(\theta) ) ^ { 2 } \right] \\ & = \operatorname { var } _ { \theta } ( W ) + \left[ E _ { \theta } ( W ) - \tau(\theta) \right] ^ { 2 } \\ & = \operatorname { var } _ { \theta } ( W ) + \operatorname { Bias } _ { \theta } ^ { 2 } ( W ) \end{aligned} $$

where $E_\theta(W)-\tau(\theta)$ is the **bias**. In general, $\operatorname{var}_\theta(W)$ measures **precision** and $\operatorname{Bias}_\theta(W)$ measures **accuracy**.

### Best unbiased estimators

Consider the class of estimators

$$ \mathcal { C } _ { \tau } = \left\{ W = W ( \mathbf { X } ) : E _ { \theta } ( W ) = \tau ( \theta ) \quad \forall \theta \in \Theta \right\} $$

The best estimator is some $W^*\in \mathcal{C_\tau}$ that has the smallest variance. Such estimator is a **uniformly minimum variance unbiased(UMVUE)** of $\tau(\theta)$. 

> **Cramer-Rao Inequality** Suppose $\mathbf{X}\sim f_{\mathbf{X}}(\mathbf{X}\mid\theta)$, where $$ \frac { d } { d \theta } \int _ { \mathbb { R } ^ { n } } h ( \mathbf { x } ) f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) d \mathbf { x } = \int _ { \mathbb { R } ^ { n } } \frac { \partial } { \partial \theta } h ( \mathbf { x } ) f _ { \mathbf { X } } ( \mathbf { x } \mid \theta ) d \mathbf { x } $$ holds
> then for any $W$ with finite variance, we have $$ \operatorname { var } _ { \theta } [ W ( \mathbf { X } ) ] \geq \frac { \left\{ \frac { d } { d \theta } E _ { \theta } [ W ( \mathbf { X } ) ] \right\} ^ { 2 } } { E _ { \theta } \left\{ \left[ \frac { \partial } { \partial \theta } \ln f _ { \mathbf { X } } ( \mathbf { X } \mid \theta ) \right] ^ { 2 } \right\} } $$ The RHS is called **Cramer-Rao Lower Bound(CRLB)**.

**Proof** From Cauchy-Schwarz Inequality $ E | X Y | \leq \sqrt { \left[ E | X | ^ { 2 } \right] \left[ E | Y | ^ { 2 } \right] } $
























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