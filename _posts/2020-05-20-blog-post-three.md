---
layout: post
title: Using PyTorch for Toxic Content Monitoring with FastText, FastAPI and Docker
tags: [social media, machine learning]
---

![cover](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/bitmap.png)

## INTROUDCTION
<p style="text-align: justify;">
In recent years tools for studying online behavior have increased in popularity in both industry and academia. One area of active study is negative online behavior, e.g. comments which are offensive enough that participants would be compelled to leave the conversation. Prior models were error prone and didn’t allow for stakeholders to pick the type of toxicity they were interested in finding, i.e. some models monitor profanity but not other types of offensive behavior. The following article presents a multi-headed model capable of detecting numerous types of toxicity, i.e. threats, obscenity, insults and identity based threats. The dataset used to train the model is provided by Wikipedia’s talk page edits. The following graphic is a breakdown of the dataset into various categories our model will be predicting
</p>

![boston](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/texic.png)

<p style="text-align: justify;">
The final model produced an F1 score of 0.753 and an ROC-AUC score of 0.987. I am using a Bi-directional LSTM + GRU neural network made with PyTorch, FastText vectorization, a FastAPI framework and deploying using a Docker image.
</p>


