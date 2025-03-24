# Understanding Large Language Models

## What is an LLM?

> [!quote] Large Language Models (LLMs)
> "An LLM is a neural network designed to understand, generate, and respond to human-like text. These models are deep neural networks trained on massive amounts of text data, sometimes encompassing large portions of the entire publicly available text on the internet" (p. 2).

- ***Large*** has a double meaning:
	- The massive amounts of training data.
	- The massive amounts of parameters the models possess (tens to hundreds of billions).
### Creating an LLM

#### Pretraining
- ***Pretraining*** is the phase initial training phase where the model is trained on a very large, diverse, dataset to get a "broad understanding of language" (p. 6).
	- It learns to predict the next word in a text (p. 7).
- During pretraining, the LLM observes and learns from raw unlabeled texts (trillions of tokens) from sources like the internet, books, Wikipedia, and research articles.
	- LLMs are ***self-supervised*** learners.
- After pretraining, the LLM becomes a ***foundational (base) model*** with text completion and few-shot learning capabilities.
#### Fine-tuning
- The refinement of a ***pretrained*** model through further training on a specific task using a narrower, domain-specific, dataset.
	- Classification, summarization, translation, personal assistants, etc.
- The fine-tuning data will be labeled.
##### Instruction Fine-Tuning
- Labeled data has ***instruction*** and ***answer*** pairs.
	- This can be used for translation (e.g., English to Spanish), or tasks like querying (e.g., questions and answers).
##### Classification Fine-Tuning
- Labeled data has texts and associated class labels (e.g., conventional classification tasks).

---
## The Transformer Architecture 

- The transformer architecture was famously introduced in the 2017 paper, "Attention is All You Need" (https://arxiv.org/abs/1706.03762).
- Consists of sub-modules: an ***encoder*** and a ***decoder***.
	- The ***encoder*** encodes text in a numerical vector that captures contextual information from the input.
	- The ***decoder*** uses ("decodes") the encoded vectors to produce the output (e.g., translated text in a translation task).
- Encoders and decoders have several layers connected by the ***self-attention mechanism***.
- The ***self-attention mechanism*** "allows the model to weigh the importance of different words or tokens in a sequence relative to each other" and to "capture long-range dependencies and contextual relationships within the input data" (p. 7).
	- This is a key reason why the generated outputs are so relevant and coherent.
### BERT (Bidirectional Encoder Representations from Transformers)
- Built on the ***encoder*** module of the transformer.
- BERT uses a ***masked word prediction*** training task.
	- *i.e.*, the model learns to predict a masked (hidden) word in a sentence (words are randomly masked during training).
- Masked word prediction makes BERT suitable for text classification tasks.
### GPT (Generative Pretrained Transformers)
- GPT models focus on the ***decoder*** module of the transformer, and is designed for generating text (e.g., machine translation, summarization, writing, code generation, etc.).
	- GPT was introduced by OpenAI (https://cdn.openai.com/research-covers/language-unsupervised/language_understanding_paper.pdf).
	- GPT models are "self-labeling" during the next-word prediction training task: labels are "created on the fly" (p. 12), as the model is trained to predict the next word based on the words it has thus far seen.
- GPT models are trained on incomplete texts and learn to predict the next token.
	- GPT models produce tokens one at a time.
	- They are ***autoregressvie***: they use their previous outputs as inputs into next token prediction.
- Even though they focus on text generation, GPT models have shown versatility in ***zero-shot*** and ***few-shot*** learning tasks.
	- They have ***emergent behavior***, such as being able to perform translation even though they only user transformer decoder blocks.