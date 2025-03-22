##PLEASE NOTE##
The provided dataset is too large to push into GitHub so I will provide a link to it.
It is a very large dataset (4.56GB), and the algorith will NOT work without it as the filepaths are hardcoded very specifically
Link to dataset: https://www.kaggle.com/datasets/debashishsau/aslamerican-sign-language-aplhabet-dataset

This project is set up in accorance to my machine (using Nvidia GPU with 12.8 gb VRAM, on a Linux Operating System). So certain reconfigurations/sizing changes may be neccessary depending on your setup.

The dataset has 2 subfolders 1. train, 1. test
The Train (main and biggest) dataset directory is then subcategorized by its corresponding alphabetical value (A, B, C, Space, etc)
The Test dataset has the test samples out freely with the .JPG file title corresponding to its alphabetical value

#####################################################################################################################################


1. Majour issues attempting to install tensorflow on linux

2. After many hours found that tensorflow (library required for advanced neural netwrok packages, etc)
Doesnt work with latest python version, only older version 3.12

3. Setup a virtual environment with the older version of python 

4. Looking for datasets

5. Found a sign lang dataset with 223k files (4.56 GB)

6. Setup a CNN algorith using tensorflow package

7. By default tensorflow is only configured to use CPU, using manual figured out to ensure the algo 
uses my Nvidid GPU for training (should be a lot quicker and efficient)

8. Using GPU we can process in big "batches", and higher image quality, ensuring we capture more details
for each image that we train the aglo on

9. So far have a working algorithm as far as training the dataset using Nvidia GPU processing

10. Setting up a seperate file for Tests (as the train algorithm is getting very long already)

11. Save the previous train results as a .h5 file to read from the new Test file

12. Using Nvidia acceleration, with batch size of 256 across 10 epochs, the model trained in 39 minutes and 32 seconds
achieving accuracy: 0.8633 - loss: 0.4276 - val_accuracy: 0.7807 - val_loss: 1.0584 - learning_rate: 0.0010 on the last epoch (for Relu)

13. This was achieved using hte RELU activation function

14. For learning purposes now i will try training our CNN with a sigmoid activation function and compare results such as processed time and accuracy

15. Sigmoid af results: 
0m 127ms/step - accuracy: 0.0273 - loss: 3.3959 - val_accuracy: 0.0365 - val_loss: 3.3628 - learning_rate: 0.0010

Such a low accuracy basically means our model didnt learn anything. This is probably mainly due to vanishing gradient which is a common issue with the sigmoid. It is safe to say this activation function doesnt work with our CNN model. 

16. Tried Sigmoid again but with slight alterations:
patience increase (doubled for simplicity)
added a smaller learning rate of 0.0001
decided to keep the main block architecture the same as Relu handled this one very well so i see no need to re-engineer the block for sigmoid

17. Adding these changes added 0.02 difference to the accuracy, but still our model doesnt learn pretty much anything and that increase is neglegable

18. Will try one more activation function Tanh

19. Tanh also outputs no learning with neglegable accuracy:
128ms/step - accuracy: 0.0430 - loss: 3.8280 - val_accuracy: 0.0357 - val_loss: 3.7973 - learning_rate: 0.0010

20. Without making majour changes to the architecture of the block i dont think ill be able to achieve anything with the other activation functions. The main issue with these AFs is the vanishin gradient, while the relu doesnt have this effect at all, because the gradient doesnt shrink in magnitude, unlike in tanh and sigmoid (where the gradient can only be multiplied by 0.25 / <1 )
