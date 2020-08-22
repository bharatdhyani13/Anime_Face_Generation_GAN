# Anime_Face_Generation_GAN

For Anime face generation we would require a lot of anime faces on which to train the model on.
I found a pre-processed (faces-cropped) dataset from the following sites:
https://www.kaggle.com/aadilmalik94/animecharacterfaces


# Take a look at the dataset:
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/2.PNG)


# How does GAN Works?
Basic mathematical foundation for GAN is to find the PDF(probability distribution function) of the dataset **D** and get its parameters.
Now genarate random samples from this which will be our **D'**. Now if D and D' have the same distribution, their values should be similar.
We try to **maximize Log Loss** at the Discriminative part of GAN, as in order to dicriminate between the two data, we assign prediction for D = 0 and D' = 1.
This technique is used to distinguish between distributions. Greater the loss of this model, higher is the similarity.


# This is how Genarator Architechture looks like:
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/1.PNG)

# This is how Genarator Architechture looks like:
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/3.PNG)


Full Training as a GIF: (images sampled every 100 step):
Faces generated at the end of 10,000 steps:
