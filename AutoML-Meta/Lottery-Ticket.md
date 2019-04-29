# Lottery Ticket

## Pruning in Training
- Jonathan Frankle, Michael Carbin. The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks. ICLR 2019
	- Randomly initialize a neural network.
	- Train the network for j iterations, reaching parameters.
	- Prune s% of the parameters, creating a mask m where Pm = (100 − s)%.
	- To extract the winning ticket, reset the remaining parameters to their values in θ0, creating the untrained network.
- Zhuang Liu, Mingjie Sun, Tinghui Zhou, Gao Huang, Trevor Darrell. Rethinking the Value of Network Pruning. ICLR 2019