# Optimization Methods

## 1st-Order
- **ADAM**: D. P. Kingma and J. Ba. Adam: A method for stochastic optimization. 2014

## 2nd-Order
- Natural Gradient:
	- Left multiplying inverse of Fisher Information Matrix
- **KFAC**: J. Martens and R. Grosse. Optimizing neural networks with kronecker-factored approximate curvature. 2015
	- Kronecker approximation to Fisher
- **FANG**: R. Grosse and R. Salakhudinov. Scaling up natural gradient by sparsely factorizing the inverse fisher
matrix.
	- Cholesky decomposition.
- **PRONG**: G. Desjardins, K. Simonyan, R. Pascanu, et.al. Natural neural networks. NIPS 2015
	- Whitening each layer.