---
layout: page
title: Large Scale Odomentry Learning
description: Moncular Fisheye Odometry
img: assets/img/tvofe.gif
importance: 1
category: vision
---
<div style="text-align: center;">
<img src="/assets/img/tvofe_large.gif" alt="TVOFE" style="width: 80%;"/>
<p><em>Evaluation of odometry prediction using a fisheye model compared to a baseline pinhole model. This trajectory is relatively simple, and both models perform well. However, the baseline model struggles in low-feature regions at the beginning and end of the trajectory.</em></p>
</div>


During my first year of the PhD at the Robotics Institute I was working on multiple aspects of aerial autonomy, one of which was learned monocular odometry from fisheye images. In this project, collaborators and I trained transformer models to predict single-step odometry from fisheye image pairs. We used very large datasets, roughly 52 TerraBytes of data, to train these models. The dataset will be published soon (true to 2025-02-18) and the fisheye odometry work is ongoing (so I won't be sharing too many details here just yet).   
