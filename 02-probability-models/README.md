# Probability Model Theory and Simulation

![python](https://img.shields.io/badge/python-3.11%2B-306998?style=flat-square)
![status](https://img.shields.io/badge/status-academic%20project-d2691e?style=flat-square)

Theoretical comparison of the Poisson and Exponential distributions, validated through simulation and applied to a real-world scenario modeling cybersecurity intrusion attempts.

## Contents

1. **Theoretical comparison** — PMF/PDF, parameters, mean/variance, and how the rate parameter λ shapes each distribution. Poisson becomes increasingly symmetric as λ grows; Exponential retains a constant right-skew (skewness = 2) regardless of λ, with only its scale changing.
2. **Relationship to the Gaussian** — Poisson converges to Normal(λ, λ) as λ → ∞ via the Central Limit Theorem. Exponential doesn't converge directly, but connects to the Normal through two paths: as a special case of the Gamma distribution (sum of n Exponentials → Gamma(n, λ), which becomes Normal as n grows), and directly via the CLT applied to sample means.
3. **Simulation study** — 1,000 samples drawn at multiple parameter values for each distribution, comparing sample mean/variance against theoretical values. Poisson matched theory closely (errors of 0.4–7%); Exponential matched well on the mean but showed larger variance errors (4–24%), consistent with its heavier right tail amplifying the influence of extreme values.
4. **Application scenario** — a security team modeling night-shift cybersecurity intrusion attempts: hourly attack counts as a Poisson process (λ=5/hour) and interarrival times between attacks as Exponential (mean = 12 minutes). Simulated 1,000 hours of monitoring plus 1,000 interarrival times, both closely matching theoretical predictions.

## Key takeaways

- Poisson answers "how many events in a fixed interval"; Exponential answers "how long until the next event" — two views of the same underlying process, linked by a shared rate parameter λ.
- Both distributions' asymptotic Normal behavior justifies using Normal-based statistical methods even when the underlying data is discrete (Poisson) or skewed (Exponential), as long as sample sizes are large enough.

## Tools

Python, NumPy, SciPy, Matplotlib, Seaborn

## Running it

Open `poisson_exponential_comparison.ipynb` in Jupyter. Requires `numpy`, `scipy`, `matplotlib`, `seaborn` — no other dependencies.
