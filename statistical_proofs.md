<!-- Enable MathJax -->
<script type="text/javascript" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>


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
= \text{Var}_\theta(\hat{\theta}) + 0 + \text{Bias}_\theta(\hat{\theta}, \theta)^2
$$

$$
\Rightarrow \text{MSE}_\theta(\hat{\theta}) = \text{Var}_\theta(\hat{\theta}) + \text{Bias}_\theta(\hat{\theta}, \theta)^2
$$

**Interpretation:**  
MSE breaks into variance and squared bias, showing how an estimator’s error depends both on how much it fluctuates and how far its average is from the truth.
