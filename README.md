# NaiveBayes-SpamFilter

## Goal
The goal of this project was to use a dataset containing spam and ham (this term is often used to refer to non spam) mails and create a classifier for spam or ham.
This was supposed to be achieved without using machine learning libraries or packages.

## Data Source
The dataset was obtained from [kaggle](https://www.kaggle.com/datasets/venky73/spam-mails-dataset).

## Results
* Function classify() to classify any string as spam or ham  
Input:
```py
classify('Hey, you won a car! Just call us and pick it up!')
```
Output:
```py
P(spam|mail): 5.362055682493099e-38
P(ham|mail): 2.86705569318837e-38
This is spam!
```

**Evaluation**

| Metric | Result |
| :--- | :----: |
| Accuracy | 0.54 |
| Accuracy with (total - no_classification) | 0.97 |
| Precision | 0.99 |
| Recall | 0.90 |
| F1 Score | 0.94 |

Explanation of *"Accuracy with (total - no_classification)"*:
Due to the nature of the algorithm a string cannot be classified as either spam or ham if the probability for both is the same.
Unfortunately this was the case for a lot of mails in the used dataset (total number of test cases: 1551; no classification: 685) which led to a low accuracy of ca. 54%.
If we were to desregard these mails, the classifier achieves an accuracy of 97%.

The precision of 99% is very good for a spam filter, because it means that *almost no mails that are in fact not spam and could be important would be filtered out*, leading to users not receiving important mails.
