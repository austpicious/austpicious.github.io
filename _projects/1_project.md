---
layout: page
title: ML for OOD Detection
description: Pest Management with Wadhwani AI
img: assets/img/projects/cotton_ace.png
importance: 1
category: tech
---
**Authors**: Austin Nguyen, Erin Tomlinson, Eric Helmold, Aloysius Lim, Molly Liu

**Affiliation**: Harvard University John A. Paulson School of Engineering and Applied Sciences, Harvard Institute for Applied Computational Science (IACS), Wadhwani AI

**Abstract**: Our goal is to identify and implement one or more effective solutions to the problem of out-of-distribution (OOD) image detection in Wadhwani AI's CottonAce pest management app, allowing it to reject errant images with minimal processing overhead. Our contributions to this work are an exploration of supervised, unsupervised, and self-supervised approaches for OOD detection. We explore convolutional autoencoders (CAEs) paired with latent dimensional analysis as our primary technique for OOD detection. We also find great potential in contrastive learning approaches to circumvent the need for costly annotation and handcrafted feature approaches which offer high interpretability and low computational costs. 

**Overview** 
Launched by Wadhwani AI, CottonAce is a pest management mobile application that helps cotton farmers manage bollworm infestations in their fields. It uses an AI algorithm to identify and count bollworms in user-submitted photos and makes customized pesticide treatment recommendations based on what is found.

**Problem** 
Images submitted should follow the app's guidelines (i.e., taken on clean white paper) to maximize the success of CottonAce in identifying and counting pests. However, a key problem is that users may submit errant images that deviate from the submission guidelines. This can lead to downstream models returning erroneous pest counts on inappropriate images and can result in user attrition. The goal of our analysis was to investigate machine learning models that can help with out-of-distribution (OOD) image detection in this setting.

<div class="row">
    <div class="col-sm mt-3 mt-md-0" style="text-align:center">
        {% include figure.html path="/assets/img/projects/project_ood_detection_example_imgs.png" title="ID vs. OOD vs. EC" class="img-fluid rounded z-depth-1" width='50%' %}
    </div>
</div>
<div class="caption">
    Figure 1: Example of ID, EC, and OOD  
</div>


**Solution** 
We explored multiple approaches focused on OOD detection with the goal of allowing the app to reject errant images with minimal overhead processing. Our recommendation is to use a model with handcrafted features because it displays competitive performance across all metrics and is small enough to be easily deployed on a mobile device. If the constraint of model size can be relaxed, a more complex modeling approach such as using a convolutional neural network (CNN) or a convolutional autoencoder (CAE) with whitened density is recommended as both of these techniques have demonstrated strong performance and have the capacity to generalize better to unseen OOD examples. 

**Highlights**

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/projects/project_ood_detection_main_results.png" title="Main results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Figure 2: Stoplight Chart of results across supervised and unsupervised techniques  
</div>


* Supervised models (rows 1-3) demonstrate strong performance on specific types of OOD images, but unsupervised/semi-supervised models (rows 4-7) may generalize better. 
* In supervised setting, handcrafted features can achieve comparable performance to CNN with dramatically reduced model size, making it highly preferable on mobile platforms.
* Image features learned by a CAE can be improved for anomaly detection tasks by applying a whitening transformation that increases the distance between in-distribution (ID) and OOD latent embeddings.
* Contrastive learning (CSI) achieves competitive results out-of-the-box; further exploration with hyperparameter tuning for this technique is warranted.
* Across all seven techniques, we observe very strong performance on identifying OOD images when tested on external datasets (Oxford Flowers and Stanford dogs). 


**Final Thoughts & Next Steps**

Several approaches have the potential to be successful for OOD detection for Wadhwani AI. Supervised techniques demonstrate strong performance on the set of OOD images observed in Wadhwani’s Open Data, but unsupervised and self-supervised techniques have the potential to generalize better on unseen OOD images. For example, contrastive learning (CSI) as a self-supervised approach produces results that are strong without much tuning.  

For future work, we advise training models with more data and better ID/OOD labels acquired via crowdsourcing to resolve edge cases, exploring generalization error on additional external datasets, and experimenting with the approach of applying a whitening transformation to the latent image representations obtained from a contrastive learning (CSI) model to combine the benefits of multiple approaches into one consolidated OOD detection model.



**Deliverables**: <a href='https://github.com/harvard-ac297r-wadhwani-ai-pm/ood-detection'>GitHub</a>  •  <a href='/assets/pdf/projects_ood_detection_wadhwani_ai.pdf'>Technical Report</a>   

