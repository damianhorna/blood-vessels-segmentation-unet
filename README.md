# vessels
Retinal blood vessel segmentation using convolutional neural network (u-net) and image processing techniques.

### Prerequisites
Use conda's spec file in order to create identical environment on your local machine:

```
cd vessels
conda create --name myenv --file dependencies.yml
conda activate myenv
```
Then run:
```
jupyter notebook
```

### Simple classification using image processing techniques
1. Original image:

![rgb](basic/rgb.PNG)

2. Transformation to grayscale:

![gray](basic/gray.PNG)

3. CLAHE (Constrast-limited adaptive histogram equalization):

![clahe](basic/clahe.PNG)

4. Gamma correction:

![gamma](basic/gamma.PNG)

5. cv2.fastNlMeansDenoising:

![denoised](basic/denoised.PNG)

6. Ridge detection:

![ridges](basic/ridges.PNG)

7. Mask:

![masked](basic/masked.PNG)

8. Median filter: 

![median](basic/median.PNG)

9. Threshold: 

![thresh](basic/thresh.PNG)

10. Results:


![simple1](results/simple/1.PNG)

![simple2](results/simple/2.PNG)

![simple3](results/simple/3.PNG)

Simple classificator evaluation:

![simple-cm](results/simple/cm.PNG)

![simple-roc](results/simple/ROC.PNG)

### Classification using U-Net architecture
[U-Net](https://en.wikipedia.org/wiki/U-Net) architecture is widely used in medical field when it comes to image segmentation. We train the network with small and random image crops sized 64 x 64 pixels, and for each of them we get 1 if it's classified as a blood vessel or 0 if's not. The training took 100 epochs, 125 steps each with the batch size equal to 16 random image crops. We used Google Colab in order to train our model (Nvidia Tesla K80). The training took no longer than 40 minutes. Some of the results are presented below:

![cnn1](results/cnn/1.PNG)

![cnn2](results/cnn/2.PNG)

![cnn3](results/cnn/3.PNG)

![cnn-cm](results/cnn/cm.PNG)

![cnn-roc](results/cnn/ROC.PNG)
