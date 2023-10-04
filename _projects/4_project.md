---
layout: page
title: Object Recognition and Path Planning
description:
img: assets/img/proj3.png
importance: 1
category: work
---

I implemented a neural network models(simplified U-Net) focused on image segmentation, achieving a 90% mIoU score. I utilized the Iterative Closest Point (ICP) algorithm for Pose Estimation, aligning point clouds for object recognition. 

<div class="row justify-content-sm-center">
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/proj3_fig1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-6 mt-3 mt-md-0">
        {% include figure.html path="assets/img/proj3_fig2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    U-Net architecture and learning curve
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/proj3_fig3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Within the order of 1e-4 of pose estimation results
</div>

I implement RRT algorithm for path planning to move the robot from one location to another while avoiding collision with the obstacles. 