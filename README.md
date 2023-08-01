# Credit-Card-Fraud-Detection-using-AutoEncoders
With the rising volume and complexity of transactions, traditional fraud detection methods fall short in identifying fraudulent activities in real time. To tackle this pressing issue, machine learning techniques have proven to be invaluable in providing effective solutions.

This is part two of the Fraud Detection series.

This project aims to develop a Credit Card Fraud Detection Model using AutoEncoder Neural Networks.

## Features

By analyzing historical credit card transactions, this model aims to accurately identify fraudulent activities while minimizing false positives and negatives. In the previous part, I used Logistic Regression to detect fraudulent transactions. 

In this part, I am using AutoEncoder Neural Networks for fraud detection.

## Learnings

For a given input, an autoencoder predicts the same input. f(x)= x.

Autoencoders may seem a bizarre at first, but actually are very impactful.

You may wonder, how do we classify transactions as fraud or not using this autoencoder?

The answer is Reconstruction Error.

We train our autoencoder model only on non-fraudulent training data and get a reconstruction error on the no-fraudulent testing data.

To make our prediction, we define a threshold reconstruction error above which the transaction will be classified as fraud.

Then we calculate the reconstruction error on the data that we want to predict and classify it as fraudulent or not fraudulent by comparing the reconstruction error to the threshold.

How to decide the threshold?

This is more of a brute force method. You can tune this paramter using gridsearchcv and select the values which give the best accuracy on the validation dataset.

To put it in simple words, we gave a lot of one-class examples (normal transactions) to a model and it learned how to discriminate whether or not new examples belong to that same class.

## Results

The Logistic Regression Model is able to detect fraudulent credit card transactions with an accuracy of 80.34% and a recall of 0.51
