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


* ### search packages, filter packages

tag # pip filer # pip search packages # pip filter out packages # pip find # pip find certain # pip find by string # pip search packages with string

```bash
# linux
pip list | grep tensorflow
```

```bash
# windows
pip list | findstr tensorflow
```




# Colab

* run py file with multiple input arguments, by adding `%%bash` on top of cell[^jakevdp]:

tag # colab multiple arg # multiple argv # colab wrap command # colab cell multiple parameters

```bash
%%bash
python example.py arg0=0 \
                    arg1=1 \
                    arg2=2 \
```
$\quad$ Note that adding `#` is not allowed in bash cell, no space after `\`



* ### Edit and overwrite files in colab

tag # colab edit files # colab edit py # colab edit and save # colab modify files

in cell, run command `%pycat *filename*`, like:
```bash
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

# Hydra

tag #hydra #hyper para #hyper parameter

Here's an example[^hydra_official]:

* set sub-config file as parameters for py file, in folder `conf/`

```yaml
defaults:
  - db: mysql

debug: false
```

$\quad$ Means that there's a yaml file in folder `conf/db/`

$\quad$ Prepare two yaml files in `conf/db`:

```yaml
# mysql.yaml
name: mysql
```

```yaml
#sqlite.yaml
name: sqlite
```

$\quad$ Prepare test py file on root folder:
```python
import hydra
from omegaconf import DictConfig, OmegaConf

@hydra.main(version_base=None, config_path="conf", config_name="config")
def my_app(cfg : DictConfig) -> None:
    print(OmegaConf.to_yaml(cfg))

if __name__ == "__main__":
    my_app()
```

$\quad$ looks like this
```
├── my_app.py
├── conf
│   ├── config.yaml
│   ├── db
│   │   ├── mysql.yaml
│   │   └── sqlite.yaml 
```

* Run commend line

```bash
python my_app.py # call default db in config/config.yaml
```

```bash
python my_app.py db=sqlite # change db to sqlite, in config/config.yaml
```

## References

[^jakevdp]: from jakevdp [stackoverflow](https://stackoverflow.com/a/60477370)

[^hydra_official]: hydra official [example1](https://hydra.cc/docs/intro/) and [example2](https://hydra.cc/docs/advanced/defaults_list/) 