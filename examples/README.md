# plotly-resampler examples

This directory withholds several examples, indicating the applicability of
plotly-resampler in various use cases.

## 0. basic example

The testing CI/CD of plotly resampler uses _selenium_ and _selenium-wire_ to test the
interactiveness of various figures. All these figures are shown in
the [basic example notebook](basic_example.ipynb)

### 0.1 Figurewidget example

The [figurewidget example notebook](figurewidget_example.ipynb) utilizes the `FigureWidgetResampler` wrapper to create a `go.FigureWidget` with dynamic aggregation functionality. A major advantage of this approach is that this does not create a web application, thus not needing to be able to create / forward a network port.

Additionally, this notebook highlights how to use the `FigureWidget` its on-click callback to utilize plotly for large **time series annotation**.

## 1. Dash apps

The [dash_apps](dash_apps/dash_app.py) folder contains example dash apps in
which `plotly-resampler` is integrated

| app-name | description |
| --- | --- |
| [file visualization](dash_apps/dash_app.py) | load and visualize multiple `.parquet` files with plotly-resampler |
| [dynamic sine generator](dash_apps/construct_dynamic_figures.py) | expeonential sine generator which uses [pattern matching callbacks](https://dash.plotly.com/pattern-matching-callbacks) to remove and construct plotly-resampler graphs dynamically |
| [dynamic static graph](dash_apps/dash_app_coarse_fine.py) | Visualization dashboard in which a dynamic (i.e., plotly-resampler graph) and static graph (i.e., go.Figure) are shown (made for [this issue](https://github.com/predict-idlab/plotly-resampler/issues/56)). Relayout events on the coarse graph update the dynamic graph.