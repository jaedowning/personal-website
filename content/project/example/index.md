---
title: Prediction of Hypertension
summary: Can we improve prediction of hypertension by adding additional variables using EHR data?
tags:
- Deep Learning
date: "2017-07-27T00:00:00Z"

# Optional external URL for project (replaces project detail page).
external_link: ""

image:
  caption: Photo by rawpixel on Unsplash
  focal_point: Smart

links:
- icon: twitter
  icon_pack: fab
  name: Follow
  url: https://twitter.com/jaedowning
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: kaiser
---

This work was done as part of my post-doc. The goal of the project was to understand if we could improve prediction of hypertension among people who didn't have hypertension at baseline. The approach here is described in detail in the attached slides that I wrote in LaTeX. The analysis for this project was done using StataMP.

First, I conducted logistic regressions (naive model and one that included the additional variables) and then compared predictive ability of models with area under the ROC. 

Next, because not all people continue over the full time period analyzed, we need to take censoring into account. Thus, I conducted survival analysis to allow for censoring. To assess predictive performance, we can use something similar to aROC - Harrell's C and Somers' D concordance. 

All these models conclude that the additional variables didn't add to the predictive performance of the model.

These approaches are grounded in epidemiology and econometrics. This was more easily understood by my colleagues. I also use a machine learning approach (Part 2) for this project. 
