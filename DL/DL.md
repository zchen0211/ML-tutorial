# Deep Learning Models

## Tutorials
- Yann LeCun, Yoshua Bengio, and Geoffrey Hinton. Deep learning. nature, 521(7553):436, 2015.

## Books
- **Deep learning**: Ian Goodfellow, Yoshua Bengio, Aaron Courville, and Yoshua Bengio. volume 1. MIT press Cambridge, 2016.

## Dropout
- Nitish Srivastava, Geoffrey Hinton, Alex Krizhevsky, Ilya Sutskever, and Ruslan Salakhutdinov. Dropout: A simple way to prevent neural networks from overfitting. JMLR, 15:1929–1958, 2014
- Aidan N. Gomez, Ivan Zhang, Kevin Swersky, Yarin Gal, Geoffrey E. Hinton. Targeted Dropout. ICLR 2019
	- github.com/for-ai/TD

## Lottery Ticket (Pruning in Training)
- Jonathan Frankle, Michael Carbin. The Lottery Ticket Hypothesis: Finding Sparse, Trainable Neural Networks. ICLR 2019
	- Randomly initialize a neural network.
	- Train the network for j iterations, reaching parameters.
	- Prune s% of the parameters, creating a mask m where Pm = (100 − s)%.
	- To extract the winning ticket, reset the remaining parameters to their values in θ0, creating the untrained network.
- Zhuang Liu, Mingjie Sun, Tinghui Zhou, Gao Huang, Trevor Darrell. Rethinking the Value of Network Pruning. ICLR 2019


## Compression
- Song Han:
	- Song Han, Jeff Pool, John Tran, and William Dally. Learning both weights and connections for efficient neural network. In NIPS, 2015.
	- Song Han, Xingyu Liu, Huizi Mao, Jing Pu, Ardavan Pedram, Mark A Horowitz, and William J Dally. Eie: efficient inference engine on compressed deep neural network. In Computer Architecture (ISCA), 2016 ACM/IEEE 43rd Annual International Symposium on, 2016a.
	- Song Han, Huizi Mao, and William J Dally. Deep compression: Compressing deep neural networks with pruning, trained quantization and huffman coding. ICLR, 2016b.