# Deep Learning Models

## Tutorials
- Yann LeCun, Yoshua Bengio, and Geoffrey Hinton. Deep learning. nature, 521(7553):436, 2015.

## Books
- **Deep learning**: Ian Goodfellow, Yoshua Bengio, Aaron Courville, and Yoshua Bengio. volume 1. MIT press Cambridge, 2016.

## Dropout
- Nitish Srivastava, Geoffrey Hinton, Alex Krizhevsky, Ilya Sutskever, and Ruslan Salakhutdinov. Dropout: A simple way to prevent neural networks from overfitting. JMLR, 15:1929–1958, 2014

## Lottery Ticket
- Jonathan Frankle, Michael Carbin. The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks. ICLR 2019
	- Randomly initialize a neural network.
	- Train the network for j iterations, reaching parameters.
	- Prune s% of the parameters, creating a mask m where Pm = (100 − s)%.
	- To extract the winning ticket, reset the remaining parameters to their values in θ0, creating the untrained network.