# Super resolution on microscopic images of different tissues using GAN architectures
Implementation of the SRGAN and ESRGAN models for image super resolution on a custom set consisting of microscopic images of different tissues.

# Dataset

As presented in Dataset Creation notebook, a dataset is created from 25 high resolutuon screenshots from different human tissues from [Bio-Atlas](http://bio-atlas.psu.edu/human/index.php). A sample of the picture is added in the dataset folder. The sliced images containes the ground truth images used for training and the sliced-val the ground truth images for testing. Train-LR containes the low resolution images used for training and val-LR the images for testing.

# Training

As presented in the TrainingAndEvaluation notebook, the [mmsr](https://github.com/open-mmlab/mmsr) PyTorch architectures SRGAN and ESRGAN are trained on datasets with 4x scale, both for 2000 iterations. [Pretrained models] (https://drive.google.com/drive/folders/1cw-dEpAdwpuQdEC7WJhITwjrn2Tr-hqd) have been used to initialize the weights, MSRGAN for SRGAN and RRDBPSNR for ESRGAN.

# Results

The metrics are obtained by training the models with two datasets by using ground truth and low resolution images with different resolution. 

#### 1). GT: 192 x 192px, LR: 48 x 48px, SCALE: 4 (A total of 900 images, from which 100 are used for testing)

ESRGAN: PSNR: 21.220876 dB; SSIM: 0.654544

SRGAN: PSNR: 21.715250 dB; SSIM: 0.626929

#### 2). GT: 840 x 840px, LR: 210 x 210px, SCALE: 4 (A total of 1400 images, from which 50 are used for testing)

ESRGAN: PSNR: 20.447230 dB; SSIM: 0.606676

SRGAN: PSNR: 21.355975 dB; SSIM: 0.617981

# Visualisation

By setting the frequency of validating the training process on every 200 iterations, a visual tracking of the changes in the generated images can be recorded:

ESRGAN:

![ESRGAN_20](https://github.com/noran9/microscopic-images-srgan/blob/master/images/tile-20_ESRGAN.gif)
![ESRGAN_421](https://github.com/noran9/microscopic-images-srgan/blob/master/images/tile-421_ESRGAN.gif)

SRGAN:

![SRGAN_20](https://github.com/noran9/microscopic-images-srgan/blob/master/images/tile-20_SRGAN.gif)
![SRGAN_421](https://github.com/noran9/microscopic-images-srgan/blob/master/images/tile-421_SRGAN.gif)
