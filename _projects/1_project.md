---
layout: page
title: Design and Control an Embedded Manipulator
description:
img: assets/img/manipulator.jpg
importance: 1
category: work
---

This project was devoted to creating a sophisticated manipulator control system utilizing Field-Programmable Gate Arrays (FPGAs), renowned for their rapid processing, adaptability, and energy efficiency. The methodology encompassed a unique approach where the robotic arm was controlled through a keyboard. Specific keys were designed to command movements in different directions and precise arm positions, with the Inverse Kinematics algorithm implemented using C language on the FPGA to ensure pinpoint control.

The mechanical design phase was an intricate process involving the utilization of 3D modeling software like SolidWorks and 3D printing technology. The manipulator, consisting of 4 servos, was meticulously crafted to manage the movement of links, the rotation of the body relative to the base, and the control of the end effector. Inverse Kinematics was leveraged to calculate the joint angles (theta1, theta2, theta3) required for a desired end-effector position, while workspace analysis determined the operational range of the end-effector.

Hardware design, centered around the DE1-SOC board and the onboard 5CSEMA5F31C6N chip, facilitated processing, storage, and physical interface management. Signal transmission for the keyboard and robotic arm was achieved through the board’s built-in GPIO and USB interface. The design featured a comprehensive control system, including debugging features and operational modes. The Peripherals were designed to acquire control signals for the robotic arm via an external keyboard, translating into four angular data points, which were processed and transmitted to the servomotors in real-time through General Purpose Input/Output (GPIO) interfaces, using Pulse Width Modulation (PWM) for precise angular adjustments.

Power management was meticulous, with an additional power adapter incorporated to safeguard the FPGA power supply and ensure stable servomotor operation. Sophisticated design features were implemented to provide efficient control of the robotic arm, demonstrating system functionality and efficiency.

The software interface was expertly constructed using the libusb 1.0 C library, renowned for its ability to ensure smooth interactions across various operating systems. A responsive chain of actions was initiated upon the pressing of a key, enabling real-time adjustments to the manipulator’s position. A unique integration process transmitted movement values through the Avalon bus, ensuring seamless communication between the keyboard inputs and manipulator.

In conclusion, this project stands as a testament to innovative engineering and thoughtful design, harmonizing software and hardware components to create a precise and efficient manipulator control system. 

<div class="row justify-content-sm-center align-items-center">
    <div class="video-container">
        <iframe class="video z-depth-1 rounded" src="https://www.youtube.com/embed/w3h8Cny9yQ4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen width="700" height="500"></iframe>
    </div>
</div>


