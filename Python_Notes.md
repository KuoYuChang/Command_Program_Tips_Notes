# Virtual Environment

## Conda


* ### Create Env
tags: \# conda create env \# create env \# conda create virtualenv

Example to create an conda env named `my_env` :
```bash
conda create --name my_env python=3.10
```

Activate: 

```bash
conda activate my_env
```

> [!NOTE]
> Recommend to upgrade pip, setuptools, wheel when first time established environment

```bash
pip install --upgrade pip setuptools wheel
```

# Pip

* ### limit range of package version

tag # pip limit version # pip version smaller than # package version smaller # package smaller version

eg
```bash
pip install "numpy<2"
```


# Pytorch

tags # torch


* ### set device
tags # torch device # torch device if cuda # torch get device # torch device variable

```python
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
```


# Colab

* ### Edit and overwrite files in colab

tag # colab edit files # colab edit py # colab edit and save # colab modify files

in cell, run command `%pycat *filename*`, like:
```python
%pycat utils.py
```

Will appear a pop up, shows codes

Copy and paste contents into new empty cell like:

```python
# this is a cell in colab
# contents of utils.py
import numpy as np

def show():
    print()

# something
# something
#
```

Edit

```python
# this is a cell in colab
# contents of utils.py
import numpy as np

def show():
    # some modified
    print("show modified")
    print()

# something
# something
#
```

After edit finished, add command `%%writefile *filename*` on top of the cell

```python
%%writefile utils.py
# this is a cell in colab
# contents of utils.py
import numpy as np

def show():
    # some modified
    print("show modified")
    print()

# something
# something
#
```
Finally, run the cell, file will be modified

[Reference](https://stackoverflow.com/a/53296722)

* ### location of colab files

Usually at `/content/`, able to access from `root` folder