## R.1

$$
rank(AB)\le\min(rank(A),rank(B))
$$

## R.2

$$
A=BC \Longrightarrow \mathcal{C}(\mathbf{A}) \subseteq \mathcal{C}(\mathbf{B})\\
\mathcal{C}(\mathbf{A}) \subseteq \mathcal{C}(\mathbf{B})\Longrightarrow \exist C, A=BC
$$

## R.3

$$
rank(A)=n=r\Longrightarrow \mathcal{N}(A)=\{0\}
$$

## T.1

$$
\dim(\mathcal{N}(A))+\dim(\mathcal{C}(A))=n
$$

## R.4

Ler $\mathcal{S}$ and $\mathcal{T}$ be orthogonal complements in $R^m$, then
$$
\forall x\in R^m, \exist s\in \mathcal{S},t\in \mathcal{T}, x=s+t
$$

such decomposition is unique.

## R.5

$$
\mathcal{C}(A)+\mathcal{N}(A^T)=R^m
$$

## R.6

If $\mathcal{S_1}$ and $\mathcal{T_1}$ are orthogonal complements, as well as $\mathcal{S_2}$ and $\mathcal{T_2}$, then 
$$ \mathcal{S_1} \subseteq \mathcal{S_2}\Longrightarrow \mathcal{T_2}\subseteq\mathcal{T_1} $$ 

## R.7

For two vector space $\mathcal{S}$ and $\mathcal{T}$
$$( S\subseteq T)  \wedge (\dim \mathcal{S}=\dim\mathcal{T}=k) \Longrightarrow \mathcal{S}=\mathcal{T}$$

## R.8

$$ \mathbf{A}\mathbf{x}+\mathbf{b}\equiv0\Longrightarrow \mathbf{A}=0,\mathbf{b}=0 $$

## C.1

$$ \mathbf{B}\mathbf{x}\equiv\mathbf{C}\mathbf{x}\Longrightarrow\mathbf{B}=\mathbf{C} $$

## C.2

if $rank(A)=n=r$
$$ \mathbf{AB}=\mathbf{AC}\Longrightarrow{B=C} $$

## L.1

$$ \mathbf{C^TC=0}\Longrightarrow\mathbf{C=0} $$

## R.9

A system of equations $\mathbf{Ax=c}$ is consistent iff $c\in \mathcal{C}(A)$

## R.10

If $\mathbf{A}$ can be partitioned as $A=\left[\begin{array}{ll}
\mathbf{C} & \mathbf{D} \\
\mathbf{E} & \mathbf{F}
\end{array}\right]$
where $rank A = rankC=r$, and $\mathbf{C}$ is nonsingular. Then $G=\left[\begin{array}{ll}
\mathbf{C^{-1}} & 0 \\
0 & 0
\end{array}\right]$
is  a generalized inverse of A

## C.3

If $\mathbf{A}$ can be partitioned as $A=\left[\begin{array}{ll}
\mathbf{C} & \mathbf{D} \\
\mathbf{E} & \mathbf{F}
\end{array}\right]$
where $rank A = rankF=r$, and $\mathbf{F}$ is nonsingular. Then $G=\left[\begin{array}{ll}
0 & 0 \\
0 & \mathbf{F^{-1}}
\end{array}\right]$
is  a generalized inverse of A

## R.11

There exist $\mathbf{P}$ and $\mathbf{Q}$ such that 
$$ \mathbf{PAQ}=\left[\begin{array}{ll}
\mathbf{C} & \mathbf{D} \\
\mathbf{E} & \mathbf{F}
\end{array}\right] $$
where $rank A=rank C=r$ and $\mathbf{C}$ is nonsingular. Then $A$ has generalized inverse
$$ G=Q\left[\begin{array}{ll}
\mathbf{C^{-1}} & 0 \\
0 & 0
\end{array}\right]P $$

## R.12

If $\mathbf{Ax=c}$ is a consistent system, $\mathbf{A^gc}$ is a solution to it.

## R.13

For a consistent system $\mathbf{Ax=c}$, $\widetilde{x}$ is a solution iff
$$ \exist\mathbf{z} \quad \widetilde{x}=\mathbf{A^gc+(I-A^gA)z} $$

## R.14

$AA^g$ is a projection onto $\mathcal{C}(A)$

## R.15

$(\mathbf{I-AA^g})$ is a projection onto $\mathcal{N}(A^T)$

## R.16

Projection matrix onto vector space $\mathcal{S}$ is unique.

## C.4

If $\mathbf{P}$ projects onto $\mathcal{S}$, then $\mathbf{I-P}$ projects onto its orthgonal complements, that is $\mathcal{N}(\mathbf{P})$

## R.17

$$
trace(AB)=trace(BA)\\
trace(A^TA)=\sum_i\sum_j A_{ij}^2
$$

##  R.18

$$
det
\left[
\begin{array}{l}
a&b\\
c&d
\end{array}

    \right
]=ad-bc
$$

 $$ |AB|=|A||B| $$
 $$ |A|^{-1}=\frac{1}{|A|} $$
 $$ |cA|=c^n A\quad \text{Where $\mathbf{A}$ is $n\times n$}$$
 $$ \operatorname{det}\left(\left[\begin{array}{ll}
\mathbf{A} & \mathbf{B} \\
\mathbf{C} & \mathbf{D}
\end{array}\right]\right)=|\mathbf{A}|\left|\mathbf{D}-\mathbf{C A}^{-1} \mathbf{B}\right|=|\mathbf{D}|\left|\mathbf{A}-\mathbf{B D}^{-1} \mathbf{C}\right| $$ 

## R.19

For symmetric $n\times n$ matrix $\mathbf{A}$, the number of nonzero eigenvalues is equal to its rank.

## R.20

Matrix $\mathbf{A}$ is positive definite iff there exist a nonsingular lower triangular matrix $L$ such that $\mathbf{A=LL^T}$





# Exercise

## A.12

If $x,y\in\mathcal{N}(A)$, then
$$
A(x+y)=Ax+Ay=0\Rightarrow (x+y)\in \mathcal{N}(A)\\
Aax=aAx=0\Rightarrow ax\in \mathcal{N}(A)
$$

## A.15

use
$$ \mathcal{C}(BC)\subseteq\mathcal{C}(B) $$

## A.16

use $F^{-1}$

## A.22

$$ AGA=A \Rightarrow A^T G^T A^G=A^G$$

## A.23

$$ A(G+G^T)A=AGA+A^T G^T A^G=A+A $$

## A.24

$A^i$ where $i$ is natural number

## A.32

$$ AA^{+}A=A(A^TA)^{-1}A^TA=PA=A \\
A^{+}AA^{+}=(A^TA)^{-1}A^TA(A^TA)^{-1}A^T=(A^TA)^{-1}A^T=A^{+}\\
AA^{+}=A(A^TA)^{-1}A^T\\
A^{+}A=(A^TA)^{-1}A^TA=I

## A.33

$$
AA^{+}A=AA^T(AA^T)^{-1}A=A\\A^{+}AA^{+}=A^T(AA^T)^{-1}AA^T(AA^T)^{-1}=A^T(AA^T)^{-1}=A^{+}\\AA^{+}=AA^T(AA^T)^{-1}=I\\A^{+}A=A^T(AA^T)^{-1}A=P
$$

## A.36

$$ \mathbf{(I-P)^2=I^2+P^2-2P=I-P} $$
Actually, $\mathbf{I-P}$ is also a projection matrix.

## A.42

$\mathbf{A}$ can be decompose as 
$$ A=Q\Sigma Q^T $$
hence
$$ |A|=|Q||\Sigma||Q^T|=|\Sigma|=\prod \lambda_i $$

## A.43

$$ trace(\mathbf{A})=trace(Q\Sigma Q^T )=trace(QQ^T\Sigma)=trace(\Sigma)=\sum \lambda_i $$

## A.44

Consider matrix:
$$
\operatorname{det}\left(\left[\begin{array}{ll}
\mathbf{I_m} & \mathbf{-A} \\
\mathbf{B^T} & \mathbf{I_n}
\end{array}\right]\right)
$$
then we obtain what we what.

## A.49

For the eigen values of $AA^T$:
$$ AA^Tx=\lambda x $$
We can see:
$$ A^TAA^Tx=A^T\lambda x $$
hence $\lambda$ is also eigenvalus of $A^TA$ with eigenvector$A^Tx$
$$  $$

## A.50

a.
As shown above

b,c,d

Because $Av_i$ is also eigenvector of $AA^T$, so we just need to prove:
$$ ||Av_i||=\lambda_i^2 u_i \Rightarrow \frac{v_i^TA^TAv_i}{\lambda_i^2}=u_i $$
Note $A^TA$ can be decomposed as 
$$
A^TA=V\Lambda^2 V^T 
$$
hence
$$
\Lambda^{-1}V^TA^TAV\Lambda^{-1}=I
$$

e.
$$  $$