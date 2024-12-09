# Translation Transformer Overview

*Note: This notebook is intended to used in Google Colab. Before proceeding, set your runtime type to a GPU such as "T4" for faster training.

In this homework, we will be building a simple sequence-to-sequence (seq2seq) model that translates simple English sentences and phrases into a simplified form of English spoken by very young children. This "toddler-speak" is comprised of

* Holophrastic Speech: The use of single words to represent entire thoughts or sentences (e.g., saying "milk" to mean "I want milk").

*  Protowords: Unique, invented words that toddlers use consistently to represent specific objects, actions, or desires (e.g., "baba" for "bottle").

* Simplistic Grammar: Only the most important words are used to convey the idea. For example "I want to watch a movie" becomes "Want see movie".

The model uses a Bidirectional and Auto-Regressive Transformer (BART) architecture that consist of both an encoder and decoder. The **encoder** in a BART model processes the input text bidirectionally, meaning it looks at the entire input sequence both forward and backward to create rich contextual representations of each token. The **decoder** in a BART model generates text auto-regressively, meaning it predicts the next token step by step based on the previously generated tokens. This is similar to how a generative pre-trained (GPT) model works.

Since this model translates a complex language to a simpler one illustrates the concepts of transformer-based models without the need for huge datasets such that we can train it within a reasonable amount of time to fit the scope of a homework assigment. We will be able to train the model with only 1000 examples, and then fine-tune the model with an additional 200 samples. The test set contains 50 samples. Each sample consists of a single short sentence. This allows us to set a smaller maximum sequence length the model can handle (max_position_embeddings) to speed up training. We also have a smaller vocabulary of around only 2000 words, which also speeds up training relative to larger translation models.

The **BLEU** (Bilingual Evaluation Understudy) score  will be our primary evaluation metric as it measures the overlap between the model's output and the reference translations. The BLEU score has been a standard metric for evaluating machine translation models, including transformer-based models. It provides a quantitative measure that allows for the comparison of different models and approaches. Researchers and practitioners often report BLEU scores to demonstrate the effectiveness of their translation models.


