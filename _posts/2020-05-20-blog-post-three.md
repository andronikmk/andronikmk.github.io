---
layout: post
title: Using PyTorch for Toxic Content Monitoring with FastText, FastAPI and Docker
cover-img: bitmap.png
tags: [social media, natural language processing, pytorch]
---

<p style="text-align: justify;">
In recent years tools for studying online behavior have increased in popularity in both industry and academia. One area of active study is negative online behavior, e.g. comments which are offensive enough that participants would be compelled to leave the conversation. Prior models were error prone and didn’t allow for stakeholders to pick the type of toxicity they were interested in finding, i.e. some models monitor profanity but not other types of offensive behavior. The following article presents a multi-headed model capable of detecting numerous types of toxicity, i.e. threats, obscenity, insults and identity based threats. The dataset used to train the model is provided by Wikipedia’s talk page edits. The following graphic is a breakdown of the dataset into various categories our model will be predicting
</p>

![boston](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/texic.png)

<p style="text-align: justify;">
The final model produced an F1 score of 0.753 and an ROC-AUC score of 0.987. I am using a Bi-directional LSTM + GRU neural network made with PyTorch, FastText vectorization, a FastAPI framework and deploying using a Docker image.
</p>

### PREPROCESSING
<p style="text-align: justify;">
The first step in building this model is data preprocessing. This includes creating multiple text files with a list of words most associated with a specific type of behavior which a comment is then assigned to. This includes comments which are interpreted as toxic, severely toxic, obscene, threatening, insulting and identity hate. The preprocessing of data was performed in three steps. First, making a dictionary with all of the words that falls into our categories. Second, writing a function that cleans the text by removing characters, user identification, and non-printable characters that can interfere with the models ability to make accurate predictions. The return value is a clean version of the string. A word splitting function is then used to account for words being hidden within normal text and a function that tokenizes the text and replaces associated characters with letters as well as adds spaces around punctuation marks. Finally, a function that does a variety of normalization steps such as separating punctuation marks and de-censoring before splitting words within a sentence into a list of words. The return value is a clean version of the string which is ready to be input into our model.
</p>

<script src="https://gist.github.com/andronikmk/688d24729068ddbc8671dbbe0a1e6b91.js"></script>

### MODEL

<p style="text-align: justify;">
The model uses PyTorch to make a Bi-directional LSTM + GRU neural network in combination with FastText vectorization. The metrics used to evaluate the results and the several other models that did not make the final cut are F1 and ROC-AUC scores. The AUC score represents the measure of separability, in this case, the difference between toxic and non-toxic behavior. ROC represents the probability curves. The following graphic shows all of the model that were made in an attempt to distinguish which tactic would result with the best results.
</p>

![models](https://raw.githubusercontent.com/andronikmk/andronikmk.github.io/master/img/modelsmodel.png)

<p style="text-align: justify;">
After numerous attempts at making Decision Tree Classifiers, Balanced Random Forest, Balanced Random Forest Classifiers, Logistic Regression and RUSBOOST with and without BERT, ELMO and TF-IDF encoding. It was a PyTorch Bi-Directional LSTM + GRU with dropout layer which randomly zeros out entire channels to effectively regularizes the network and FastText vectorization that produced the best F1 (0.753) and ROC-AUC (0.987) score for this project.
</p>

<script src="https://gist.github.com/andronikmk/11f02432efa38d365bec5a74d283fae0.js"></script>

### FRAMEWORK AND DEPLOYMENT

<p style="text-align: justify;">
The API uses FastAPI as the front-end framework and can be deployed via a Docker image locally or your choice of cloud service. FastAPI is a modern, fast, web-framework for building APIs with python 3.6+. It gives you very high-performance on par with NodeJS and Go.
</p>

<script src="https://gist.github.com/andronikmk/ff839c01e13400936fabbee681c60be3.js"></script>

<p style="text-align: justify;">
Finally, I will provide a link to a Docker image of the model which may deployed using the following command: docker run -p 8081:80 toxic-content-monitoring:0.1 after pulling the docker image to your local machine.
</p>

### CONCLUSION

<p style="text-align: justify;">
Although the results of the model are impressive the model is quite heavy and attempting to deploy it via a cloud service is rather costly. In addition, one area of further improvement could be to expand on the existing dataset provided via Wikipedia. Overall, I found that using PyTorch over TensorFlow for this particular application made for better results. FastText was a great open-source, free, lightweight library that allows users to learn text representations with low overhead and the FastAPI framework made for great frond-end access to test the model. Finally, I found that deploying the model from a Docker image made the results easy to reproduce and transport from my local machine to Google Cloud Platform.
</p>






