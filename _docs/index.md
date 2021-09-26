---
title: Getting Started
permalink: /datasets/overview/
redirect_from: /datasets/index.html
---
**`Full dataset` in [Zenodo](https://zenodo.org/record/5130612#.YTIiZI5KiUk). `Descriptions` for [Power Data](https://nikp29.github.io/time-series-benchmarks/datasets/power/).**

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

### License ###
The PSML dataset is published under [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/), meaning everyone can use it for non-commercial research purpose.

### Suggested Citation ###
Please cite the following paper when you use this data hub:  
```
X. Zheng, N. Xu, L. Trinh, D. Wu, T. Huang, S. Sivaranjani, Y. Liu, and L. Xie, "PSML: A Multi-scale Time-series Dataset for Machine Learning in Decarbonized Energy Grids." (2021).
```

### Contact ###
Please contact us if you need further technical support or search for cooperation. Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.\
Email contact: &nbsp; [Le Xie](mailto:le.xie@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Yan Liu](mailto:yanliu.cs@usc.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Xiangtian Zheng](mailto:zxt0515@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Nan Xu](mailto:nanx@usc.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Dongqi Wu](mailto:dqwu@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Loc Trinh](mailto:loctrinh@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [Tong Huang](mailto:tonghuang@tamu.edu?subject=[GitHub]%20POWERDATASET), &nbsp; [S. Sivaranjani](mailto:sivaranjani@tamu.edu?subject=[GitHub]%20POWERDATASET). 


<!-- ## Getting started

[GitHub Pages](https://pages.github.com) can automatically generate and serve the website for you.
Let's say you have a username/organisation `my-org` and project `my-proj`; if you locate Jekyll source under `docs` folder of master branch in your repo `github.com/my-org/my-proj`, the website will be served on `my-org.github.io/my-proj`.
The good thing about coupling your documentation with the source repo is, whenever you merge features with regarding content to master branch, it will also be published on the webpage instantly.

1. Just [download the source](https://github.com/aksakalli/jekyll-doc-theme/archive/gh-pages.zip) into your repo under `docs` folder.
2. Edit site settings in `_config.yml` file according to your project. !!! `baseurl` should be your website's relative URI like `/my-proj` !!!
3. Replace `favicon.ico` and `assets/img/logonav.png` with your own logo.

## Writing content

### Docs

Docs are [collections](https://jekyllrb.com/docs/collections/) of pages stored under `_docs` folder. To create a new page:

**1.** Create a new Markdown as `_docs/my-page.md` and write [front matter](https://jekyllrb.com/docs/frontmatter/) & content such as:

```
---
title: My Page
permalink: /docs/my-page/
---

Hello World!
```

**2.** Add the pagename to `_data/docs.yml` file in order to list in docs navigation panel:

```
- title: My Group Title
  docs:
  - my-page
```

### Blog posts

Add a new Markdown file such as `2017-05-09-my-post.md` and write the content similar to other post examples.

### Pages

The homepage is located under `index.html` file. You can change the content or design completely different welcome page for your taste. (You can use [bootstrap components](http://getbootstrap.com/components/))

In order to add a new page, create a new `.html` or `.md` (markdown) file under root directory and link it in `_includes/topnav.html`. -->
