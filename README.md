# **HOW TO USE?**

## STEP 1

Import `easy_import` into your python file with `import hot_import` or `from hot_import import EasyImport`

## STEP 2

Import the desired module as following `import module_name`

**/!\** It will **not** work if you do `from module_name import *` or `from module_name import function` **/!\**


## STEP 3


Create an object EasyImport that you will use to manage your modules


```py
# main.py
from hot_import import EasyImport

import module


mods = EasyImport([module], auto_update=True)

module = mods.get_module(module)
```


### STEP 4

Check if it's working, to proceed, you have to edit `module.py` while your code is running

```py
# module.py
def hello():
    return "Hello world!"
```
```py
# main.py
from hot_import import EasyImport
import time

import module


mods = EasyImport([module], auto_update=True)

module = mods.get_module(module)

while True:
    print(module.hello())
    time.sleep(1)
```


### STEP 5 (optional)


You can add an event on_update to help you debugging

```py
# main.py
from hot_import import EasyImport
import time

import module


mods = EasyImport([module], auto_update=True)

module = mods.get_module(module)


@mods.on_update()
def on_update(module):
    print(f"The module {module.module_name} has been updated!")


while True:
    print(module.hello())
    time.sleep(1)
```


## DISCLAIMER

This library is new and may contain some errors

Otherwise, have fun with it as long as you declare my work
