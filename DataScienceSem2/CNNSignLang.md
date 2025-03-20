1. Majour issues attempting ot install tensorflow on linux

2. After many hours found that tensorflow (library required for advanced neural netwrok packages, etc)
Doesnt work with latest python version, only older version 3.12

3. installed a virtual environment with the older version of python 

4. Looking for datasets

5. Found a sign lang dataset with 223k files (4.56 GB)

6. Setup a CNN algorith using tensorflow package

7. By default tensorflow is only configured to use CPU, using manual figured out to ensure the algo 
uses my Nvidid GPU for training (shpuld be a lot quicker)

8. Using GPU we can process in big "batches", and higher image quality, ensuring we capture more details
for each image that we train the aglo on

9. So far have a working algorithm as far as training the dataset using Nvidia GPU processing