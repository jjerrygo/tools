# tools

## 1.CuteR
CuteR is a QR code generator, it combines your image with QR code which puts link into your image.

As a fresh hand of Python, I try to summarize how to use it as my practice of learning.

You can find the original project here: https://github.com/chinuno-usami/CuteR

Here is a quick demo to showcase:

#### 1) Before

![CuteR_head](https://github.com/jjerrygo/tools/blob/master/CuteR_head.jpg)

#### 2) Run Command
```
CuteR -C -v 6 -r 0 0 0 -o head_color.jpg head.jpg http://www.operasolutions.com
```

#### 3) After

![CuteR_head_out](https://github.com/jjerrygo/tools/blob/master/CuteR_head_out.jpg)

### 1.0 Preparation
There are 2 ways to use it, first is command line with option, second is to run python module.

#### 1) Setup
Install Pillow/CuteR
```shell
pip install Pillow
pip install CuteR
```
Pillow is a powerful branch of PIL(Python Imaging Library), since PIL no longer supports after Python 2.7, we should use Pillow.

#### 2) Input
* Link the of QR code(text)
* An image you want to use as background(image)

Please note the image should better be square to be consitent with output, if not, will automatically use the top left square area of your image as the input.

#### 3) Output
* A QR code image with background

### 1.1 Run as Python script

#### Example
```python
#!/usr/bin/env python3

# For Python 2.7, please use <import CuteR as cr>
import CuteR.CuteR as cr
cr.produce("http://www.operasolutions.com","sample_input.png").save("sample_output.png")
```
Then output image would be in the same location as the input.

#### Attention
Do **NOT** name the script as CuteR.py in case of duplication with module.

### 1.2 Run as command

#### Example(shell)
```shell
CuteR -C -c 10 -o sample_output.png -v 10 sample_input.png http://www.operasolutions.com
```
```
-C    [] colorful mode
-v    [num] QR version, from 1 to 40, the larger number, the higher resolution
-c    [num] contrast enhance
```

#### Usage
```shell
CuteR [-h] [-o OUTPUT] [-v VERSION] [-e {Q,H,M,L}] [-b BRIGHTNESS]
                [-c CONTRAST] [-C] [-r R G B]
                image
                text
```
```
required arguments:
  image                 Image name
  text                  QR code link

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT, --output OUTPUT
                        Name of output file.
  -v VERSION, --version VERSION
                        QR version.In range of [1-40]
  -e {Q,H,M,L}, --errorcorrect {Q,H,M,L}
                        Error correct
  -b BRIGHTNESS, --brightness BRIGHTNESS
                        Brightness enhance
  -c CONTRAST, --contrast CONTRAST
                        Contrast enhance
  -C, --colourful       colourful mode
  -r R G B, --rgb R G B
                        color to replace black
```
