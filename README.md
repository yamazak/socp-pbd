# SOCP-PBD

**SOCP-PBD: Suppressing Slack in Position-Based Cloth Simulation via Second-Order Cone Programming**

This repository contains the Python implementation of **SOCP-PBD**, a novel physics simulation method for nearly inextensible cloth.

## Overview
While Position-Based Dynamics (PBD) is widely used for deformable object simulation due to its simplicity and speed, it inherently suffers from visually undesirable "slack" and stretching artifacts, especially near anchored boundary conditions. 

SOCP-PBD addresses this issue by formulating the post-prediction constraint enforcement as a global **Second-Order Cone Programming (SOCP)** problem. By globally optimizing node positions, our method strictly enforces upper bounds on edge lengths. This effectively suppresses artificial stretching while permitting the natural compression required for cloth folding.

## Features
* **Anti-Stretching Constraint:** Globally resolves distance constraints using SOCP to prevent macroscopic slack.
* **Physics Extensions:** Supports Isometric Bending Model (IBM), XPBD-based self-collision handling, and approximate friction.
* **Readable Implementation:** Built purely in Python using `cvxpy` for easy understanding, testing, and algorithmic extension.

## Requirements
The core optimization relies on [CVXPY](https://www.cvxpy.org/) and the [Clarabel](https://clarabel.org/stable/) interior-point solver.

* Python 3.8+
* `numpy`
* `scipy`
* `matplotlib`
* `cvxpy`
* `clarabel`

License
This project is licensed under the MIT License.
