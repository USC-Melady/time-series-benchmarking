---
title: Power Dataset
permalink: /datasets/power/
---

### Dataloaders ###
We prepare easy-to-use PyTorch data loaders that handle dataset processing and standardized dataset splits after download from Zenodo. Following is an example in PyTorch showing that a few lines of code are sufficient to prepare and split the dataset.

```python
from dataloader import TimeSeriesLoader

# Download and process data at './dataset/'
dataset = TimeSeriesLoader(task = "forecasting", root = 'dataset/')
data = dataset.get_split() 

train_loader = DataLoader(data["train"], batch_size=32, shuffle=True)
valid_loader = DataLoader(data["valid"], batch_size=32, shuffle=False)
test_loader = DataLoader(data["test"], batch_size=32, shuffle=False)
```
