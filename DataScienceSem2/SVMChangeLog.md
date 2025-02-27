1. looking for dataset, actually proved to be more difficult that expected, wiht huge amounts of datasets available online.

2. Chose a decent dataset with ~50k rows, 16 columns, not too large but not too small. Mainly categorical data, with the target (salary) being a string also (rather than int), beacuse of  < > = signs

3. Dataset comes undefined, manually have to assign column names.

4. beacuse dataset is categorical, we have to translate into numerical features and encoding the categoriacl features into an appropriate format for model training.

5. splitting into test, and train and generate precision matirx:
              precision    recall  f1-score   support

       <=50K       0.88      0.94      0.91      4942
        >50K       0.77      0.60      0.68      1571

    accuracy                           0.86      6513
   macro avg       0.83      0.77      0.79      6513
weighted avg       0.86      0.86      0.85      6513


>50k has a relitavely low precision @ 77% and recall and f-1 scores... why?

6. Found a Large dataset (818457 entries, 32 columns)

7. New Large Dataset contains 'NaN' fields, need to remediate this.

8. Running SVM Large dataset, finding... took over 235+ minutes to process, unfeesable.

9. setting up to use GPU acceleration

10. First issue my laptop has 2 GPU's, integrated gpu in the processor and a dedicated nvidia GPU. On Linux have to install official nvidia driver to use dedicated GPU