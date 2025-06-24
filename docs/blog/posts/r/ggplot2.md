---
title: Introduction to ggplot2
date: 2024-06-23
draft : true
authors:
  - thao-nguyen
summary: An introduction to data visualization with ggplot2.
tags:
  - R
  - ggplot2
  - Visualization
---

# Introduction to ggplot2

`ggplot2` is a popular R package for creating elegant and flexible data visualizations.

## Example: A Simple Plot

```r
library(ggplot2)

ggplot(mtcars, aes(x = wt, y = mpg)) +
  geom_point()
```

<!-- more -->


Test 123