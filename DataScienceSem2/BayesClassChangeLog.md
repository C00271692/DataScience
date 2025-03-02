1. After learning resources/templates i want to keep things consistant and also apply Naive Bayes algorith to my large dataset.

2. First problem Naive Bayes needs to classify by 2 classes and i do not have that in my dataet.

3. Decided to change the price field to instead of storing actual proice numeric value, to split it into 2 categories: 'Expensive' and 'Cheap', based on the average (median)

4. Usual defining features, tagrets, numeric, cat, data fields etc

5. Preprocessor (almost identical to those of KNN ) with the diference of our data beiong in dense format 'sparse_output=false' which will otherwise cause errors in the fitting

6. Create a Gaussian Pipeline

7. Split, Train, Test

8. Fit and make predixtion on a classification matrix:
Splitting the dataset...
Dataset split complete.
              precision    recall  f1-score   support

       cheap       0.90      0.71      0.80      2030
   expensive       0.76      0.92      0.83      1970

    accuracy                           0.82      4000
   macro avg       0.83      0.82      0.81      4000
weighted avg       0.83      0.82      0.81      4000