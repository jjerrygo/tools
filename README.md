# tools

## 1.CuteR
CuteR is a QR code head potrait generator, it combines your image with QC code which generates QC code with your image as the background.

You can find the original version here: https://github.com/chinuno-usami/CuteR

As a fresh hand of Python, I try to figure out how to use it as my practice of learing.

### 1.0 Preparation
There are 2 ways to use it, first is command line with option, second is to run python module.

### Setup
Install CuteR package
```shell
pip install CuteR
```
### Input
* Link the of QR code
* An image you want to use as background

### Output
* A QC code image with background

### 1.1 As Python module

#### Example
```python
#!/usr/bin/env python3

# For Python 2.7, please use <import CuteR as cr>
import CuteR.CuteR as cr
cr.produce("http://www.operasolutions.com","sample_input.png").save("sample_output.png")
```

#### Attention
Do **NOT** name the script as CuteR.py in case of duplication with module

### 1.2 As command line tool

#### Example
```shell
python CuteR.py -C -c 10 -e H -o sample_output.png -v 10 sample_input.png http://www.operasolutions.com
```

#### Usage
```shell
python CuteR.py [-h] [-o OUTPUT] [-v VERSION] [-e {Q,H,M,L}] [-b BRIGHTNESS]
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
