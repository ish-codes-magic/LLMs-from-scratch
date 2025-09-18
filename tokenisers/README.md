# What is tokenisation?

Tokenisation is a fundamental step in LLMs. It is the process of breaking down text into smaller subword units, known as tokens.

# Why is tokenisation required for processing textual data for LLMs?

Texts need to be represented as numbers in our models so that our model can understand. Tokenisation breaks down text into tokens, and each token is assigned a numerical representation, or index, which can be used to feed into a model.

To contextualize this a bit, let’s consider a simple sequence of words, with the final word missing:

> The quick brown fox jumped over the lazy ___

Reading this sentence, it’s clear to us what the words are. But to a computer, a block of text (a “string”) is just one long sequence of characters. By default, a computer program doesn’t know what a word is; for example, in Python, a string is actually represented by a series of Unicode characters. If we want a system to predict the next “element” in that sequence, we first have to decide what kind of thing those elements are and how to identify them in the text. Are the elements words? Individual characters?

A natural place to start is to chunk the sequence into words. In a language like English, written words are typically separated by spaces, so identifying the word boundaries is pretty straightforward (this is not the case in every language!). We can divide the string along each space character we find, producing a list of “words”.

We get the result something like this:

> ['The', 'quick', 'brown', 'fox', 'jumped', 'over', 'the', 'lazy']

That list of words is a Tokenisation of the sentence we started with. Each unit in that sequence is a token, which in this case corresponds to the words in that sentence. A language model can use those tokens to determine what token is most likely to come next. Technically, each token is assigned a different ID; in modern LLMs, these IDs map onto a token embedding, which in turn is fed into the LLM.

An example of token mappings to IDs may look like: 

> [1996, 4248, 2829, 4419, 5598, 2058, 1996, 13971]

Overall, Tokenisation is a crucial step for training a language model because it determines a model’s vocabulary. A language model needs to “know” how to process its input and what kinds of things it’s supposed to predict.

# Word-level vs character-level tokens


# Types of tokenisation

1. Naive Tokenization
2. Stemming and Lemmatization
3. Byte-Pair Encoding (BPE)
4. WordPiece
5. SentencePiece and Unigram



# References

1. <https://seantrott.substack.com/p/tokenization-in-large-language-models>
2. <https://www.ai21.com/knowledge/tokenization/>
3. <https://machinelearningmastery.com/tokenizers-in-language-models/>
4. <https://docs.mistral.ai/guides/tokenization/>