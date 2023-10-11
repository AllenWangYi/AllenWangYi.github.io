---
layout: page
title: Robot Learning
description:
img: assets/img/proj3.png
importance: 1
category: work
---
**PART 1：**
In this project, I developed and trained Deep Neural Networks (DNNs) and Convolutional Neural Networks (CNNs) to navigate a simulated 2D maze environment. Utilizing an agent-based model, the project integrated dynamics, control systems, and machine learning to enable autonomous navigation towards a designated goal. The task complexity was heightened by randomizing the spawn locations of both the agent and the goal, and by incorporating multiple obstacle maps. The machine learning models were trained using human-generated data, where an expert user provided demonstrations through keyboard controls. This research illustrates the intersection of neural networks and robotics for complex autonomous navigation tasks.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/proj4_fig1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

[**Colab code**](https://colab.research.google.com/drive/1q2pl2tTfpugU69dM3x13EcOwGa1bzrV_?usp=sharing): https://colab.research.google.com/drive/1q2pl2tTfpugU69dM3x13EcOwGa1bzrV_?usp=sharing

**PART 2：**
In this project project, I employed Deep Learning techniques to train a 3-link robotic arm ('arm_student') to mimic the behavior of another similar arm ('arm_teacher') operating under known forward dynamics. The objective was to enable the 'arm_student' to learn the ground-truth forward dynamics of 'arm_teacher', which encompassed understanding the state of the arm and the application of torques at the joints. The system was initialized with a 6x1-dimensional numpy array representing state and a 3x1-dimensional array representing action in torque. The project utilized a simulation time step of 0.01 seconds, and applied a constant torque to the first joint of both arms for experimental analysis. The model was optimized for starting in a hanging position for performance consistency. Overall, this project epitomizes the application of machine learning in understanding and replicating complex mechanical dynamics
<div class="row justify-content-sm-center align-items-center">
    <div class="col-sm-9 mt-3 mt-md-0">
      <div class="image-with-caption">
        <img class="img-fluid rounded" src="/assets/img/proj4_fig1.png" alt="Your GIF Description Here">
      </div>
      <div class="caption"></div>
    </div>
</div>

[**Colab code**](https://colab.research.google.com/drive/1Gx5iswzb9uGuXg1q2kjMVEaHT90GSq9G#scrollTo=D1vjDH2fL9Tu): https://colab.research.google.com/drive/1Gx5iswzb9uGuXg1q2kjMVEaHT90GSq9G#scrollTo=D1vjDH2fL9Tu

**PART 3：**
In a continuation of previous work involving n-linked robotic arms, this project focused on leveraging neural networks for learning forward dynamics. Utilizing a provided 'teacher dynamics' model and controller, the task was to train a 'student dynamics' model to mimic the ground-truth behavior of the arm. The system architecture consisted of key Python classes to handle robot control and dynamics, including a flexible 'Robot' interface for setting and retrieving state and actions, as well as advancing the system through time steps. The state of each arm was represented as a 2n-dimensional vector, consisting of n joint positions [rad] and n joint velocities [rad/s], while the action was characterized by n torques [N-m] applied to n joints. This project not only integrated machine learning techniques with complex robotics systems but also allowed for modular extensions to arms with varying numbers of links

[**Colab code**](https://colab.research.google.com/drive/1q2pl2tTfpugU69dM3x13EcOwGa1bzrV_?usp=sharing#scrollTo=tIoNAwGQpHfH): https://colab.research.google.com/drive/1q2pl2tTfpugU69dM3x13EcOwGa1bzrV_?usp=sharing#scrollTo=tIoNAwGQpHfH

**PART 4：**
In this project, I implement reinforcement learning (RL) algorithms for an n-linked robotic arm within a custom 'ArmEnv' environment. This environment encapsulated the arm dynamics and provided essential functions like 'reset(...)' and 'step(...)', conforming to the expected RL API. I dealt with the challenge of adapting a high-dimensional, continuous action space to work with a Discrete Q-Network (DQN) by implementing action space conversions. The observation vector was extended to include both the end-effector position and goal, enabling the policy to learn to achieve arbitrary goals. Training and testing were carried out under a fixed episode length of 200 steps, with a time simulation of 0.01 seconds per step. The reward function was designed as the negative square of the L2 distance between the end-effector and the target position, optimizing the arm's movements towards set objectives.

[**Colab code**](https://colab.research.google.com/drive/1Y_WJglf208-H6yAFFn_phU49dpY23-kM?usp=sharing#scrollTo=t-JvzRuwNsYz): https://colab.research.google.com/drive/1Y_WJglf208-H6yAFFn_phU49dpY23-kM?usp=sharing#scrollTo=t-JvzRuwNsYz