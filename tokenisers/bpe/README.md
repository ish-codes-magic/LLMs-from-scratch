# Byte Pair Encoding (BPE)
____


Byte-Pair Encoding (BPE) was introduced in [Neural Machine Translation of Rare Words with Subword Units (Sennrich et al., 2015)](https://arxiv.org/abs/1508.07909).


BPE works by repeatedly finding the most common pairs of characters in the text and combining them into a new subword until the vocabulary reaches a desired size. This technique helps in handling rare or unknown words by breaking them into smaller parts that the model has already learned during training. By reducing the vocabulary size, it makes it easier to work with large amounts of text while allowing the model to understand wide variety of languages.

## How Byte-Pair Encoding (BPE) works?

### Basic implementation

Suppose we have a text corpus with the following four words: "ab", "bc", "bcd" and "cde". We begin by calculating the frequencies of each byte (character). Initial vocabulary consists of all the unique characters in the corpus like {"a", "b", "c", "d", "e"}.

**Step 1: Initialize the vocabulary**

> Vocabulary = {"a", "b", "c", "d", "e"}

**Step 2: Calculate the frequency of each byte or character in the text corpus**

> Frequency = {"a": 1, "b": 3, "c": 3, "d": 2, "e": 1}

**Step 3: Find the most frequent pair of two characters**

Most frequent pair is "bc" with a frequency of 2.

**Step 4: Merge the pair to create a new subword unit.**

Merge "bc" to create a new subword unit "bc".

**Step 5: Update frequency counts of all the bytes or characters that contain the merged pair.**
Update the frequency counts of all the bytes or characters that contain "bc":

> Frequency = {"a": 1, "b": 1, "c": 1, "d": 2, "e": 1, "bc": 2}
"b"'s frequency decreases to 1 because the pair "bc" now represents both "b" and "c" together.
Similarly, "c"'s frequency drops to 1 as well.

**Step 6: Add the new subword unit to the vocabulary**
Add "bc" to the vocabulary:

>Vocabulary = {"a", "b", "c", "d", "e", "bc"}

**Repeat steps 3-6 until the desired vocabulary size is reached.**