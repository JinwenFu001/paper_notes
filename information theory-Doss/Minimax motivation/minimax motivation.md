## Optimal order 1 Kernel 

For Kernel density estimator $\hat p_n(x)=\frac{1}{nh}\sum_{i=1}^nK(\frac{x-x_i}{h})$ with a kernel $K(t)$ and bandwidth $h$, one can define the optimal Kernel $K^*$ and optimal bandwith $h^*$ by minimizing a metric called MISE(mean integrated square error).

Note on the KDE: usually have the following restrictions on the Kernels:

- $\int K^2(u)du<\infty$
- $\int u^2|K(u)|du<\infty$
- $S_K=\int u^2K(u)du\neq0$

And an order condition, order 1 if $\int uK(u)du=0$, sometimes also use order 2, and have other unnecessary conditions like symmetry.

The MISE is the summation of the bias and variance

Under the above conditions(with order 1 condition) and $p$ being smooth with absolutely continuous $p'$ and $\int [p''(x)]^2dx<\infty$, one can write
$$
\begin{align*}
MISE&=\mathbb E_p\int[\hat p_n(x)-p(x)]^2dx\\
&=[\underbrace{\frac{1}{nh}\int K^2(u)du}_{\text{variance}}+\underbrace{\frac{h^4}{4}S_K^2\int(p''(x))^2dx}_\text{bias}](1+o(1))
\end{align*}
$$
where the terms other than n and h are treated as constants. 

Restric $K$ to be **nonnegative Kernel**, one can always obtain Epanechnikov oracle MISE result with Epanechnikov Kernel $K^*(u)=\frac{3}{4}(1-u^2)_+$ and bandwidth $h^{MISE}(K)=\left(\frac{\int K^2}{nS_K^2\int (p'')^2dx}\right)^{1/5}$, Therefore $n^{4/5}MISE\to C$.

## The optimality definition is deficient

The conclusion is: If one further restrict Kernel to be order 2, but not necessarily nonnegative, she can always construct a choice of Kernel and bandwidth such that $n^{4/5}MISE\to0$, so the definition of the optimality is deficient.

Specifically, the Kernel can be any $K$ of order 2. For any $\epsilon>0$, let $h=n^{-1/5}\epsilon^{-1}\int K^2(u)du$, then both $\hat p_n$ and $\hat p_{n+}$ satisfy the above limitation. (So it also justifies the removal of nonnegative constraint.)

The magic lies in the the order 2 condition. For a fixed $p$, the order 2 condition, namely, the zero $S_K$ can remove the bias term in MISE, and let variance tend to zero by choosing a large $h$. But the magic is gone if we consider a class of $p$, thus motivates a minimax criterion.