# Attention, Transformer

## Transformer
- Attention is all you need:
	- https://github.com/Kyubyong/transformer
	- Pytorch: https://github.com/jadore801120/attention-is-all-you-need-pytorch
- Rami Al-Rfou, Dokook Choe, Noah Constant, Mandy Guo, Llion Jones. Character-Level Language Modeling with Deeper Self-Attention. 2018
	- 64 transformer layers (deep, multi-head self-attention + fc x 2);
	- Mask for causal attention;
	- Auxiliary loss:
		- Multiple prediction (predict every character in the sequence)
		- Intermediate layer losses (deep supervision)
		- Multiple targets
	- 235 million parameters, dropout (0.55)