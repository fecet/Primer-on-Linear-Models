# Discrete Distribuutions

## Discrete Uniform

$$ f _ { X } ( x \mid N ) = \left\{ \begin{array} { c c } \frac { 1 } { N } , & x = 1,2 , \ldots , N \\ 0 , & \text { otherwise } \end{array} \right. $$

**Notation**: $X\sim\operatorname{DU}(1,N)$

### Moments

$$ \begin{aligned} E ( X ) & = \frac { N + 1 } { 2 } \\ \operatorname { var } ( X ) & = \frac { ( N + 1 ) ( N - 1 ) } { 12 } \end{aligned} $$

### MGF

$$ \begin{aligned} M _ { X } ( t ) = E \left( e ^ { t X } \right) & = \sum _ { x = 1 } ^ { N } e ^ { t x } \frac { 1 } { N } \\ & = \frac { 1 } { N } e ^ { t } + \frac { 1 } { N } e ^ { 2 t } + \cdots + \frac { 1 } { N } e ^ { N t } \end{aligned} $$

## Hypergeometric

$$ f _ { X } ( x \mid N , M , K ) = \left\{ \begin{array} { c c } \frac { \left( \begin{array} { c } M \\ x \end{array} \right) \left( \begin{array} { c } N - M \\ K - x \end{array} \right) } { \left( \begin{array} { c } N \\ K \end{array} \right) } , & x = 0,1,2 , \ldots , K \\ 0 , & \text { otherwise } \end{array} \right. $$

**Notation** $X\sim \operatorname{hyper}(N,K,M)$

### Moments

$$ \begin{aligned} E ( X ) & = \frac { K M } { N } \\ \operatorname { var } ( X ) & = \frac { K M } { N } \left( 1 - \frac { M } { N } \right) \left( \frac { N - K } { N - 1 } \right) \end{aligned} $$

## Binomial

$$ f _ { X } ( x \mid n , p ) = \left\{ \begin{array} { c c } \left( \begin{array} { c } n \\ x \end{array} \right) p ^ { x } ( 1 - p ) ^ { n - x } , & x = 0,1,2 , \ldots , n \\ 0 , & \text { otherwise } \end{array} \right. $$

**Notation** $X \sim b(n,p)$

### Moments

$$ \begin{aligned} E ( X ) & = n p \\ \operatorname { var } ( X ) & = n p ( 1 - p ) \end{aligned} $$

### MGF

$$ \begin{aligned} M _ { X } ( t ) = E \left( e ^ { t X } \right) & = \sum _ { x = 0 } ^ { n } e ^ { t x } \left( \begin{array} { c } n \\ x \end{array} \right) p ^ { x } ( 1 - p ) ^ { n - x } \\ & = \sum _ { x = 0 } ^ { n } \left( \begin{array} { c } n \\ x \end{array} \right) \left( p e ^ { t } \right) ^ { x } ( 1 - p ) ^ { n - x } = \left( q + p e ^ { t } \right) ^ { n } \end{aligned} $$

## Geometric

$$ f _ { X } ( x \mid p ) = \left\{ \begin{array} { c c } ( 1 - p ) ^ { x - 1 } p , & x = 1,2,3 , \ldots \\ 0 , & \text { otherwise } \end{array} \right. $$

**Notation** $X\sim \operatorname{geom}(p)$

### Moments

$$ \begin{aligned} M _ { X } ( t ) = E \left( e ^ { t X } \right) = \sum _ { x = 1 } ^ { \infty } e ^ { t x } ( 1 - p ) ^ { x - 1 } p & = \frac { p } { q } \sum _ { x = 1 } ^ { \infty } \left( q e ^ { t } \right) ^ { x } \\ & = \frac { p } { q } \left[ \sum _ { x = 0 } ^ { \infty } \left( q e ^ { t } \right) ^ { x } - 1 \right] \\ & = \frac { p } { q } \left( \frac { 1 } { 1 - q e ^ { t } } - 1 \right) \\ & = \frac { p e ^ { t } } { 1 - q e ^ { t } } \end{aligned} $$

### Memoryless

The geometric distribution is the only discrete distribution that has this property

## Negative Binomial

$$ f _ { X } ( x \mid r , p ) = \left\{ \begin{array} { c } \left( \begin{array} { c } x - 1 \\ r - 1 \end{array} \right) p ^ { r } ( 1 - p ) ^ { x - r } , \quad x = r , r + 1 , r + 2 , \ldots \\ 0 , & \text { otherwise } \end{array} \right. $$

**Notation**: $X\sim nib(r,p)$

### Moments

$$ \begin{aligned} E ( X ) & = \frac { r } { p } \\ \operatorname { var } ( X ) & = \frac { r q } { p ^ { 2 } } \end{aligned} $$

### MGF

$$ \begin{aligned} M _ { X } ( t ) = E \left( e ^ { t X } \right) & = \sum _ { x = r } ^ { \infty } e ^ { t x } \left( \begin{array} { c } x - 1 \\ r - 1 \end{array} \right) p ^ { r } ( 1 - p ) ^ { x - r } \\ & = \left( p e ^ { t } \right) ^ { r } \sum _ { r = r } ^ { \infty } \left( \begin{array} { c } x - 1 \\ r - 1 \end{array} \right) \left( q e ^ { t } \right) ^ { x - r }
\\&=\left( \frac { p e ^ { t } } { 1 - q e ^ { t } } \right) ^ { r }
 \end{aligned} $$

Note $(1-w)^{-r}= \sum _ { z = 0 } ^ { \infty } \frac { f ^ { ( z ) } ( 0 ) } { z ! } w ^ { z } = \sum _ { z = 0 } ^ { \infty } \frac { r ( r + 1 ) \cdots ( r + z - 1 ) } { z ! } w ^ { z } = \sum _ { z = 0 } ^ { \infty } \left( \begin{array} { c } r + z - 1 \\ r - 1 \end{array} \right) w ^ { z }$

## Poisson
$$ f _ { X } ( x \mid \lambda ) = \left\{ \begin{aligned} \frac { \lambda ^ { x } e ^ { - \lambda } } { x ! } , & x = 0,1,2 , \\ 0 , & \text { otherwise } \end{aligned} \right. $$

**Notation**: $X\sim \operatorname{Poisson}(\lambda)$

### Moments

$$ \begin{aligned} E ( X ) & = \lambda \\ \operatorname { var } ( X ) & = \lambda \end{aligned} $$

### MGF

$$ \begin{aligned} M _ { X } ( t ) = E \left( e ^ { t X } \right) & = \sum _ { x = 0 } ^ { \infty } e ^ { t x } \frac { \lambda ^ { x } e ^ { - \lambda } } { x ! } \\ & = e ^ { - \lambda } \sum \frac { \left( \lambda e ^ { t } \right) ^ { x } } { x ! } = e ^ { - \lambda } e ^ { \lambda e ^ { t } } = e ^ { \lambda ( t } \end{aligned} $$

# Continuous Distributions

## Uniform

$$ f _ { X } ( x \mid a , b ) = \left\{ \begin{array} { c l } \frac { 1 } { b - a } , & a < x < b \\ 0 , & \text { otherwise } \end{array} \right. $$

**Notation**: $X\sim U(a,b)$

### Moments

$$ \begin{aligned} E ( X ) & = \frac { a + b } { 2 } \\ \operatorname { var } ( X ) & = \frac { ( b - a ) ^ { 2 } } { 12 } \end{aligned} $$

### MGF

$$ M _ { X } ( t ) = \left\{ \begin{array} { c l } \frac { e ^ { b t } - e ^ { a t } } { ( b - a ) t } , & t \neq 0 \\ 1 , & t = 0 \end{array} \right. $$

### CDF

$$ F _ { X } ( x ) = \left\{ \begin{array} { c c } 0 , & x \leq a \\ \frac { x - a } { b - a } , & a < x < b \\ 1 , & x \geq b \end{array} \right. $$


## Gamma

$$ f _ { X } ( x \mid \alpha , \beta ) = \frac { 1 } { \Gamma ( \alpha ) \beta ^ { \alpha } } x ^ { \alpha - 1 } e ^ { - x / \beta } I ( x > 0 ) $$

**Notation:** $X\sim \operatorname{gamma}(\alpha,\beta)$,Where $\Gamma ( \alpha ) = \int _ { 0 } ^ { \infty } u ^ { \alpha - 1 } e ^ { - u } d u$

### Moments

$$ \begin{aligned} E ( X ) & = \alpha \beta \\ \operatorname { var } ( X ) & = \alpha \beta ^ { 2 } \end{aligned} $$

### MGF

$$ \begin{aligned} 
M _ { X } ( t ) & = \frac { 1 } { \Gamma ( \alpha ) \beta ^ { \alpha } } \int _ { 0 } ^ { \infty } e ^ { t x } x ^ { \alpha - 1 } e ^ { - x / \beta } d x \\ & = \frac { 1 } { \Gamma ( \alpha ) \beta ^ { \alpha } } \int _ { 0 } ^ { \infty } x ^ { \alpha - 1 } e ^ { - \left( \frac { 1 } { \phi } - t \right) x } d x \\ & = \frac { 1 } { \Gamma ( \alpha ) \beta ^ { \alpha } } \int _ { 0 } ^ { \infty } x ^ { \alpha - 1 } e ^ { - x / \left( \frac { \rho } { 1 - \beta t } \right) } d x 
\\&=\frac { 1 } { \Gamma ( \alpha ) \beta ^ { \alpha } } \Gamma ( \alpha ) \left( \frac { \beta } { 1 - \beta t } \right) ^ { \alpha } = \left( \frac { 1 } { 1 - \beta t } \right) ^ { \alpha }
\end{aligned} $$

Note we use the fact $$ \int _ { 0 } ^ { \infty } \frac { 1 } { \Gamma ( \alpha ) \beta \alpha } x ^ { \alpha - 1 } e ^ { - x / \beta } d x = 1 \quad \Longrightarrow \quad \int _ { 0 } ^ { \infty } x ^ { \alpha - 1 } e ^ { - x / \beta } d x = \Gamma ( \alpha ) \beta ^ { \alpha } $$

### Connection with Poisson

Suppose we observe some Poisson process with $\lambda$, Define $W$ is the time untill we observe the $\alpha$th event.

$$ \begin{aligned} F _ { W } ( w ) = P _ { W } ( W \leq w ) & = 1 - P _ { W } ( W > w ) \\ & = 1 - \operatorname { pr } ( \{ \text { fewer than } \alpha \text { events in } [ 0 , w ] \} ) \\ & = 1 - \sum _ { j = 0 } ^ { \alpha - 1 } \frac { ( \lambda w ) ^ { j } e ^ { - \lambda w } } { j ! } \end{aligned} $$

$$ \begin{aligned} f _ { W } ( w ) = \frac { d } { d w } F _ { W } ( w ) & = \lambda e ^ { - \lambda w } - e ^ { - \lambda w } \sum _ { j = 1 } ^ { \alpha - 1 } \left[ \frac { j ( \lambda w ) ^ { j - 1 } \lambda } { j ! } - \frac { ( \lambda w ) ^ { j } \lambda } { j ! } \right] \\ & = \lambda e ^ { - \lambda w } - e ^ { - \lambda w } \left[ \lambda - \frac { \lambda ( \lambda w ) ^ { \alpha - 1 } } { ( \alpha - 1 ) ! } \right] \\ & = \frac { \lambda ^ { \alpha } } { \Gamma ( \alpha ) } w ^ { \alpha - 1 } e ^ { - \lambda w } \end{aligned} $$

Hence $W \sim \operatorname{gamma}(\alpha,\frac{1}{\lambda})$. 

## Exponential
$$ f _ { X } ( x \mid \beta ) = \frac { 1 } { \beta } e ^ { - x / \beta } I ( x > 0 ) $$

**Notation**: $X\sim \operatorname{exponential}(\beta)$. Note $\operatorname{exponential}(\beta)=\operatorname{gamma}(1,\beta)$

### Moments

$$ \begin{aligned} E ( X ) & = \beta \\ \operatorname { var } ( X ) & = \beta ^ { 2 } \end{aligned} $$

### MGF

$$ M _ { X } ( t ) = \frac { 1 } { 1 - \beta t } , \quad t < \frac { 1 } { \beta } $$

### CDF

$$ F _ { X } ( x ) = \left\{ \begin{array} { c c } 0 , & x \leq 0 \\ 1 - e ^ { - x / \beta } , & x > 0 \end{array} \right. $$

### Memoryless

The exponential distribution is the only continuous distribution that has this property

## Chi-squared

$$ f _ { X } ( x \mid p ) = \frac { 1 } { \Gamma \left( \frac { p } { 2 } \right) 2 ^ { p / 2 } } x ^ { \frac { p } { 2 } - 1 } e ^ { - x / 2 } I ( x > 0 ) $$

**Notation**: $X\sim \chi^2_p$ where $\chi_p^2=\operatorname{gamma}(p/2,2)$

### Moments

$$ \begin{aligned} E ( X ) & = p \\ \operatorname { var } ( X ) & = 2 p \end{aligned} $$


### MGF

$$ M _ { X } ( t ) = \left( \frac { 1 } { 1 - 2 t } \right) ^ { p / 2 }$$

## Non-Center Chi-squared

$$
\begin{aligned} X \mid Y & \sim \chi _ { p + 2 Y } ^ { 2 } \\ Y & \sim \operatorname { Poisson } ( \lambda ) \end{aligned}
$$

$$
\begin{aligned} f _ { X } ( x ) = \sum _ { y = 0 } ^ { \infty } f _ { X , Y } ( x , y ) & = \sum _ { y = 0 } ^ { \infty } f _ { X \mid Y } ( x \mid y ) f _ { Y } ( y ) \\ & = \sum _ { y = 0 } ^ { \infty } \frac { 1 } { \Gamma \left( \frac { p } { 2 } + y \right) 2 ^ { \frac { p } { 2 } + y } } x ^ { \frac { p } { 2 } + y - 1 } e ^ { - x / 2 } \left( \frac { \lambda ^ { y } e ^ { - \lambda } } { y ! } \right) \end{aligned}
$$

### Moments

$$
E ( X ) = E [ E ( X \mid Y ) ] = E ( p + 2 Y ) = p + 2 \lambda
$$

$$
\begin{aligned} \operatorname { var } ( X ) & = E [ \operatorname { var } ( X \mid Y ) ] + \operatorname { var } [ E ( X \mid Y ) ] \\ & = 2 p + 4 \lambda + 4 \lambda \\ & = 2 p + 8 \lambda \end{aligned}
$$

since 
$$
\begin{array} { l } E [ \operatorname { var } ( X \mid Y ) ] = E [ 2 ( p + 2 Y ) ] = 2 p + 4 \lambda \\ \operatorname { var } [ E ( X \mid Y ) ] = \operatorname { var } ( p + 2 Y ) = 4 \lambda \end{array}
$$

### MGF

$$
\begin{aligned} M _ { X } ( t ) = E \left[ \left( \frac { 1 } { 1 - 2 t } \right) ^ { \frac { p } { 2 } + Y } \right] & = \sum _ { y = 0 } ^ { \infty } \left( \frac { 1 } { 1 - 2 t } \right) ^ { \frac { p } { 2 } + y } \frac { \lambda ^ { y } e ^ { - \lambda } } { y ! } \\ & = e ^ { - \lambda } \left( \frac { 1 } { 1 - 2 t } \right) ^ { p / 2 } \sum _ { y = 0 } ^ { \infty } \frac { \left( \frac { \lambda } { 1 - 2 t } \right) ^ { y } } { y ! } \\ & = \left( \frac { 1 } { 1 - 2 t } \right) ^ { p / 2 } \exp \left( \frac { 2 \lambda t } { 1 - 2 t } \right) \end{aligned}
$$


## Weibull

$$ f _ { X } ( x \mid \gamma , \beta ) = \frac { \gamma } { \beta } x ^ { \gamma - 1 } e ^ { - x ^ { \gamma } / \beta } I ( x > 0 ) $$

**Notation:** $X\sim \operatorname{Weibull}(\gamma,\beta)$ where $\operatorname{weibull}(1,\beta)=\operatorname{exponential}(\beta)$

### Moments

$$ \begin{aligned} E ( X ) & = \beta ^ { 1 / \gamma } \Gamma ( 1 + 1 / \gamma ) \\ \operatorname { var } ( X ) & = \beta ^ { 2 / \gamma } \left[ \Gamma ( 1 + 2 / \gamma ) - \Gamma ^ { 2 } ( 1 + 1 / \gamma ) \right] \end{aligned} $$

### MGF

The mgf of $X$ exist only if $\gamma \ge 1$.

## Normal

$$ f _ { X } \left( x \mid \mu , \sigma ^ { 2 } \right) = \frac { 1 } { \sqrt { 2 \pi } \sigma } e ^ { - ( x - \mu ) ^ { 2 } / 2 \sigma ^ { 2 } } I ( x \in \mathbb { R } ) $$

**Notation**: $X\sim N(\mu,\sigma^2)$

### Moments

$$ \begin{aligned} E ( X ) & = \mu \\ \operatorname { var } ( X ) & = \sigma ^ { 2 } \end{aligned} $$

### MGF

Note $Z = \frac { X - \mu } { \sigma } \sim \mathcal { N } ( 0,1 )$, then $$ M _ { Z } ( t ) = E \left( e ^ { t Z } \right) = \int _ { \mathbb { R } } e ^ { t z } \frac { 1 } { \sqrt { 2 \pi } } e ^ { - z ^ { 2 } / 2 } d z = e ^ { t ^ { 2 } / 2 } $$

Where we use the fact $$ \int_{-\infty }^{\infty } e^{-z^2} \, dz=\sqrt{\pi} $$

Then we have $$ M _ { X } ( t ) = e ^ { \mu t } M _ { Z } ( \sigma t ) = e ^ { \mu t } e ^ { ( \sigma t ) ^ { 2 } / 2 } = e ^ { \mu t + \sigma ^ { 2 } t ^ { 2 } / 2 }  $$

## Beta

$$ f _ { X } ( x \mid \alpha , \beta ) = \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) \Gamma ( \beta ) } x ^ { \alpha - 1 } ( 1 - x ) ^ { \beta - 1 } I ( 0 < x < 1 ) $$

**Notation:** $X\sim \operatorname{beta}(\alpha,\beta)$. $\operatorname{beta}(1,1)=N(0,1)$



The expression $\frac { \Gamma ( \alpha ) \Gamma ( \beta ) } { \Gamma ( \alpha + \beta ) } = \int _ { 0 } ^ { 1 } x ^ { \alpha - 1 } ( 1 - x ) ^ { \beta - 1 } d x$ is also called **beta function** and denoted by $B(\alpha,\beta)$


### Moments

$$ \begin{aligned} E ( X ) & = \frac { \alpha } { \alpha + \beta } \\ \operatorname { var } ( X ) & = \frac { \alpha \beta } { ( \alpha + \beta ) ^ { 2 } ( \alpha + \beta + 1 ) } 
\\
E \left( X ^ { k } \right) & = \int _ { 0 } ^ { 1 } x ^ { k } \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) \Gamma ( \beta ) } x ^ { \alpha - 1 } ( 1 - x ) ^ { \beta - 1 } d x \\ & = \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) \Gamma ( \beta ) } \int _ { 0 } ^ { 1 } x ^ { \alpha + k - 1 } ( 1 - x ) ^ { \beta - 1 } d x \\ & = \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) \Gamma ( \beta ) } \frac { \Gamma ( \alpha + k ) \Gamma ( \beta ) } { \Gamma ( \alpha + k + \beta ) } \\ & = \frac { \Gamma ( \alpha + \beta ) \Gamma ( \alpha + k ) } { \Gamma ( \alpha ) \Gamma ( \alpha + \beta + k ) } 
\end{aligned} $$

## Cauchy

$$ f _ { X } ( x \mid \mu , \sigma ) = \frac { 1 } { \pi \sigma \left[ 1 + \left( \frac { x - \mu } { \sigma } \right) ^ { 2 } \right] } I ( x \in \mathbb { R } ) $$

**Notation:** $X\sim \operatorname{Cauchy}(\mu,\sigma)$



## Student's t distribution

Suppose $U\sim N(0,1)$ and $V \sim \chi_p^2$
$$
T=\frac{U}{\sqrt{V/p}}\sim t_p
$$

$$
f _ { T } ( t ) = \frac { \Gamma \left( \frac { p + 1 } { 2 } \right) } { \sqrt { p \pi } \Gamma \left( \frac { p } { 2 } \right) } \frac { 1 } { \left( 1 + \frac { t ^ { 2 } } { p } \right) ( p + 1 ) / 2 } I ( t \in \mathbb { R } )
$$

Suppose $X_{1:n}$ are iid $N(\mu,\sigma^2)$. then we have 
$$ Z = \frac { \bar { X } - \mu } { \sigma / \sqrt { n } } \sim \mathcal { N } ( 0,1 ) $$

and 

$$T = \frac { \bar { X } - \mu } { S / \sqrt { n } } = \frac { \sigma } { S } \left( \frac { \bar { X } - \mu } { \sigma / \sqrt { n } } \right) = \frac { \frac { \bar { X } - \mu } { \sigma / \sqrt { n } } } { \sqrt { \frac { ( n - 1 ) S ^ { 2 } } { \sigma ^ { 2 } } / ( n - 1 ) } }\sim t_{n-1}$$

## Moments

$$ \begin{aligned} E ( T ) & = 0 , \quad \text { if } p > 1 \\ \operatorname { var } ( T ) & = \frac { p } { p - 2 } , \quad \text { if } p > 2 \end{aligned} $$

## Snedecor's F distribution

Suppose $U\sim \chi_p^2$ and $V\sim \chi_q^2$, then $$ W=\frac{U/p}{V/q}\sim F_{p,q} $$

$$ f _ { W } ( w ) = \frac { \Gamma \left( \frac { p + q } { 2 } \right) } { \Gamma \left( \frac { p } { 2 } \right) \Gamma \left( \frac { q } { 2 } \right) } \left( \frac { p } { q } \right) ^ { p / 2 } \frac { w ^ { \frac { p } { 2 } - 1 } } { \left[ 1 + \left( \frac { p } { q } \right) w \right] ^ { ( p + q ) / 2 } } I ( w > 0 ) $$

Suppose $$ \begin{aligned} X _ { 1 } , X _ { 2 } , \ldots , X _ { n } & \sim \operatorname { iid } \mathcal { N } \left( \mu _ { X } , \sigma _ { X } ^ { 2 } \right) \\ Y _ { 1 } , Y _ { 2 } , \ldots , Y _ { m } & \sim \operatorname { iid } \mathcal { N } \left( \mu _ { Y } , \sigma _ { Y } ^ { 2 } \right) \end{aligned} $$

then 

$$ W = \frac { \frac { ( n - 1 ) S _ { X } ^ { 2 } } { \sigma _ { X } ^ { 2 } } / ( n - 1 ) } { \frac { ( m - 1 ) S _ { Y } ^ { 2 } } { \sigma _ { Y } ^ { 2 } } / ( m - 1 ) } = \left( \frac { S _ { X } ^ { 2 } } { S _ { Y } ^ { 2 } } \right) \frac { \sigma _ { Y } ^ { 2 } } { \sigma _ { X } ^ { 2 } } \sim F _ { n - 1 , m - 1 } $$

Note

1. If $X\sim_{p,q}$ then $\frac{1}{X}\sim F_{q,p}$
2. $X\sim t_q \implies X^2 \sim F_{1,q}$
3. $X\sim F_{p,q} \sim Y = \frac { \left( \frac { p } { q } \right) X } { 1 + \left( \frac { p } { q } \right) X } \sim \operatorname { beta } \left( \frac { p } { 2 } , \frac { q } { 2 } \right)$

### Moments

$$ \begin{array} { l } E ( W ) = \frac { q } { q - 2 } , \quad \text { if } q > 2 \\ \operatorname { ar } ( W ) = 2 \left( \frac { q } { q - 2 } \right) ^ { 2 } \frac { p + q - 2 } { p ( q - 4 ) } , \quad \text { if } q > 4 \end{array} $$



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