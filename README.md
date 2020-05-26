# Image Style Transfer Using Convolutional Neural Networks in PyTorch
This is unofficial pytorch implementation of the paper, "Image Style Transfer Using Convolutional Neural Networks" [Gatys+, CVPR2016].

<img src='imgs/style.jpg' title='Style Image' width='30%'> <img src='imgs/content.jpg' title='Content Image' width='30%'> <img src='imgs/transferred.jpg' title='Transferred Image' width='30%'>

## Requirements
* Python 3.6+ 
* PyTorch 1.5.0+ or 1.5.0+cu*
* TorchVision 0.6.0+ or 0.6.0+cu*
* Numpy 1.16.2+ 
* Pillow 5.1.0+ 

## Usage
### Options
* `--content, -c`: The path to the content image.
* `--style, -s`: The path to the style image.
* `--epoch, -e`: The number of epoch. (Default: 300)
* `-content_weight, -c_w`: The weight of the content loss. (Default: 1)
* `-style_weight, -s_w`: The weight of the style loss. (Default: 1000)
* `--initialize_noise, -i_n`: If you use this option, the transferred image is initialized with white noise. If not, it is initialized with the grayscale content image.
* `--cuda`: If you have an available GPU, you should use this option.
* `--content_layers, -c_l`: If you want to name which layers have content-related information, use this. name of each layers are like conv_i or relu_i <br>
use like this: ``` python style_transfer.py --content_layers conv_1 conv_2```
* `--style_layers, -s_l`: If you want to name which layers have style-related information, use this. name of each layers are like conv_i or relu_i <br>
use like this: ``` python style_transfer.py --style_layers conv_1 reelu_3```
* `--model, -m`: The net structure. You can choose from `vgg11 vgg13 vgg16 vgg19`

### Examples
With CPU:
```bash
python style_transfer.py -c contents/golden_gate.jpg -s styles/kandinsky.jpg
```
With GPU:
```bash
python style_transfer.py -c contents/golden_gate.jpg -s styles/kandinsky.jpg --cuda
```

## Installation
```bash
git clone https://github.com/zephyr-jebel/pytorch-Neural-Style-Transfer.git
```
Install PyTorch and dependencies from [http://pytorch.org.](http://pytorch.org)  
We have prepared requirement.txt, but it is preferable to use Anaconda as recommended on [http://pytorch.org.](http://pytorch.org)

## References
* Leon A. Gatys, Alexander S. Ecker and Matthias Bethge. "Image Style Transfer Using Convolutional Neural Networks", in CVPR 2016. [[Paper]](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)
* Code is inspired by [Neural Transfer with PyTorch.](http://pytorch.org/tutorials/advanced/neural_style_tutorial.html)

