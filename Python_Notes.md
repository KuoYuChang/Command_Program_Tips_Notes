# Virtual Environment

## Conda


### Create Env
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

limit range of package version

tag # pip limit version # pip version smaller than # package version smaller # package smaller version

eg
```bash
pip install "numpy<2"
```


# Pytorch

tags # torch


#### set device
tags # torch device # torch device if cuda # torch get device # torch device variable

```python
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
```