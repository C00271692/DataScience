1. Found a good sample on kaggle to get me started with KNN algorithm.

2. Works fine out of the box, understanding the librarys and how to use the Algorithm.

3. Some key points:
    Must normalize the data (as float in this case), so the algorithm can take the correct input,
    K values has to be inputted manually, or implement a loop to try different combinations
    Plotting accuracy for different k values
    
---------------------------------------------------------------------------------------------------

4. Making KNN for my Large dataset, hopefully have more luck in KNN than i did for SVM
5. Frist thing have to define target (went for price as its numeric and makes most sense)
6. Need to split data into categorical and numeric
7. this part was difficult enough because i have to figure out how to preprocess numeric cols and categorical cols (translate into binary), and what to do with missing fields(average, or most frequent entry for that cell).
8. Create a pipeline (with a hard-coded k for now)
9. Thhen the usual splitting, training and predicting of our cols
10. this model takes again too long to process, so i decided to limit our data to 100,000  random rows for now
11. output the following:
Mean Squared Error: 192867090.44
R^2 Score: 0.64

Not too great results, might be able to get higher score if i can figure out how to use the full dataset