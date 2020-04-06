<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet">
    <img src="https://coloradoengineering.com/wp-content/uploads/2017/09/Computer-Vision-and-Machine-Learning.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Semantic Segmentation of Tissue Images using Deep Learning</h3>

  <p align="center">
    Image Segmentation carried out using UNET, SegNet and Deeplabv3+ on MonuSeg Dataset.
    <br />
    <a href="https://monuseg.grand-challenge.org/"><strong>Learn about MonuSeg »</strong></a>
    <br />
    <br />
    <a href="https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/blob/master/DeepLabv3%2B_ACV_Assg3.ipynb">Deep Lab v3+ (Training + Inference)</a>
    ·
    <a href="https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/blob/master/SegNet_ACV_Assg3.ipynb">SegNet (Training + Inference)</a>
    ·
    <a href="https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/blob/master/UNET_ACV_Assg3.ipynb">UNET (Training + Inference)</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Obtaining Data](#obtaining-data)
* [Usage](#usage)
* [Results](#results)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## About The Project

[![Tissue Image and Ground Truth Example][product-screenshot]](https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet)

Originally the MonuSeg dataset consists of 30 training images, each of size 1000 x 1000. In addition to these, there are 14 testing images of the same dimensions.
Images are in RGB format, while the ground truth is a binary image (Single Channel).
For the purpose of training, we extracted patches of size 256 x 256 from these images with 50% overlapping, this resulted in 1080 different patches.

### Built With
Major Libraries that were used in this project,
* [Keras](https://keras.io)
* [Tensorflow](https://tensorflow.org)
* [Numpy](https://numpy.org)



<!-- GETTING STARTED -->
## Getting Started

The notebooks provided in this repository are standalone and can be run directly using colab.

### Prerequisites

Account on colab is recommended, although not required.

### Obtaining Data

Data is made public using google drive links and then directly downloaded to colab workspace with the help of *gdown*. First code cell in each notebook downloads the data.



<!-- USAGE EXAMPLES -->
## Usage

There are weights for each model available, although these weights are used in the notebooks after training, separate notebooks that are only used for inference are also provided.

### Config File
Due to the nature of colab, it was considered that not using a separate config file would be a better option, although a cell of code in each notebook was dedicated was the purpose of configuration.

## Results

### Training Settings

Patches of size 256 x 256 with 50% overlap were fed to each model. The problem was treated as a **binary classification problem**. Generally an auto-encoder like model was used, where the input was 256 x 256 x 3 and the output was 256 x 256 x 1.
*Sigmoid activation* along with *binary cross entropy loss* was used. *Adam* optimizer was used. Techniques such as *Early Stopping*, *Reducing Learning Rate on Plateu* and *Saving Best Model* were used.
The Dataset already provides a test set, so in order to make sure no overfitting on the test set was taking place, we separated 108 patches from the training set as validation data.

### Quantitative Results
| Model | Accuracy | Dice Coefficient | F1 Score | Binary Cross Entropy Loss|
| ------------- | ------------- | ------------- | ------------- | ------------- |
| UNET | 89.63% | 0.7199 | 0.7567 | **0.2803** |
| SegNet | 89.31% | 0.6858 | 0.7209 | 0.3076 |
| DeepLabV3 | **90.63%** | **0.7696** | **0.7802** | 0.3735 |



#### *For each model, (i)Qualitative Results (ii)Training and Validation graphs are shown.*

### Qualitative Results

#### UNET
![UNET Visual Results][unet-qual-res]
#### SegNet
![SegNet Visual Results][segnet-qual-res]
#### Deep Lab v3+
![Deep Lab v3+ Visual Results][deeplabv3+-qual-res]

### Training and Validation Graphs

#### UNET
![UNET Training Loss][unet-train-graph]
#### SegNet
![SegNet Training Loss][segnet-train-graph]
#### Deep Lab v3+
![Deep Lab v3+ Training Loss][deeplabv3+-train-graph]

<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/issues) for a list of proposed features (and known issues).



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Muhammad Ehsan ul Haq - [@EhsanBinEjaz](https://twitter.com/EhsanBinEjaz) - ehsanulhaq18@gmail.com

Project Link: [https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet](https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [UNET Implementation by hlamba28](https://github.com/hlamba28/UNET-TGS)
* [SegNet Implementation by ykamikawa](https://github.com/ykamikawa/tf-keras-SegNet)
* [DeepLab v3+ Implementation by xuannianz](https://github.com/xuannianz/keras-deeplab-v3-plus)
* [GitHub Emoji Cheat Sheet](https://www.webpagefx.com/tools/emoji-cheat-sheet)
* [Img Shields](https://shields.io)
* [Choose an Open Source License](https://choosealicense.com)
* [GitHub Pages](https://pages.github.com)
* [Animate.css](https://daneden.github.io/animate.css)
* [Loaders.css](https://connoratherton.com/loaders)
* [Slick Carousel](https://kenwheeler.github.io/slick)
* [Smooth Scroll](https://github.com/cferdinandi/smooth-scroll)
* [Sticky Kit](http://leafo.net/sticky-kit)
* [JVectorMap](http://jvectormap.com)
* [Font Awesome](https://fontawesome.com)





<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet.svg?style=flat-square
[contributors-url]: https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet.svg?style=flat-square
[forks-url]: https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/network/members
[stars-shield]: https://img.shields.io/github/stars/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet.svg?style=flat-square
[stars-url]: https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/stargazers
[issues-shield]: https://img.shields.io/github/issues/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet.svg?style=flat-square
[issues-url]: https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/issues
[license-shield]: https://img.shields.io/github/license/othneildrew/Best-README-Template.svg?style=flat-square
[license-url]: https://github.com/Ehsan1997/ImageSegmentation-UNET-DeepLab-SegNet/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/ehsansonofejaz
[product-screenshot]: temp_tissue_image_with_gt.png
[unet-train-graph]: unet-train-graph.png
[segnet-train-graph]: segnet-train-graph.png
[deeplabv3+-train-graph]: deeplabv3+-train-graph.png
[unet-qual-res]: unet-qual-res.png
[segnet-qual-res]: segnet-qual-res.png
[deeplabv3+-qual-res]: deeplabv3+-qual-res.png
