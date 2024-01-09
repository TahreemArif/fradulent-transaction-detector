# Fraudulent Transaction Detector

## Problem Statement
Most of the time, a pattern for fraud transactions cannot be observed in credit card transactions; 
Therefore, it is very difficult for banking systems and electronic paymentsystems to detect fraudulent transactions.
Further, this is an extreme-rare event classification problem where positively labelled data is less than 1%.

### Dataset Overview
The dataset used for this project is [Synthetic Financial Datasets For Fraud Detection](https://www.kaggle.com/datasets/ealaxi/paysim1) taken from Kaggle.
This dataset contains the following features:
- step - maps a unit of time in the real world. In this case 1 step is 1 hour of time. Total steps 744 (30 days simulation).
- type - CASH-IN, CASH-OUT, DEBIT, PAYMENT and TRANSFER.
- amount - amount of the transaction in local currency.
- nameOrig - customer who started the transaction
- oldbalanceOrg - initial balance before the transaction
- newbalanceOrig - new balance after the transaction
- nameDest - customer who is the recipient of the transaction
- oldbalanceDest - initial balance recipient before the transaction. Note that there is not information for customers that start with M (Merchants).
- newbalanceDest - new balance recipient after the transaction. Note that there is not information for customers that start with M (Merchants).
- isFraud - This is the transactions made by the fraudulent agents inside the simulation. In this specific dataset the fraudulent behavior of the agents aims to profit by taking control or customers accounts and try to empty the funds by transferring to another account and then cashing out of the system.
- isFlaggedFraud - The business model aims to control massive transfers from one account to another and flags illegal attempts. An illegal attempt in this dataset is an attempt to transfer more than 200.000 in a single transaction

### AutoEncoder for Anomaly Detection
To approach this problem, I have used a simple dense layer autoencoder to build a rare event classifier.
The autoencoder approach for classification is similar to anomaly detection. In anomaly
detection, we learn the pattern of a normal process. Anything that does not follow this
pattern is classified as an anomaly. For a binary classification of rare events, we can use a
similar approach using autoencoders.

The whole process can be checked in the notebook
