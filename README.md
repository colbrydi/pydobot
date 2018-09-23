

This code is a fork of code provided by [ luismesas/pydobot](https://github.com/luismesas/pydobot).

We our using the DoBot in our NumricalLinearAlgebra course. I added an example in a jupyter notebook and I made a minor modification to add the ```goj``` function to go to a specific joint angle. 

[![CircleCI](https://circleci.com/gh/luismesas/pydobot.svg?style=svg)](https://circleci.com/gh/luismesas/pydobot)

Python library for Dobot Magician
===

Based on Communication Protocol V1.0.4 (_latest version [here](http://dobot.cc/download-center/dobot-magician.html)_)


Installation
---

```
pip install pydobot
```

Samples
---

```python
import time
from glob import glob

from pydobot import Dobot

available_ports = glob('/dev/cu*usb*')  # mask for OSX Dobot port
if len(available_ports) == 0:
    print('no port found for Dobot Magician')
    exit(1)

device = Dobot(port=available_ports[0])

time.sleep(0.5)
device.speed(100)
device.go(250.0, 0.0, 25.0)
device.speed(10)
device.go(250.0, 0.0, 0.0)
time.sleep(2)
device.close()

```
