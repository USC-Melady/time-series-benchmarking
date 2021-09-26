---
title: Power Dataset
permalink: /datasets/power/
---

### Dataloaders ###
We prepare easy-to-use PyTorch data loaders that handle dataset processing and standardized dataset splits after download from Zenodo. Following is an example in PyTorch showing that a few lines of code are sufficient to prepare and split the dataset.

```python
from dataloader import TimeSeriesLoader

# Download and process data at './dataset/'
dataset = TimeSeriesLoader(task="forecasting", root='dataset/')
train_loader, test_loader = dataset.load(batch_size=32, shuffle=True)
```

### Evaluators ###
We prepare easy-to-use task-specific evaluators that handle evaluation of models' output. Following is an example in PyTorch showing that a few lines of code are sufficient to get testing results.

```python
from evaluator import TimeSeriesEvaluator

evaluator  = TimeSeriesEvaluator(task="forecasting", root='dataset/')
print(evaluator.expected_input_format)
print(evaluator.expected_output_format)

predictions = # model's output
input_dict = {
    'classification': predictions[:, 0],
    'localization': predictions[:, 1],
    'detection': predictions[:, 2],
}

result_dict = evaluator.eval(input_dict)
```
