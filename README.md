# tools

## 1.CuteR
CuteR is a QR code head potrait generator, it combines your image with QC code which generates QC code with your image as the background.

You can find the original version here: https://github.com/chinuno-usami/CuteR

As a fresh hand of Python, I try to figure out how to use it as my practice of learing.

Two ways to use it, first is command line with option, second is to run python module.

### 1.1 As Python module
1) Install package
```shell
pip install CuteR
```
2) Create a Python script demo.py
*Attention: do **NOT** name the script as CuteR.py in case of duplication with module*
Define options, run and save within a Python file.
A code example is as below:
```python
#!/usr/bin/env python3

# For Python 2.7, please use <import CuteR as cr>
import CuteR.CuteR as cr
cr.produce("http://www.operasolutions.com","sample_input.png").save("sample_output.png")
```
3) Run demo.py
Find the output sample_output.png in the same folder

### 1.2 As command line tool

```shell
python CuteR_tool.py -c 10 -e H -o sample_output.png -v 10 sample_input.png http://www.operasolutions.com
```

Below are the steps:
