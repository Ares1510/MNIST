# MNIST with TensorFlow - Kaggle 99.5%

Learning computer vision by improving rank on Kaggle.


After completing Andrew NG's course, I thought working on the MNIST dataset and improving my rank on kaggle would be the perfect place to practice what I've learnt.

I started off with a simple feed forward network just to get things started. Obviously this did not fair well for my ranking. I think I ended up placing around 1800 on the leaderboard. 

I knew that using CNN's were my best bet to up my ranking. I followed a similar architecture to the one used in VGG-16.

Conv2D -- Conv2D -- MaxPool -- Conv2D -- Conv2D -- MaxPool -- Dense -- Dense

1st Iteration -
Kept epochs at 10 and used a batch size of 32. I was running this on my laptop with a GTX 960M and tensorflow-gpu installed.
Decided to use SGD as my optimizer. Tried 0.01 and 0.001 as my learning rates. 0.001 turned out to be the better choice. Kept momentum at 0.9.
Each iteration took almost 160s. Knew I needed better hardware.
Ended up scoring about 98% on Kaggle.

2nd Iteration -
Seeing the loss and accuracy graphs from the previous iteration, it was clear that the model was learning well without overfitting.
Increased the epochs to 25. Added a decay of LR / EPOCHS.
This took a really long time to train, which led me to finding out different cloud services which provide GPU's.
The extra training helped a little bit with the score being 98.414.

3rd Itertion - 
Stumbled upon Paperspace and signed up for their service. They provide Jupyter notebooks with a Nvidia P5000 GPU free of cost!
I removed the decay and trained the exact same network as before. Each iteration took only 32s compared to ~170s on my laptop.
And to my surprise Kaggle scored this submission at 99.071%! Now we're getting somewhere.

4th Iteration -
After learning about the benefits of cloud training and Paperspace, I decided to feed the model more images using data augmentation.
Looking at the previous training progress, I could see that the model was learning well, but it was learning very slowly. I decided to switch to the Adam optimizer which helped speed up the training. I also increased the epochs to 30.
Lo and behold! 99.5% on Kaggle with a rank of 391! Not bad at all.

I decided to stop here and move on to other datasets. I'm sure we could improve the score to 99.7% using multiple models and ensembling them. This exercise taught me a lot about computer vision as well as how Kaggle competitions work. Now time to move on to a different project.
