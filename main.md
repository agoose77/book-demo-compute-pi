---
title: Computing Pi by RNG
short_title: Computing Pi
banner: banner.jpg
abstract: |
  Physicists have two favourite tools at their disposal: the <wiki:Fourier_Transform> and <wiki:Monte_Carlo_simulation>. In this paper, we'll use Monte Carlo techniques to compute an approximation to $\pi$.
---

There have been described many techniques for statistically computing an approximation for $\pi$, such as the <wiki:Buffon_Needle_Problem> or [estimating $\pi$ with a Coin](https://doi.org/10.48550/arxiv.2602.14487).

An intuitive approach is to consider the geometric problem of area sampling. In @fig-empty we can see the unit circle nested within a square whose sides have length two.

:::{figure} #empty-plot
:label: fig-empty
A schematic diagram depicting the areas of a regular square, and the unit circle that it bounds. Pi can be computed from the areas of these two primitives.
:::

If we consider the two regions `inside-circle` and `inside-square`, with areas $C$ and $S$ respectively, we would expect that a random point chosen within the square should have $P=\frac{C}{S}$ probability of falling within the circle. As such, we can observe many events in which a random point is selected, and compute $P$ in order to find $C$.

```{math}
:label: pi-calc
\begin{align*}

S &= 2\times 2 \\
C &= \pi\times 1^2 \\
\\
C &\approx 4\times \frac{C^\prime}{S^\prime}\,,
\end{align*}
```

where $C^\prime$ is the observed number of points within circle $C$, and $S^\prime$ is the number of points that were sampled altogether.

In @fig-scatter, a visual sample of 1 million Monte Carlo events is shown, in which the interior points are coloured yellow.

:::{figure} #scatter-plot
:label: fig-scatter
A scatter plot of random numbers drawn from $x,y\in[-1, 1)$
:::

:::{admonition} Result
:label: result
From the Monte Carlo simulation used to produce @fig-scatter, it was found that

![](#pi-result)
:::
