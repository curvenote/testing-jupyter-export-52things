---
title: "Simple Machine Learning: A Mini Tutorial"
description: ""
date: 2021-01-27T15:20:30.903Z
author:
  - Didi Ool
name: ooi-simple-machine-learning-tutorial
oxa: oxa:5w7N97WoctdHdShYPn5p/QrDB7UysRuCZnYILLVyy
---

# Simple Machine Learning: A Mini Tutorial

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/oPAT4lXhptmoNVDQYnpH.1","pinned":false}

Coming from a pure geology background in the undergraduate, without any statistics prerequisites – you can imagine the horror of jumping into a PhD that deals with a horde of data under geology supervisors! Here I would like to present to take us through the whole basic machine learning workflow, which includes the underrated exploratory data analysis (EDA). This is something I wished I had when I started my PhD and life I imagine, would be simpler. The goal for this multivariate analysis is to look for the highest independence between variables that correlate to produce the best predictor model.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/56PKK5AF7Zn53VvEq6F4.1","pinned":false}

## 6 Steps in a Machine Learning workflow

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/EtFFUCPRvujqRdOED8RP.1","pinned":false}

**1. Understand each variable independently**\
This first step, often overlooked by many, is crucial as it will significantly affect our machine learning model. We can simply do univariate analyses by knowing the distribution shape of our data, the range of values (including outliers), determine the normality, quantify the missing-ness (N/A, nulls) and perform descriptive statistics on them.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/9QvxUyCgee3U1Dpp63rV.1","pinned":false}

Statistical Plots: *Box plot, Quantile-quantile (QQ) plot*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/3xtIziayG3wBJjV0XqBK.1","pinned":false}

**2. Feature engineering**\
The portion of Machine Learning that validates the need for us human geoscientist – the subject matter expertise (SME)! Our job here is to determine whether a set of variables should be converted to categorical (low-medium-high), to make new metrics (Variable 1/Variable 2), transform the data (log or square root), create formulaic columns, manually categorize data (with tags), handle data imputation, and/or deal with outliers.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/fLJ5JazkA4Blai2jmDEj.1","pinned":false}

Tools: *Pandas, Excel (yes for small data!)*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/TF5x99dtDtSZI256be9Q.1","pinned":false}

**3. Understand bivariate relationship**\
Linear regression on data relationships are commonly used by geoscienstists, but the statistical significance of the regression (*p-value*) and the statistically significant differences (*ANOVA* or *Kruskal Wallis, Chi-square*) are too often neglected. *R<sup>2</sup>* only tells us the potential dependency among predictors, but it is not a validation of whether they are and statistically significant. *P-value* helps to quantify our ‘guessing’. The simple trick here is for the bivariate data to have the smallest *p-value* and highest *R<sup>2</sup>*.

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/0VTWznJRxNRBvJYPu5JY.1","pinned":false}

Tools: *Scikit-learn, Plotly, SciPy*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/kLaWvNXG6JeMYm6zyzEk.1","pinned":false}

**4. Exploit multivariate patterns**\
To understand variation of our dataset, aka relationship of ALL variables versus ALL variables, we can use dimensionality reduction techniques such as *Principal Component Analysis*. This is important especially if we have more than 10 interdependent variables! We can get sense of the multi co-linearity of your variables and identify variables (and which of them are outliers) that provide the most information. Here we can get rid of uninformative variables for your model creation, unless you are looking to determine an outlier like a fault, salt bodies, or a lost circulation zone?

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/Lab3UDwEfvfWqFglUGLM.1","pinned":false}

Tools: *prcomp in R, scikit-learn*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/pq6nPg28tFH2vCMRJZKy.1","pinned":false}

**5. Train your Machine Learning model** Now we are ready to create your first multivariate model! Divide up your data into a training and validation set, preferably in 80:20. Lower ratio allows for better predictability, but only do this if you have really large data. Start with the minimum number of variables and train competing models with a simple algorithm, like *random forest*. Tools for 5-6: *TensorFlow, Scikit-learn, Keras, Caffe, PyTorch etc*

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/6DFEeCsPL39IyPrvA0zb.1","pinned":false}

**6. Prediction!** Now use your remaining 20% of your dataset set aside for validation to test your model. The model performances typically entails: *residual standard error (RSE), root mean square error (RMSE), degrees of freedom, adjusted R2, F-stats* and *p-value*. *Residual* analysis tells us the difference between actual data against the value predicted by your model. This is the part where you will have to repeat step 2 and 3 – 6 to get the ‘best model’, or immediately apply model(s) to new unseen data. Run sensitivity analysis on parameters and compare outputs of competing models!

+++ {"oxa":"oxa:5w7N97WoctdHdShYPn5p/hWOtI4zy6gnEbVegWenh.1","pinned":false}

Voila! You are now ready for the next adventure in being an AI geoscientist!

