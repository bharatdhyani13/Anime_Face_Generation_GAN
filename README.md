# Anime_Face_Generation_GAN

For Anime face generation we would require a lot of anime faces on which to train the model on.
I found a pre-processed (faces-cropped) dataset from the following sites:
https://www.kaggle.com/aadilmalik94/animecharacterfaces


# Take a look at the dataset:
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/2.PNG)


# How does GAN Works?
Basic mathematical foundation for GAN is to find the PDF(probability distribution function) of the dataset **D** and get its parameters.

Now genarate random samples from this which will be our **D'**. 
Now if D and D' have the same distribution, their values should be similar.
We try to **maximize Log Loss** at the Discriminative part of GAN, as in order to dicriminate between the two data,
we assign prediction for D = 0 and D' = 1.

This technique is used to distinguish between distributions. Greater the loss of this model, higher is the similarity.

# Training
Only simple GAN training methods are used. Training is done on about 22,000 images. Images are not loaded entirely into memory instead, each time a batch is sampled, only the sampled images are loaded. An overview of what happens each step is:
-Sample images from dataset (real data)
-Generate images using generator (gaussian noise as input) (fake data)
-Add noise to labels of real and fake data
-Train discriminator on real data -Train discriminator on fake data
-Train GAN on fake images and real data labels
Training is done for 20,000 steps. In my setup (GTX 660; i5 4670) it takes 10-11 secs for each step.


Training results as a GIF: (images at every 100 step):
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/gif.gif)

Faces generated at the end of 20,000 steps:
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/19900.png)
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/19800.png)
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/19700.png)
