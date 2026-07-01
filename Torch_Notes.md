# Pytorch

tags # torch


* ### set device
tags # torch device # torch device if cuda # torch get device # torch device variable

```python
device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')
```


## lightning

* ### progress bar refresh, reduce freeze

tags # progress bar refresh rate # progress bar freeze # torch lightning progress refresh # progress bar stuck

1. set refresh rate before constructing progress_bar

2. put into callbacks

```python
mnist_model = MNISTModel()

# prepare progress bar, set refresh rate
our_progress_bar = TQDMProgressBar(refresh_rate=10)
trainer = pl.Trainer(max_epochs=10, callbacks=[our_progress_bar])

trainer.fit(mnist_model)
```