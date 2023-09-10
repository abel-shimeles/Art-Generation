# Art Generation with Neural Style Transfer

This repository is inspired by an algorithm created by [Gatys et al. (2015).](https://arxiv.org/abs/1508.06576) called Neural Style Transfer.

Neural Style Transfer (NST) is one of the most interesting optimization techniques in deep learning. It merges two images, namely: a <strong>"content" image (C)</strong> and a <strong>"style" image (S)</strong>, to create a <strong>"generated" image (G)</strong>. The generated image G combines the "content" of the image C with the "style" of image S. 

In this repository, Louvre museum in Paris (content image C) was combined with the impressionist style of Claude Monet (style image S) to generate the following image:

<img src="images/louvre_generated.png" style="width:750px;height:300px;">

Neural Style Transfer (NST) uses a previously trained convolutional network, and builds on top of that. 

This repository will be using the eponymously named VGG network from the [original NST paper](https://arxiv.org/abs/1508.06576) published by the Visual Geometry Group at University of Oxford in 2014. Specifically,  VGG-19, a 19-layer version of the VGG network. This model has already been trained on the very large ImageNet database, and has learned to recognize a variety of low level features (at the shallower layers) and high level features (at the deeper layers). 

## Setup
1. Clone this repository
``` shell
git clone https://github.com/abel-shimeles/Art-Generation
cd Art-Generation
```
2. Download [pretrained model](https://drive.google.com/file/d/1-2aHu1D0JpHMfSVytbb4VzlERtXcX38u/view) from Google Drive since transfer learning is used. Then extract the downloaded file and paste it in the root folder of the cloned repository

## Train and test it in your own images
Some other content and style images can be found in the images/ folder but if you want to use your own images you can follow the following steps

1. Go to the images folder
2. Paste your images (images will scaled to 400x400, but you can change that parameter too ), rename them "my_content.png" and "my_style.png" for example.
3. Change the code in jupyter notebook from :

```py
content_image = np.array(Image.open("images/louvre_small.jpg").resize((img_size, img_size)))
style_image =  np.array(Image.open("images/monet.jpg").resize((img_size, img_size)))

```

&emsp;&emsp;to:

``` py
content_image = np.array(Image.open("images/my_content.jpg").resize((img_size, img_size)))
style_image =  np.array(Image.open("my_style.jpg").resize((img_size, img_size)))

```
4. Rerun the cells (you may need to restart the Kernel in the upper tab of the notebook).

### NOTE

If you don't have a very good computational power in your machine you can decrease the number of epoches and increase the learning rate at the cost of the output. But if you have an even better computational power then you can increase the number of epoches and decrease the learning rate to get even better results.

### Output

The pre-generated images from my implementation can be found in the output directory.
