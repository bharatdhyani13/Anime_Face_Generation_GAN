# Anime Face Generation(DCGAN)

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
We use DCGAN ([read it here](https://medium.com/@jonathan_hui/gan-dcgan-deep-convolutional-generative-adversarial-networks-df855c438f)). Training is done on 62,608 images.
Images are loaded into memory batch wise.

Steps:
1. First we take images from dataset and create a batch sample
2. Then we generate images using generator(**input = gaussian noise**) 
3. We add noise to labels of real and fake data (genarator output)
4. Then we train discriminator on both real data as well as on fake data
5. Train GAN on fake images and real data labels
I trained the model for 20,000 stepson MacBook Pro (i7) which took 6-7 secs for each step.

**As we are trying to maximize the loss in the Discriminative model, we do *Gradient Ascend* instead of Gradient Descend.**


# Training results as a GIF: (images at every 100 step):

![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/gif.gif)

# Faces generated at the end of 20,000 steps:
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/19900_image.png)
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/19800_image.png)
![](https://github.com/bharatdhyani13/Anime_Face_Generation_GAN/blob/master/images/19700_image.png)

These results are not as accurate, but more training images and step count will create better images.
However, the output images gives a good idea of the anime character looks.

# Sources
https://medium.com/@jonathan_hui/gan-dcgan-deep-convolutional-generative-adversarial-networks-df855c438f
https://medium.com/@nikitasharma_43692/my-mangagan-building-my-first-generative-adversarial-network-2ec1920257e3?sk=0eef45a3ef8d8b13f23f620abe48ef07
