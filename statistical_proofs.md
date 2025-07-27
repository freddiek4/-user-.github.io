<!-- Enable MathJax -->
<script type="text/javascript" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>

## 1

$$
\text{MSE}_\theta(\hat{\theta}) = \mathbb{E}_\theta\left[ (\hat{\theta} - \theta)^2 \right]
$$

$$
= \mathbb{E}_\theta\left[ \left( \hat{\theta} - \mathbb{E}_\theta[\hat{\theta}] + \mathbb{E}_\theta[\hat{\theta}] - \theta \right)^2 \right]
$$

$$
= \mathbb{E}_\theta\left[ (\hat{\theta} - \mathbb{E}_\theta[\hat{\theta}])^2 + 2(\hat{\theta} - \mathbb{E}_\theta[\hat{\theta}])(\mathbb{E}_\theta[\hat{\theta}] - \theta) + (\mathbb{E}_\theta[\hat{\theta}] - \theta)^2 \right]
$$

$$
= \mathbb{E}_\theta\left[ (\hat{\theta} - \mathbb{E}_\theta[\hat{\theta}])^2 \right] + 2(\mathbb{E}_\theta[\hat{\theta}] - \theta) \cdot \mathbb{E}_\theta\left[ \hat{\theta} - \mathbb{E}_\theta[\hat{\theta}] \right] + (\mathbb{E}_\theta[\hat{\theta}] - \theta)^2
$$

$$
= \mathbb{E}_\theta\left[ (\hat{\theta} - \mathbb{E}_\theta[\hat{\theta}])^2 \right] + 2(\mathbb{E}_\theta[\hat{\theta}] - \theta) \cdot 0 + (\mathbb{E}_\theta[\hat{\theta}] - \theta)^2
$$

$$
= \text{Var}_\theta(\hat{\theta}) + 0 + \text{Bias}_\theta(\hat{\theta}, \theta)^2
$$

$$
\Rightarrow \text{MSE}_\theta(\hat{\theta}) = \text{Var}_\theta(\hat{\theta}) + \text{Bias}_\theta(\hat{\theta}, \theta)^2
$$

**Interpretation:**  
MSE breaks into variance and squared bias, showing how an estimator’s error depends both on how much it fluctuates and how far its average is from the truth.





$$
\mathbb{E}_p[f(X)] = \int f(x)p(x)\,dx = \int f(x) \frac{p(x)}{q(x)} q(x)\,dx = \mathbb{E}_q\left[ f(X) \frac{p(X)}{q(X)} \right]
$$

$$
\hat{\mu}_{\text{IS}} = \frac{1}{n} \sum_{i=1}^n f(X_i) \cdot \frac{p(X_i)}{q(X_i)}, \quad X_i \sim q
$$

$$
\text{Let } f(x) = x
$$

$$
\mu_{\text{Germany}} = \mathbb{E}_p[x] = \int x \cdot p(x)\,dx = \int x \cdot \frac{p(x)}{q(x)} \cdot q(x)\,dx = \mathbb{E}_q\left[x \cdot \frac{p(x)}{q(x)}\right]
$$

$$
\hat{\mu}_{\text{Germany}} = \frac{1}{n} \sum_{i=1}^n X_i \cdot \frac{p(X_i)}{q(X_i)}, \quad X_i \sim \text{U.S.}
$$

$$
\mu_{\text{U.S.}} = \mathbb{E}_q[x] = \int x \cdot q(x)\,dx = \int x \cdot \frac{q(x)}{p(x)} \cdot p(x)\,dx = \mathbb{E}_p\left[x \cdot \frac{q(x)}{p(x)}\right]
$$

$$
\hat{\mu}_{\text{U.S.}} = \frac{1}{n} \sum_{i=1}^n X_i \cdot \frac{q(X_i)}{p(X_i)}, \quad X_i \sim \text{Germany}
$$

**Interpretation:**  
Monte Carlo Importance sampling reweights samples drawn from one distribution to estimate expectations under another.

$$
\text{Example:} \quad \text{Suppose average income in Germany is } \mathbb{E}_p[x], \text{ and we sample from the U.S. } q(x).
$$

$$
\text{Let } X_1 = 30,\ X_2 = 50,\ X_3 = 70 \text{ (in thousands, sampled from U.S.), and weights } \frac{p(X_i)}{q(X_i)} = 1.5,\ 0.8,\ 0.6.
$$

$$
\hat{\mu}_{\text{Germany}} = \frac{1}{3} \left(30 \cdot 1.5 + 50 \cdot 0.8 + 70 \cdot 0.6\right) = \frac{1}{3} (45 + 40 + 42) = \frac{127}{3} \approx 42.33
$$

$$
\text{We adjust each U.S. sample by how likely it is under Germany’s distribution to approximate Germany’s mean income.}
$$
















