# Embedding, Dimension Reduction

## t-SNE series
- **t-SNE**: Laurens van der Maaten, Geoffrey Hinton. Visualizing Data using t-SNE, JMLR 2008
	- Original space p: Gaussian (x)
	- New space q: Student-t (y)
	- KL(P||Q) = sum p log(p/q)
	- SGD on y points to minimize
