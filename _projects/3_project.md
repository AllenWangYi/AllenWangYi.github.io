---
layout: page
title: Object Recognition and Path Planning
description:
img: assets/img/proj3.png
importance: 1
category: work
---
**PART 1：**
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
    U-Net architecture and learning curve.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/proj3_fig3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Within the order of 1e-4 of pose estimation results.
</div>

**PART 2:**
Following part 1, I implement RRT algorithm for path planning to move the robot from one location to another while avoiding collision with the obstacles. 

Main pipeline for this grasping algorithm is as follows:
<ul>
  <li>Train a segmentation network to predict segmentation mask given an RGB image.</li>
  <li>Generate point cloud of the object as follows:
    <ul>
      <li>Capture an RGBD image.</li>
      <li>Using RGB part of it, generate segmentation mask using the trained segmentation model.</li>
      <li>Mask out this object in depth image using the generated segmentation mask.</li>
      <li>From this depth mask, generate point clouds in world coordinates for this object.</li>
    </ul>
  <li>Sample a point cloud from the original object model as well.</li>
  <li>Using ICP, align the original object point cloud to the segmented object pointcloud and hence get access to the object position and orientation in world coordinates.</li>
  <li>Grasp the object by transforming the optimal grasp pose from object frame to the world frame.</li>
  <li>use the RRT algorithm to plan the path from one bin to another and move the object to second bin.</li>

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-9 mt-3 mt-md-0">
        <video class="img-fluid rounded" controls>
            <source src="/assets/video/part4_recording.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>
</div>

<div class="row">
    <div class="col-sm-7 mt-3 mt-md-0">
        <p>&nbsp;</p> <!-- 空行 -->
        <p><strong>PART 3:</strong> In this part, I implement and train a Visual Affordance model (also called Spatial Action Map) with manually labeled data for visual robotic pack-and-place tasks.</p>
        <p>Two key assumptions in this part:</p>
        <ul>
            <li>The robot arm’s image observations come from a top-down camera, and the entire workspace is visible.</li>
            <li>The robot performs only top-down grasping, where the pose of the gripper is reduced to 3 degrees of freedom (2D translation and 1D rotation).</li>
        </ul>
    </div>
    <div class="col-sm-5 mt-3 mt-md-0">
        <p>&nbsp;</p> <!-- 空行 -->
        {% include figure.html path="assets/img/proj3_fig4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        <video class="img-fluid rounded" controls>
            <source src="/assets/video/proj_3a.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>
</div>
<div class="caption">
     Evaluate model on the same set of objects used in the training dataset. (Success rate: 0.8)
</div>

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        <video class="img-fluid rounded" controls>
            <source src="/assets/video/proj_3b.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>
</div>
<div class="caption">
    Evaluate model on a novel set of objects that were not included in the training dataset. (Success rate: 0.72)
</div>

<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-12 mt-3 mt-md-0">
        <video class="img-fluid rounded" controls>
            <source src="/assets/video/proj_3c.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </div>
</div>
<div class="caption">
    Evaluate on mixed objects: it will load 15 objects into a bin, and the model tries to move all of them into another bin within 25 attempts. (4 objects left)
</div>