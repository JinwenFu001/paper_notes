# Classical analysis of consistency and asymptotic distribution

## Consistency

There are two types of consistency results, one of which is to use the existence of $\hat\theta_n$ for each process $M_n(\theta)$ plus the uniform convergence of $M_n(\theta)$ towards $M(\theta)$ over any neighborhood $U$. We omit other relatively more trivial conditions like compact space here. This set of conditions is usually stronger than necessary, with some possible relief in the shape of objective, etc. The existence is usually ensured by semicontinuity, which in math is often used to guarantee the maximum of a function over a compact set, the math format is $\lim\sup_{x\to x_0}f(x)\le f(x_0)$. The uniform convergence is usually verified by the function class being Glivenko-Cantelli.

The other way is Wald's consistency, which is a different framework for proof with more essential conditions (from my personal perspective). It also allows convergence to a set of true values rather than only one. The most important condition is $E\sup_{\theta\in U} m_\theta(x)<\infty$ for each sufficiently small neighborhood $U$, it can also be hard to verify, see more details in Van der Vaart book ch5. 