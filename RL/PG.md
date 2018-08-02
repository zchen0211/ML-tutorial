# Policy Gradient

## Classic
- On-Policy
- Better Convergence
- Effective in high-dimensional or continuous action spaces
- Can learn **stochastic** policies

## Off-Policy
- Importance-Sampling

## Legacy
- Williams (1992). Simple statistical gradient-following algorithms for connectionist
reinforcement learning: introduces REINFORCE algorithm
- Baxter & Bartlett (2001). Infinite-horizon policy-gradient estimation: temporally decomposed policy gradient (not the first paper on this! see actor-critic section later)
- Peters & Schaal (2008). Reinforcement learning of motor skills with policy gradients: very accessible overview of optimal baselines and natural gradient

## Latest
- Levine & Koltun (2013). Guided policy search: deep RL with importance sampled policy
gradient (unrelated to later discussion of guided policy search)
- Schulman, L., Moritz, Jordan, Abbeel (2015). Trust region policy optimization: deep RL with natural policy gradient and adaptive step size
- Schulman, Wolski, Dhariwal, Radford, Klimov (2017). Proximal policy optimization algorithms: deep RL with importance sampled policy gradient

- High-dimensional continuous control with generalized advantage estimation, Schulman et al. ‘16
- Trust region policy optimization with value function approximation