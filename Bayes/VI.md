# Variational Inference

## Basics:
- p(x) = sum_z p(x,z)
- EM:
	- E-step: p(z)
	- M-step: argmax_theta Q(theta, theta_old)
- MCMC:
	- Hard to do m-step, sample some z and average
- VI, ELBO:
	- KL(q(z) | p(z|x)) = E(log q(z)) - E(log p(z,x)) + log p(x)
	- ELBO(q) = E(log p(z, x)) - E(log q(z))

## Mean Field
- Variational Inference: A Review for Statisticians, 2018
	- David Blei
	- ELBO (Evidence Lower-Bound)

## SVGD
- Stein variational gradient descent: A general purpose bayesian inference algorithm, NIPS 2016
	- https://github.com/DartML/Stein-Variational-Gradient-Descent
