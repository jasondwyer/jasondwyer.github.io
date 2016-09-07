---
layout: post
title: Naive Bayes Text Classifier
---

Naive Bayes can be a useful tool for document classification. In short, the model can be trained with texts from known sources and then used to classify new documents from an unknown source. A classic use case for naive bayes is in spam filtering. By training the model with large data sets of spam and non-spam messages, the classifier can quite accurately determine if new emails are spam or not. This is based, largely, on the idea that spam messages tend to use similar words. I recently created a simple implementation of a naive bayes text classifier trained on JFK and MLK speeches. The [code](https://github.com/jasondwyer/simple-naive-bayes) is posted on github. 

*Note: The training texts supplied are simply for demo purposes and are quite small. Theoretically the model would perform much better with larger data sets.
