---
layout: post
title:  "5 Easy RMarkdown Customization Tools"
author: Aubree Curtis
description: Learn some quick techniques to personalize your knitted Rmarkdown layout!
image: /assets/images/report.jpeg
---

If you've ever taken a data science course or worked as a data science intern, you have probably been asked to generate a statistical report at some point. While there are several methods to choose from, it's likely that you've explored using a **Markdown Editor**, a lightweight text-to-HTML conversion tool. While IDEs such as RStudio typically provide simple tutorials for how to set up a markdown, there are a variety of other customization tools available in order to make your report look more professional *(and potentially easier on the eyes!)*. 

Here are **5 simple customizations** that are sure to elevate your report's appearance and impress your boss!

*Note: This tutorial will be utilizing the RStudio IDE and is best suited for those with previous RMarkdown experience. If you need an introduction (or a refresher) to the basics of RMarkdown syntax, check out [this link](https://bookdown.org/yihui/rmarkdown/markdown-syntax.html) and explore sections 2.5 and 2.6* 

### 1. Hiding Your Setup

If you are generating a report that contains the findings gathered from external sources, such as a *.csv, .txt, etc.*, chances are your audience doesn't care to know how you sourced that data into your IDE. Luckily, with RStudio, you have complete control over which code chunks you want to be included in your final report and which chunks you want excluded -- and it's pretty simple.

In the options portion of your R chunk (denoted by a series of three backtics), simply include ```{r setup, include = FALSE}```. The `setup` argument tells RMarkdown to run that chunk first, even if it isn't first in the markdown, while the `include = FALSE` argument insures that the chunk will not be knitted in your final output, whether it be *.html, .pdf, .doc, etc.*

![Hiding Setup](https://github.com/acurtis2023/stat386-projects/blob/main/assets/images/step1_blogtut.png | width = 100)


### 2. Positioning Plots



