---
title: Overview
permalink: /datasets/overview/
redirect_from: /datasets/index.html
---
**`Full dataset` in [Zenodo](https://zenodo.org/record/5130612#.YTIiZI5KiUk). `Dataloaders in [Power Data](https://nikp29.github.io/time-series-benchmarks/datasets/power/).**

### Minute-level Load and Renewable ###
- File Name
  - ISO_zone_#.csv: `CAISO_zone_1.csv` contains minute-level load, renewable and weather data from 2018 to 2020 in the zone 1 of CAISO.
- Field Description
  - Field `time`: Time of minute resolution.
  - Field `load_power`: Normalized load power.
  - Field `wind_power`: Normalized wind turbine power.
  - Field `solar_power`: Normalized solar PV power.
  - Field `DHI`: Direct normal irradiance.
  - Field `DNI`: Diffuse horizontal irradiance.
  - Field `GHI`: Global horizontal irradiance.
  - Field `Dew Point`: Dew point in degree Celsius.
  - Field `Solar Zeinth Angle`: The angle between the sun's rays and the vertical direction in degree.
  - Field `Wind Speed`: Wind speed (m/s).
  - Field `Relative Humidity`: Relative humidity (%).
  - Field `Temperature`: Temperature in degree Celsius.

### Minute-level PMU Measurements ###
- File Name
  - case #: The `case 0` folder contains all data of scenario setting #0.
    - pf_input_#.txt: Selected load, renewable and solar generation for the simulation.
    - pf_result_#.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
- Filed Description
  - Field `time`: Time of minute resolution.
  - Field `Vm_###`: Voltage magnitude (p.u.) at the bus ### in the simulated model.
  - Field `Va_###`: Voltage angle (rad) at the bus ### in the simulated model.
  - Field `P_#_#_#`: `P_3_4_1` means the active power transferring in the #1 branch from the bus 3 to 4.
  - Field `Q_#_#_#`: `Q_5_20_1` means the reactive power transferring in the #1 branch from the bus 5 to 20.

### Millisecond-level PMU Measurements ###
- File Name
  - Forced Oscillation: The folder contains all forced oscillation cases.
    - row_#: The folder contains all data of the disturbance scenario #.
      - dist.csv: Three-phased voltage at nodes in the distribution system via T+D simualtion.
      - info.csv: This file contains the start time, end time, location and type of the disturbance.
      - trans.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
  - Natural Oscillation: The folder contains all natural oscillation cases.
    - row_#: The folder contains all data of the disturbance scenario #.
      - dist.csv: Three-phased voltage at nodes in the distribution system via T+D simualtion.
      - info.csv: This file contains the start time, end time, location and type of the disturbance.
      - trans.csv: Voltage at nodes and power on branches in the transmission system via T+D simualtion.
- Filed Description
  > trans.csv
  - Field `Time(s)`: Time of millisecond resolution.
  - Field `VOLT ###`: Voltage magnitude (p.u.) at the bus ### in the transmission model.
  - Field `POWR ### TO ### CKT #`: `POWR 151 TO 152 CKT '1 '` means the active power transferring in the #1 branch from the bus 151 to 152.
  - Field `VARS ### TO ### CKT #`: `VARS 151 TO 152 CKT '1 '` means the reactive power transferring in the #1 branch from the bus 151 to 152.
  > dist.csv
  - Field `Time(s)`: Time of millisecond resolution.
  - Field `####.###.#`: `3005.633.1` means per-unit voltage magnitude of the phase A at the bus 633 of the distribution grid, the one connecting to the bus 3005 in the transmission system.

## License
The PSML dataset is published under [CC BY-NC 4.0 license](https://creativecommons.org/licenses/by-nc/4.0/), meaning everyone can use it for non-commercial research purpose.

## Suggested Citation
- Please cite the following paper when you use this data hub:  
`
X. Zheng, N. Xu, L. Trinh, D. Wu, T. Huang, S. Sivaranjani, Y. Liu, and L. Xie, "PSML: A Multi-scale Time-series Dataset for Machine Learning in Decarbonized Energy Grids." (2021).
`

## Contact
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
