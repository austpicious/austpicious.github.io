---
layout: page
title: Computer Vision Image Recognition of Ancient Greek Vases 
description: CAE for feature extraction
img: assets/img/projects/greek_vase.png
importance: 5
category: tech
---


**Authors**: Austin Nguyen, Ivonne Martinez, David Harshbarger

**Affiliation**: Harvard University John A. Paulson School of Engineering and Applied Sciences, Harvard Institute for Applied Computational Science (IACS)

**Summary**: Ancient Greek vases are arguably one of the greatest archaeological findings in history due to its ability to provide pictorial insight into one of the earliest human civilizations. As museums shift inventory to digital collection, this presents a unique opportunity to apply machine learning techniques to better understand, categorize, and curate Greek vases. Our goal is to develop a model for visual recognition of images to intelligently sort images into meaningful categories. We focus on black-figure vases mainly and propose a three-staged method: (1) Convolutional autoencoder (CAE) to reduce the dimensionality of image data into a latent representation, (2) K-means clustering applied to feature representations extracted at different parts of convolutional autoencoder, and (3) Vanilla CNN with latent representation as input  𝑋  and labels  𝑌  from K-Means to evaluate which pixel regions are most important to predicting that class via SmoothGrad and Grad-CAM saliency maps. Saliency maps are a tool for Greek vase curators to interpret labels from unsupervised approaches based on their domain expertise to gauge whether labels are novel or not. We find that our model returns helpful and meaningful categories for class 2 (kylix or flat saucers/cups to hold drinks) and class 4 (lekythos or tall skinny vases used to hold oil). Future work can introduce strategic cropping to focus on scenes and/or explore a more focused scope (i.e. black-figure lekythos vases) to differentiate within a specific category of vases.



**Deliverables**: <a href='https://colab.research.google.com/drive/1JwOlwB7sVhr_2KzXLyNu1kG_K10jeKZ0?usp=sharing'>Colab Notebook</a>   
