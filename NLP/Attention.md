# Attention, Transformer

## Transformer
- Attention is all you need:
	- A very good intro: http://jalammar.github.io/illustrated-transformer/
	- Explanation with Pytorch: http://nlp.seas.harvard.edu/2018/04/03/attention.html
	- https://github.com/Kyubyong/transformer
	- Pytorch: https://github.com/jadore801120/attention-is-all-you-need-pytorch
- **ELMO**: Matthew E. Peters, Mark Neumann, Mohit Iyyer, Matt Gardner, Christopher Clark, Kenton Lee, Luke Zettlemoyer. Deep contextualized word representations. NAACL 2018
	- https://allennlp.org/elmo
	- ELMo (Embeddings from Language Models)
	- bidirectional LSTM, predict next/last word
- Rami Al-Rfou, Dokook Choe, Noah Constant, Mandy Guo, Llion Jones. Character-Level Language Modeling with Deeper Self-Attention. 2018
	- 64 transformer layers (deep, multi-head self-attention + fc x 2);
	- Mask for causal attention;
	- Auxiliary loss:
		- Multiple prediction (predict every character in the sequence)
		- Intermediate layer losses (deep supervision)
		- Multiple targets
	- 235 million parameters, dropout (0.55)