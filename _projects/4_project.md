---
layout: page
title: ML for Mortality Prediction 
description: Focus on explainability using SHAP
img: assets/img/projects/project_mortality_shap.png
importance: 3
category: tech
---

**Authors**: Austin Nguyen, Molly Liu, Aloysius Lim

**Affiliation**: Harvard University John A. Paulson School of Engineering and Applied Sciences, Harvard Institute for Applied Computational Science (IACS)

**Summary**: Mortality is a key concern at a population-level as well as at an individual-level. In this paper, we provide three approaches to understanding mortality: (1) model that predicts as a binary outcome whether a person will survive for at least 5 years, (2) a model that predicts whether a person will survive for at least 20 years and (3) a cox proportional hazard model to predict general survival period.  We find that the best model for the first two approaches is XGBoost given the highest AUC score of 0.80, a common metric used in machine learning applications. We hope our findings provide health policymakers as well as physicians with additional information to guide their policy decisions as well as healthcare guidance. 


**Conclusions**

Connecting back to our objective of finding out which are the most important predictors of mortality, our models generally produced consistent results. Age is unsurprisingly the most important variable with gender, pulse pressure and poverty index, and a few other blood-related variables showing up as the other important variables. As such, we would recommend that such information should be collected for predictions on survival or mortality. 
 
On our interpretability objective, a one-size fit all approach to modeling is unlikely able to address all questions from users. As results interpretation depends on our modeling approach, any such interpretation should be based on the objective of the users. 

For example, an actuary may only be interested in the survival period of 5 years for the design of an insurance product. Interpretation should then be based more on the modeling results of the binary outcome of 5-years survival. For a doctor who may be interested in the survival curve of a patient for the next 20 years, interpretation should then be based on our survival analysis. 

We would strongly recommend that any actions decided based on the results of our modeling should only be made with a good understanding of our limitations, and correspondingly adjust for any limitations.  In addition, we should be mindful of ethical considerations relating to unfair outcomes from discrimination. We believe that there is scope for future work which could improve the usability of the work as described in the next section. 


**Deliverables**: <a href='/assets/pdf/project_ml_mortality_prediction.pdf'>Technical Report</a>,  <a href='https://colab.research.google.com/drive/1DnaqQCGHeu7wAA7rveHMuF3ppIvKFJjo'>Colab Notebook</a>
