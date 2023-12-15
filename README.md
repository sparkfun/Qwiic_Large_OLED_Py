Qwiic_Large_OLED_Py
========================

<p align="center">
   <img src="https://cdn.sparkfun.com/assets/custom_pages/2/7/2/qwiic-logo-registered.jpg"  width=200>  
   <img src="https://www.python.org/static/community_logos/python-logo-master-v3-TM.png"  width=240>   
</p>
<p align="center">
	<a href="https://pypi.org/project/sparkfun-qwiic-large-oled/" alt="Package">
		<img src="https://img.shields.io/pypi/pyversions/sparkfun_qwiic_large_oled.svg" /></a>
	<a href="https://github.com/sparkfun/Qwiic_Large_OLED_Py/issues" alt="Issues">
		<img src="https://img.shields.io/github/issues/sparkfun/Qwiic_Large_OLED_Py.svg" /></a>
	<a href="https://qwiic-large-oled-py.readthedocs.io/en/latest/index.html" alt="Documentation">
		<img src="https://readthedocs.org/projects/qwiic-large-oled-py/badge/?version=latest&style=flat" /></a>
	<a href="https://github.com/sparkfun/Qwiic_Large_OLED_Py/blob/master/LICENSE" alt="License">
		<img src="https://img.shields.io/badge/license-MIT-blue.svg" /></a>
	<a href="https://twitter.com/intent/follow?screen_name=sparkfun">
        	<img src="https://img.shields.io/twitter/follow/sparkfun.svg?style=social&logo=twitter"
           	 alt="follow on Twitter"></a>
	
</p>

<img src="https://cdn.sparkfun.com//assets/parts/2/3/7/6/0/23453-Qwiic-OLED-Feature-WithDisplay.jpg" align="right" width=200 alt="SparkFun Qwiic OLED Display - (1.3in., 128x64)">

The Python package for the [Qwiic OLED - (1.3in., 128x64)](https://www.sparkfun.com/products/23453) board.

This package is a port of the [SparkFun Micro OLED Breakout Arduino Library](https://github.com/sparkfun/SparkFun_Micro_OLED_Arduino_Library)

This package can be used in conjunction with the overall [SparkFun qwiic Python Package](https://github.com/sparkfun/Qwiic_Py)

New to qwiic? Take a look at the entire [SparkFun qwiic ecosystem](https://www.sparkfun.com/qwiic).


## Contents

* [Supported Platforms](#supported-platforms)
* [Dependencies](#dependencies)
* [Installation](#installation)
* [Documentation](#documentation)
* [Example Use](#example-use)

Supported Platforms
--------------------
The qwiic Python package current supports the following platforms:
* [Raspberry Pi](https://www.sparkfun.com/search/results?term=raspberry+pi)
* [NVidia Jetson Nano](https://www.sparkfun.com/products/15297)
* [Google Coral Development Board](https://www.sparkfun.com/products/15318)

Dependencies
================
This driver package depends on the qwiic I2C driver: [Qwiic_I2C_Py](https://github.com/sparkfun/Qwiic_I2C_Py)

This package depends on the OLED display driver base package: [Qwiic_OLED_Base_Py](https://github.com/sparkfun/Qwiic_OLED_Base_Py)

Documentation
-------------
The SparkFun Qwiic OLED Display module documentation is hosted at [ReadTheDocs](https://qwiic-large-oled-py.readthedocs.io/en/latest/index.html)

Installation
--------------

### PyPi Installation
This repository is hosted on PyPi as the [sparkfun-qwiic-large-oled](https://pypi.org/project/sparkfun-qwiic-large-oled/) package. On systems that support PyPi installation via pip, this library is installed using the following commands

For all users (note: the user must have sudo privileges):
```sh
sudo pip install sparkfun-qwiic-large-oled
```
For the current user:

```sh
pip install sparkfun_qwiic_large_oled
```

### Local Installation
To install, make sure the setuptools package is installed on the system.

Direct installation at the command line:
```sh
python setup.py install
```

To build a package for use with pip:
```sh
python setup.py sdist
 ```
A package file is built and placed in a subdirectory called dist. This package file can be installed using pip.
```sh
cd dist
pip install sparkfun_oled_display-<version>.tar.gz
```
  
Example Use
------------
This example is intended to be used with the [Qwiic OLED - (1.3in., 128x64)](https://www.sparkfun.com/products/23453) board. (See the <a href="https://github.com/sparkfun/Qwiic_Large_OLED_Py/tree/main/examples">examples directory</a> for more detailed use cases.)

```python
import qwiic_large_oled
import sys


def runExample():

    #  These lines of code are all you need to initialize the OLED display and print text on the screen.
  
    print("\nSparkFun Qwiic OLED Display - Hello Example\n")
    myOLED = qwiic_large_oled.QwiicLargeOled()

    if myOLED.is_connected() == False:
        print("The Qwiic OLED Display isn't connected to the system. Please check your connection", \
            file=sys.stderr)
        return
    
    #  Before you can start using the OLED, call begin() to init all of the pins and configure the OLED.
    myOLED.begin()

    myOLED.clear(myOLED.PAGE)  #  Clear the display's buffer

    myOLED.print("Hello World")  #  Add "Hello World" to buffer

    #  To actually draw anything on the display, you must call the display() function. 
    myOLED.display()

runExample()
```

<p align="center">
<img src="https://cdn.sparkfun.com/assets/custom_pages/3/3/4/dark-logo-red-flame.png" alt="SparkFun - Start Something">
</p>
