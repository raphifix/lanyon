---
published: false
---
- Introduction/Motivation

One of the key goals in natural language processing is understanding the relationship among words and phrases. Understanding the context in which words and phrases occur can be a great help for text classification, sentiment analysis, query expansion, and other language processing tasks.

I am currently utilizing them for a named entity recognition problem, which inspired me to make this post.

- How are word vectors created

Two popular models for building word vectors are continuous bag of words (CBOW) and skipgram.

-CBOW takes in a user-defined window of words on both sides of the target word in order to predict the target word. _In other words, CBOW attempts to predict a word given a context._
-Skipgram takes in a single word and tries to predict words surrounding the input word. _In other words, skipgram attempts to predict a context given a word._

This is a very high-level description of these methods. If you're interested in learning more about these and other methods for building word embeddings, [here](https://lilianweng.github.io/lil-log/2017/10/15/learning-word-embedding.html) is a good place to start.

Both approaches involve a single-layer neural network to calculate the word vectors. Unlike in other neural net setups where the output layers is the layer of interest, the weights in the _hidden layer_ instead represent the embedded space.

- data cleaning in r

Getting the President's tweets was fairly straightforward thanks to the [Trump Twitter Archive](http://www.trumptwitterarchive.com/archive). I used a pipe delimiter to avoid conflicts within the tweets.

I decided to stick to basic text preprocessing for this task:
1.Removing punctuation
2.Lemmatizing the strings: converting all words to their base form. E.g. is, am, are -> be
3.Removing stop words: common words that typically do not add any information to text analytics tasks

```{r}
library(textstem)
library(qdap)

trump_tweets <- read.csv('~/Documents/trump_tweets.txt', sep = '|', quote = "", row.names = NULL, stringsAsFactors = F)
trump_tweets$text <- gsub('[[:punct:] ]+',' ',trump_tweets$text)
trump_tweets$text <- lemmatize_strings(trump_tweets$text)
trump_tweets$text <- rm_stopwords(trump_tweets$text, separate = FALSE)
```
- model running from command line
- examples
- further exploration