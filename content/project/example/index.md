---
title: Prediction of Hypertension
summary: Parametric approaches to prediction of a health outcome 
tags:
- Prediction
- EHR 
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
url_pdf: "kaiser"
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: "kaiser"
---


For this project, we had longitudinal electronic health records of a large managed care organization, and I linked a probability survey of members with these records. Our goal was to understand if we could improve prediction of hypertension by adding the data we had from the survey. The approach here is described in detail in the attached slides that I wrote in LaTeX. The analysis for this project was done using Stata MP.

This is an illustration of a classic, parametric approach to prediction with use of ROC for regressions, and Harrell's C and Sommers D with survival analysis. Logistic regressions are (sometimes) enough. Fancy algorithms are only as good as the ability to interpret them. 

I conducted logistic regressions (naive model and one that included the additional variables) to assess whether a patient got a hypertension diagnosis over their enrollment period. Then, I compared predictive ability of models with area under the ROC. The additional variables didn't add to the predictive performance of the naive model.

Next, because not all people are enrolled in the plan over the full time period analyzed, the model would be biased if the people with hypertension died or left the plan because they were too sick. Thus we need to take censoring into account. I conducted survival analysis to allow for censoring. To assess predictive performance, we can use something similar to aROC - Harrell's C and Somers' D concordance. Again, the additional variables didn't add much to prediction.

All these models conclude that if we knew about patients education, financial strain, smoking, drinking, and marital status - we wouldn't be able to guess any better if they would develop hypertension. This is likely because there is a high correlation between these variables and the ones we already know - race, ethnicity, sex, age, and body mass index. 

The question we want to know next is, what do we do when we have a lot of variables? Which ones matter for prediction, and which ones matter most? These questions require more a more sophisticated approach such as ensemble machine learning, which I will cover in another post. 

