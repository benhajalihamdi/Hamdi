---
tags:
  - AI
aliases:
  - NLP
date/time: 2026-03-30 21:09
Date /Time: "{date} {time}"
title:
draft: true
---
splits into multiple categories: 
- Classification
- Multi Classification 
- Generation
Classification like Sentiment extraction, intent detection, language detection, topic modeling 
Multi Classification: Dependency parsing, constituency parsing, part of speech tagging 

Goal: Go through the tasks one by one:
## Sentiment Extraction task 
Datasets:

We want the model to predict the sentiment of a sentence / phrase:
the way we evalue such outputs by using traditional evaluation metrics 
- accuracy:% of observations that were correctly predicted 
- Precision:% of predicted positive that were correct
- Recall:% of all true labels were correctly predicted 
- F1 score: harmonic mean of precision and recall

## Named Entity recognition 
identifying the category of given words 
datasets Annotated Reuters newspaper(CoNLL)

## Machine translation 
Datasets: WMT'1
evaluation metrics 
- BLEU: quality of text translated similar to precision
- ROUGE quality of text generated similar ro recall 
- Perplexity: quantifies how surprised the model is to see some words together 

# [[TOKENIZATION]] 
Models doesn't understand text: 
"A cute teddy bear is reading" 
-> To pass this sentence to a model we have to cut this text in respect of an unit of text: (unit of text is called a token)
some way:
- arbitrary 
- words: However some words "bear" and "bears" would be considered different even though they are efficiently the same Pros: simple but risk of OOV(not knowing the word)
- sub-word: leveraging roots of words: however the sequence would be longer because the complexity of this model is a function of sequence length
- a Caracter level: take much more time to process because to sequence length, also representations of letter is harder
# TOKEN REPRESNTATION 
the simple and naive way to do it is to assign a one heart encoding vector ([[OHD encoding]]). However we want to compare these tokens. Common way we may use is [[Cosine Similarity]].
for similar tokens they have high cosine similarity (the angle between the vectors is smaller)
[[Word2vec]] paper is a way to make sense to embeddings 
- Continues bag of words, levergae text that we have and try predict the target word 
- skip-gram from target word try to predict the words around it 
the goal is to learn a representation of these word that is meaningful.


