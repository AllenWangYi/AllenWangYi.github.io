---
layout: page
title: Aggressive Motion Planner
detailed-title: Kinodynamic Aggressive Trajectory Planner
description: 
img: assets/img/1.jpg
importance: 2
category: main
---

<hr />

<div class="container">
    <div class="row-1">
        <!-- <div class="col-md-8"> -->
            <p>
            Proposed a sampling-based bi-level planning algorithm for non-holonomic constrained robots to achieve aggressive maneuvers.The global problem is tackled by solving locally and in parallel within the highly-constrained regions of the state space, then refined globally.
            </p>
            <p>
            The overview of four steps of this algorithm：
            </p>
            <ul>
                <li>
                  Explore in the holonomic space to identify regions with constraints.
                </li>
                <li>
                   Sampling configurations with maximum margins within each constrained region in parallel.
                </li>
                <li>
                    Identify the escape velocity for each constrained region and generated local trajectories within each region that satisfy the non-holonomic constraints.
                </li>
                <li>
                   Integrate trajectories into a single trajectory and refine it.
                </li>

            </ul>
        <!-- </div> -->
    </div>
        
</div>



