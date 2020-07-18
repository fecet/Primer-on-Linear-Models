# Distributional Theory

## Multivariate normal distribution

Density of random variable $Y\sim N(\mu,\sigma^2)$ is given by $$ p _ { Y } ( y ) = \left( 2 \pi \sigma ^ { 2 } \right) ^ { - \frac { 1 } { 2 } } \exp \left\{ - ( y - \mu ) ^ { 2 } / \left( 2 \sigma ^ { 2 } \right) \right\} $$

Another route to this is to begin with the standard normal distribution, say $Z\sim N(0,1)$, whose density is $$ p _ { z } ( z ) = ( 2 \pi ) ^ { - \frac { 1 } { 2 } } \exp \left( - z ^ { 2 } / 2 \right) $$

The moment generating function(mgf) for it is $$ m _ { z } ( t ) \equiv E \left[ e ^ { t Z } \right] = \int _ { - \infty } ^ { \infty } e ^ { t z } p _ { z } ( z ) d z = \exp(\frac{t^2}{2}) $$

Now the general case can be constructed by $Y=\mu+\sigma Z$, the density can be derived by note the pdf $F_Y(y)=F_Z(\frac{y-\mu}{\sigma})$ and hence $p_Y(y)=\frac{p_Z(\frac{y-\mu}{\sigma})}{\sigma}$. And the mgf can be derived as $$ \begin{aligned} 
m _ { Y } ( t ) \equiv E \left\{ e ^ { t Y } \right\} & = E \left\{ e ^ { t ( \mu + \sigma Z ) } \right\} \\ & = e ^ { t \mu } \times E \left\{ e ^ { t \sigma Z } \right\} 
\\&= \exp(t\mu+\frac{t^2\sigma^2}{2})
\end{aligned} $$

Similarly, the general case of random vector from the standard multivariate normal $\mathbf{Z}\sim N(0,\mathbf{I})$ is $\mathbf{X=AZ+\mu}$:

If every component of $\mathbf{Z}$ have i.i.d $Z_i \sim N(0,1)$. Then $\mathbf{Z}\sim N(0,\mathbf{I})$. The joint density is $$ p _ { \mathbf { Z } } ( \mathbf { z } ) = ( 2 \pi ) ^ { - p / 2 } \exp \left\{ - \sum _{ i = 1 } ^ { p } z_ { i } ^ { 2 } / 2 \right\} =( 2 \pi ) ^ { - p / 2 } \exp(-\mathbf{z'z}/2)$$

The mgf is $$ \begin{aligned} m _ { \mathbf { z } } ( \mathbf { t } ) & = E \left\{ \exp \left( \mathbf { t } ^ { T } \mathbf { Z } \right) \right\} = E \left\{ \exp \left( \sum _ { i = 1 } ^ { p } t _{ i } Z_ { i } \right) \right\} = \prod _{ i = 1 } ^ { p } m_ { z _{ i } } \left( t_ { i } \right) \\ & = \exp \left\{ \sum _{ i = 1 } ^ { p } t_ { i } ^ { 2 } / 2 \right\} = \exp \left\{ \mathbf { t } ^ { T } \mathbf { t } / 2 \right\} \end{aligned} $$

Thus the mgf for $\mathbf{X=\mu+AZ}$ can be constructed: $$ m _{ \mathbf { X } } ( \mathbf { t } ) = E \left[ e ^ { \mathbf { t } ^ { T } \mathbf { X } } \right] = E \left[ e ^ { \mathbf { t } ^ { T } \mu + \mathbf { t } ^ { T } \mathbf { A } \mathbf { Z } } \right] = e ^ { \mathbf { t } ^ { T } \mu } \times m_ { z } \left( \mathbf { A } ^ { T } \mathbf { t } \right) = \exp \left\{ \mathbf { t } ^ { T } \mu + \mathbf { t } ^ { T } \mathbf { A } \mathbf { A } ^ { T } \mathbf { t } / 2 \right\} $$ where we have $E[\mathbf{X}]=\mu$ and $\operatorname{Cov}(\mathbf{X})=\mathbf{AA}^T$, which lead to 

> **Definition** Random vector $\mathbf{X}\sim N(\mu,\mathbf{V})$ iff the mgf satisfy $$ m _ { \mathbf { X } } ( \mathbf { t } ) = \exp \left\{ \mathbf { t } ^ { T } \mu + \mathbf { t } ^ { T } \mathbf { V } \mathbf { t } / 2 \right\} $$

Note that the shape of $\mathbf{X}$ is the same as $\mu$, the we consider the transformation which turn $\mathbf{X}$ into different dimensions. Suppose $\mathbf{X}\sim N(\mu,\mathbf{V})$ where $X$ is $p\times 1$ and $\mathbf{Y=a+BX}$ where $\mathbf{a}$ is $q\times 1$ and thus $\mathbf{B}$ $q\times p$, then $\mathbf { Y } \sim N _ { q } \left( \mathbf { a } + \mathbf { B } \mu , \mathbf { B } \mathbf { V } \mathbf { B } ^ { T } \right)$ since 

$$ \begin{aligned} m _ { \mathbf { Y } } ( \mathbf { t } ) & = E \left[ e ^ { \mathbf { t } ^ { T } \mathbf { Y } } \right] = E \left[ e ^ { \mathbf { t } ^ { T } ( \mathbf { a } + \mathbf { B } \mathbf { X } ) } \right] = e ^ { \mathbf { t } ^ { T } \mathbf { a } } \times m _ { \mathbf { X } } \left( \mathbf { B } ^ { T } \mathbf { t } \right) \\ & = e ^ { \mathbf { t } ^ { T } \mathbf { a } } \times \exp \left\{ \mathbf { t } ^ { T } \mathbf { B } \mu + \mathbf { t } ^ { T } \mathbf { B } \mathbf { V } \mathbf { B } ^ { T } \mathbf { t } / 2 \right\} \end{aligned} $$

> If $X$ is multivariate normal, then the joint distribution of any subset is multivariate normal.

**Proof** W.L.O.G, partition $\mathbf{X,\mu}$ and $\mathbf{V}$ as: $$ \mathbf { X } = \left[ \begin{array} { l } \mathbf { X } _ { 1 } \\ \mathbf { X } _ { 2 } \end{array} \right] \begin{array} { l } p _ { 1 } \\ p _ { 2 } \end{array} , \quad \mu = \left[ \begin{array} { l } \mu _ { 1 } \\ \mu _ { 2 } \end{array} \right] \begin{array} { l } p _ { 1 } \\ p _ { 2 } \end{array} , \quad \mathbf { V } = \left[ \begin{array} { l l } \mathbf { V } _ { 11 } & \mathbf { V } _ { 12 } \\ \mathbf { V } _ { 21 } & \mathbf { V } _ { 22 } \end{array} \right] \begin{array} { l } p _ { 1 } \\ p _ { 2 } \end{array} $$

Using $\mathbf{a=0}$ and $\mathbf{B}=\mathbf{[I\quad 0]}$, we have $\mathbf{X_1}\sim N(\mu_1,\mathbf{V}_{11})$ $\quad \blacksquare$

If $\mathbf{X\sim N(\mu,\mathbf{V})}$ and $\mathbf{V}$ is nonsingular. then 
1. A nonsingular matrix $\mathbf{A}$ exist s,t, $\mathbf{V=AA}^T$
2. $\mathbf{A}^{-1}(\mathbf{X-\mu})\sim N(0,\mathbf{I})$
3. The pdf is $( 2 \pi ) ^ { - p / 2 } | \mathbf { V } | ^ { - \frac { 1 } { 2 } } \exp \left\{ - \frac { 1 } { 2 } ( \mathbf { x } - \mu ) ^ { T } \mathbf { V } ^ { - 1 } ( \mathbf { x } - \mu ) \right\}$.

**Proof** Covariance matrix must be semi posdef, since $\mathbf{V}$ is nonsingular in this case, it's posdef. Employed Cholesky demp, we have 1. 2 is derived from last result and 3 is given by replacing $\mathbf{Z=\mathbf{A}^{-1}(\mathbf{X-\mu})}$ in the pdf of standard case and note $|\det(\frac{\partial \mathbf{Z}}{\partial \mathbf{X}})|=|\det(\mathbf{A}^{-1})|=\det(V)^{-\frac{1}{2}}$

### Singular Covariance

If covariance matrix $\mathbf{V}$ is singular, since it's still semi posdef, there exist $\Gamma$ such that $\Gamma\Gamma'=\mathbf{V}$, then $\mathbf{Y}\sim N_p(\mu,\mathbf{V})$ has the same distribution of $\mu+\Gamma \mathbf{Z}_k$ where $k=rank(\mathbf{V})$ and $\mathbf{Z}$ is standard. Such $\mathbf{Y}$ is said to have a $p$-variate normal distribution with rank $k$-variate normal distribution with rank $k$ and thus have no density function.

### Independence

Suppose $\mathbf{Y\sim}N(\mathbf{\mu,V})$ where $$ \mathbf { Y } = \left( \begin{array} { c } \mathbf { Y } _ { 1 } \\ \mathbf { Y } _ { 2 } \\ \vdots \\ \mathbf { Y } _ { m } \end{array} \right) , \quad \boldsymbol { \mu } = \left( \begin{array} { c } \boldsymbol { \mu } _ { 1 } \\ \boldsymbol { \mu } _ { 2 } \\ \vdots \\ \boldsymbol { \mu } _ { m } \end{array} \right) , \quad \text { and } \mathbf { V } = \left( \begin{array} { c c c c c } \mathbf { V } _ { 11 } & \mathbf { V } _ { 12 } & \cdots & \mathbf { V } _ { 1 m } \\ \mathbf { V } _ { 21 } & \mathbf { V } _ { 22 } & \cdots & \mathbf { V } _ { 2 m } \\ \vdots & \vdots & \ddots & \vdots \\ \mathbf { V } _ { m 1 } & \mathbf { V } _ { m 2 } & \cdots & \mathbf { V } _ { m m } \end{array} \right) $$ 

then $\mathbf{Y_{1:m}}$ are jointly independent iff $\forall i\neq j \ni \mathbf{V}_{ij}=\mathbf{0}$. Sufficiency is easy to get, for necessity, note

$$ \begin{aligned} M _ { \mathbf { Y } } ( \mathbf { t } ) & = \exp \left( \mathbf { t } ^ { \prime } \boldsymbol { \mu } + \mathbf { t } ^ { \prime } \mathbf { V } \mathbf { t } / 2 \right) \\ & = \exp \left( \sum _ { i = 1 } ^ { m } \mathbf { t } _ { i } ^ { \prime } \boldsymbol { \mu } _ { i } + \sum _ { i = 1 } ^ { m } \mathbf { t } _ { i } ^ { \prime } \mathbf { V } _ { i i } \mathbf { t } _ { i } / 2 \right) \\ & = \prod _ { i = 1 } ^ { m } \exp \left( \mathbf { t } _ { i } ^ { \prime } \boldsymbol { \mu } _ { i } + \mathbf { t } _ { i } ^ { \prime } \mathbf { V } _ { i i } \mathbf { t } _ { i } / 2 \right) = \prod _ { i = 1 } ^ { m } M _ { \mathbf { Y } _ { i } } \left( \mathbf { t } _ { i } \right)\  \blacksquare 
\end{aligned} $$

### Conditinoal distributions

Suppose $\mathbf{X}=( X , Y ) ^ { \prime } \sim \mathcal { N } _ { 2 } ( \boldsymbol { \mu } ,  \mathbf{V})$

where
$$\boldsymbol { \mu } = \left( \begin{array} { c } \mu _ { X } \\ \mu _ { Y } \end{array} \right) \quad \text { and } \quad \mathbf{V}= \left( \begin{array} { c c } \sigma _ { X } ^ { 2 } & \rho \sigma _ { X } \sigma _ { Y } \\ \rho \sigma _ { X } \sigma _ { Y } & \sigma _ { Y } ^ { 2 } \end{array} \right) $$ 

Then 

$$ \begin{aligned}
 f_{Y\mid X}(y|x)=\frac{f_{XY}(x,y)}{f_X(x)}&=\frac{( 2 \pi ) ^ { - 2 / 2 }
 | \mathbf { V } | ^ { - \frac { 1 } { 2 } } \exp \left\{ - \frac { 1 } { 2 } 
 ( \mathbf { x } - \mu ) ^ { T } \mathbf { V } ^ { - 1 } ( \mathbf { x } - \mu ) \right\}}
{\left( 2 \pi  \right) ^ { - \frac { 1 } { 2 } }
 \sigma_x^{-1}
\exp \left\{ -\frac{1}{2}
 ( x - \mu_x ) ^ { 2 } / \left(  \sigma_x ^ { 2 } \right) \right\} }
 \\&=(2\pi)^{-\frac{1}{2}}\left(\frac{|V|}{\sigma_x^2}\right)^{-\frac{1}{2}}\exp\left\{-\frac{1}{2}\left({( \mathbf { x } - \mu ) ^ { T } \mathbf { V } ^ { - 1 } ( \mathbf { x } - \mu )}-{( x - \mu_x ) ^ { 2 } / \sigma_x ^ { 2 }
 }\right)\right\}
\end{aligned} $$

Where

$$ ( \mathbf { x } - \mu ) ^ { T } \mathbf { V } ^ { - 1 } ( \mathbf { x } - \mu ) =- \frac { \left( y - \mu _ { y } \right) ^ { 2 } \sigma _ { x } ^ { 2 } - 2 \left( x - \mu _ { x } \right) \left( y - \mu _ { y } \right) \rho \sigma _ { x } \sigma _ { y } + \left( x - \mu _ { x } \right) ^ { 2 } \sigma _ { y } ^ { 2 } } { \left( - 1 + \rho ^ { 2 } \right) \sigma _ { x } ^ { 2 } \sigma _ { v } ^ { 2 } }$$

Thus we have 

$$ {( \mathbf { x } - \mu ) ^ { T } \mathbf { V } ^ { - 1 } ( \mathbf { x } - \mu )}-{( x - \mu_x ) ^ { 2 } / \sigma_x ^ { 2 }
 }=\frac { \left( y \sigma _ { x } - \mu _ { y } \sigma _ { x } + \left( - x + \mu _ { x } \right) \rho \sigma _ { y } \right) ^ { 2 } } { \left(  1 - \rho ^ { 2 } \right) \sigma _ { x } ^ { 2 } \sigma _ { y } ^ { 2 } } $$

and $$ \left(\frac{|V|}{\sigma_x^2}\right)^{-\frac{1}{2}}= \sigma _ { Y } ^ { 2 } \left( 1 - \rho ^ { 2 } \right)$$

Hence $Y \mid \{ X = x \} \sim N \left\{ \mu _ { Y } + \rho \left( \sigma _ { Y } / \sigma _ { X } \right) \left( x - \mu _ { X } \right) , \sigma _ { Y } ^ { 2 } \left( 1 - \rho ^ { 2 } \right) \right\}$

Similay we can show that, for random vectors $\mathbf{X}$ and $\mathbf{Y}$, suppose they are jointly mult normal $$ \left( \begin{array} { c } \mathrm { X } \\ \mathrm { Y } \end{array} \right) \sim \mathcal { N } \left\{ \left( \begin{array} { c } \boldsymbol { \mu } _ { X } \\ \boldsymbol { \mu } _ { Y } \end{array} \right) , \left( \begin{array} { c c } \boldsymbol { \Sigma } _ { X } & \boldsymbol { \Sigma } _ { Y X } \\ \boldsymbol { \Sigma } _ { X Y } & \boldsymbol { \Sigma } _ { Y } \end{array} \right) \right\} $$

assume $\mathbf{\Sigma_X}$ is nonsingular then $$ \mathbf { Y } \mid \{ \mathbf { X } = \mathbf { x } \} \sim \mathcal { N } \left( \boldsymbol { \mu } _ { Y \mid X } , \boldsymbol { \Sigma } _ { Y \mid X } \right) $$

where $\boldsymbol { \mu } _ { Y \mid X } = \boldsymbol { \mu } _ { Y } + \boldsymbol { \Sigma } _ { Y X } \boldsymbol { \Sigma } _ { X } ^ { - 1 } \left( \mathbf { x } - \boldsymbol { \mu } _ { X } \right)$ and ${ } _ { Y \mid X } = { \boldsymbol { \Sigma } } _ { Y } - { \boldsymbol { \Sigma } } _ { Y X } { \boldsymbol { \Sigma } } _ { X } ^ { - 1 } { \boldsymbol { \Sigma } } _ { X Y }$

## Chi-Square distributions

Let $\mathbf{Z}\sim N_p(\mathbf{0,I_p})$, then $U=\mathbf{=Z'Z}=\sum \mathbf{Z_i^2}$ has chi-square distribution with $p$ degress of freedom, denoted by $U=\chi_p^2$. With density 
$$  f _ { X } ( x \mid p ) = \frac { 1 } { \Gamma \left( \frac { p } { 2 } \right) 2 ^ { p / 2 } } x ^ { \frac { p } { 2 } - 1 } e ^ { - x / 2 } I ( x > 0 )  $$ 

Thus $\chi^2_p=\operatorname{gamma}(p/2,2)$, then it's mgf is

$$ M _ { X } ( t ) = \left( \frac { 1 } { 1 - 2 t } \right) ^ { p / 2 } $$

### Noncentral Chi-square

Suppose 
$$ \begin{aligned} X \mid Y & \sim \chi _ { p + 2 Y } ^ { 2 } \\ Y & \sim \operatorname { Poisson } ( \lambda ) \end{aligned} $$

Such $X$ has noncentral chi-square distribution, denoted by $X\sim \chi_p^2(\lambda)$. The density is

$$ \begin{aligned} f _ { X } ( x ) = \sum _ { y = 0 } ^ { \infty } f _ { X , Y } ( x , y ) & = \sum _ { y = 0 } ^ { \infty } f _ { X \mid Y } ( x \mid y ) f _ { Y } ( y ) \\ & = \sum _ { y = 0 } ^ { \infty } \frac { 1 } { \Gamma \left( \frac { p } { 2 } + y \right) 2 ^ { \frac { p } { 2 } + y } } x ^ { \frac { p } { 2 } + y - 1 } e ^ { - x / 2 } \left( \frac { \lambda ^ { y } e ^ { - \lambda } } { y ! } \right) \end{aligned} $$

and mgf is 

$$ \begin{aligned} M _ { X } ( t ) = E \left[ \left( \frac { 1 } { 1 - 2 t } \right) ^ { \frac { p } { 2 } + Y } \right] & = \sum _ { y = 0 } ^ { \infty } \left( \frac { 1 } { 1 - 2 t } \right) ^ { \frac { p } { 2 } + y } \frac { \lambda ^ { y } e ^ { - \lambda } } { y ! } \\ & = e ^ { - \lambda } \left( \frac { 1 } { 1 - 2 t } \right) ^ { p / 2 } \sum _ { y = 0 } ^ { \infty } \frac { \left( \frac { \lambda } { 1 - 2 t } \right) ^ { y } } { y ! } \\ & = \left( \frac { 1 } { 1 - 2 t } \right) ^ { p / 2 } \exp \left( \frac { 2 \lambda t } { 1 - 2 t } \right) \end{aligned} $$

> If $U_{1:n}$ are independent and $U_i\sim \chi_{p_i}^2(\lambda_i)$, then $U=\sum U_i\sim \chi_p^2(\lambda)$ where $p=\sum p_i$ and $\lambda=\lambda_i$

> If $X \sim N(\mu,1)$, then $U=X^2\sim \chi_1^2(\frac{\mu^2}{2})$

**Proof** Trival from mgf.

> If $\mathbf{X}\sim N_p(\mu,\mathbf{I_p})$, then $W=\mathbf{X'X}\sim \chi_p^2(\frac{1}{2}\mu'\mu)$

**Proof** Trival from above two results.

> If $\mathbf{X}\sim N_p(\mu,\mathbf{V})$ where we assume $\mathbf{V}$ is nonsingular, then $W=\mathbf{X'VX}\sim \chi_p^2(\frac{1}{2}\mu'\mathbf{V}^{-1}\mu)$

**Proof**

Since $\mathbf{V}$ is nonsingular, we can construct $\mathbf{AA'=V}$ hence $\mathbf{Z}=\mathbf{A}^{-1}\mathbf{X}\sim N_p(\mathbf{A}^{-1}\mu,\mathbf{I}_p)$. From last result, we have $\mathbf{Z'Z}\sim\chi^2_p(\frac{1}{2}\mu'\mathbf{V}^{-1}\mu)$.

### Stochastically larger

Suppose noncentral chi-square as 
$$ \begin{aligned} X \mid Y & \sim \chi _ { p + 2 Y } ^ { 2 } \\ Y & \sim \operatorname { Poisson } ( \lambda ) \end{aligned} $$

where $X\sim \chi_p^2(\lambda)$, then $P(X>c)$ is a strictly increasing function of $\lambda$ for fixed $c$ and $p$.

$$\begin{aligned}
 P(X>c)&=\int_{c}^{\infty} f_X(x) dx\\&= \int_{c}^{\infty} \sum_y f_{XY}(x,y) dx\\&=\int_{c}^{\infty} \sum_y f_{X|Y}(x)f_Y(y) dx
\\&=\sum_y f_Y(y)\int_c^{\infty} f_{X|Y}(x|y) dx
\\&=\sum_y\frac{e^{-\lambda } \lambda ^y}{y!} \int_c^{\infty} f_{X|Y}(x|y) dx
\end{aligned} $$

Then we take derivative w.r.t $\lambda$:

$$\begin{aligned}
\frac{d P(X>c)}{d\lambda}&=\frac{d\sum_y\frac{e^{-\lambda } \lambda ^y}{y!} \int_c^{\infty} f_{X|Y}(x|y) dx}{d\lambda}  
\\&=\sum_y\frac{d\frac{e^{-\lambda } \lambda ^y}{y!}  }{d\lambda} \int_c^{\infty} f_{X|Y}(x|y) dx
\\&=\sum_y\left(\frac{e^{-\lambda }  \lambda ^{y-1}}{(y-1)!}-\frac{e^{-\lambda } \lambda ^y}{y!}\right) \int_c^{\infty} f_{X|Y}(x|y) dx
\\&=\sum_y\frac{e^{-\lambda } \lambda ^y}{y!}\left(\int_c^{\infty} f_{X|Y}(x|y+1) dx-\int_c^{\infty} f_{X|Y}(x|y) dx\right)>0\quad \blacksquare 
\end{aligned}  $$

## F Ratio Distribution

Suppose indpendent $U\sim \chi_p^2$ and $V\sim \chi_q^2$, then $$ W=\frac{U/p}{V/q}\sim F_{p,q} $$

with density

$$  f _ { W } ( w ) = \frac { \Gamma \left( \frac { p + q } { 2 } \right) } { \Gamma \left( \frac { p } { 2 } \right) \Gamma \left( \frac { q } { 2 } \right) } \left( \frac { p } { q } \right) ^ { p / 2 } \frac { w ^ { \frac { p } { 2 } - 1 } } { \left[ 1 + \left( \frac { p } { q } \right) w \right] ^ { ( p + q ) / 2 } } I ( w > 0 )  $$

If $U_1\sim \chi_{p1}^2(\phi)$ and $U_2 \sim \chi_{p2}^2$ then

$$ F=\frac{U_1/p_1}{U_2/p_2}\sim F_{p_1,p_2}(\phi) $$ 

with density

$$ p _ { F } ( f ) = \frac { \Gamma \left( \frac { p _ { 1 } + p _ { 2 } } { 2 } \right) \left( p _ { 2 } / p _ { 1 } \right) ^ { p _ { 1 } / 2 } } { \Gamma \left( \frac { 1 } { 2 } p _ { 1 } \right) \Gamma \left( \frac { 1 } { 2 } p _ { 2 } \right) } f ^ { \left( p _ { 1 } / 2 \right) - 1 } \left( 1 + \frac { p _ { 1 } } { p _ { 2 } } f \right) ^ { - \left( p _ { 1 } + p _ { 2 } \right) / 2 } $$

For a noncentral F distribution, $P(W>c)$ is strictly increasing since

$$ \begin{aligned} \operatorname { Pr } ( W > c ) & = \operatorname { Pr } \left( \frac { U _ { 1 } / p _ { 1 } } { U _ { 2 } / p _ { 2 } } > c \right) = \operatorname { Pr } \left( U _ { 1 } > \frac { p _ { 1 } } { p _ { 2 } } c U _ { 2 } \right) \\ & = \int _ { 0 } ^ { \infty } \operatorname { Pr } \left( U _ { 1 } > \frac { p _ { 1 } } { p _ { 2 } } c u _ { 2 } \mid U _ { 2 } = u _ { 2 } \right) p _ { U _ { 2 } } \left( u _ { 2 } \right) d u _ { 2 } \end{aligned} $$

## Quadratic forms

> Suppose symmrtric matrix $p\times p$ $\mathbf{A}$. It's idempotent of rank $s$ iff there exist a $p\times s$ $\mathbf{P}$  $\ni \mathbf{PP'=A}$ and $\mathbf{P'P=I}$.

**Proof** Sufficiency is trival. For necessity, since $\mathbf{A}$ is symmetric and idempotent matrix, it can be spectral decompostioned by $\mathbf{A=Q\Lambda Q'}$. Where the diagonal of $\mathbf{\Lambda}$  is $s$ 1 and $p-s$ 0. Thus

$$ \mathbf{A=Q\Lambda Q'}= \left( \begin{array} { l l } \mathbf{P_1} & \mathbf{P_2} \end{array} \right) \left( \begin{array} { l l } \mathbf { I } _ { s } & 0 \\ 0 & 0 \end{array} \right) \left( \begin{array} { l } \mathbf { P } _ { 1 } ^ { \prime } \\ \mathbf { P } _ { 2 } ^ { \prime } \end{array} \right) = \mathbf { P } _ { 1 } \mathbf { P } _ { 1 } ^ { \prime } $$

Note $$ \mathbf { I } _ { p } = \mathbf { Q } ^ { \prime } \mathbf { Q } = \left( \begin{array} { c } \mathbf { P } _ { 1 } ^ { \prime } \\ \mathbf { P } _ { 2 } ^ { \prime } \end{array} \right) \left( \begin{array} { c c } \mathbf { P } _ { 1 } & \mathbf { P } _ { 2 } \end{array} \right) = \left( \begin{array} { c c } \mathbf { P } _ { 1 } ^ { \prime } \mathbf { P } _ { 1 } & \mathbf { P } _ { 1 } ^ { \prime } \mathbf { P } _ { 2 } \\ \mathbf { P } _ { 2 } ^ { \prime } \mathbf { P } _ { 1 } & \mathbf { P } _ { 2 } ^ { \prime } \mathbf { P } _ { 2 } \end{array} \right)= \left( \begin{array} { c c } \mathbf { P } _ { 1 } ^ { \prime } \mathbf { P } _ { 1 } & \mathbf { P } _ { 1 } ^ { \prime } \mathbf { P } _ { 2 } \\ \mathbf { P } _ { 2 } ^ { \prime } \mathbf { P } _ { 1 } & \mathbf { P } _ { 2 } ^ { \prime } \mathbf { P } _ { 2 } \end{array} \right)=$$
























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
