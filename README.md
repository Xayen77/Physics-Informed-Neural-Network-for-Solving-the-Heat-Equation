# Physics-Informed Neural Network for Solving the Heat Equation

This repository implements a **Physics-Informed Neural Network (PINN)** to solve the **one-dimensional heat equation** with a source term. The network is designed to predict the temperature distribution over time and space using deep learning techniques, incorporating both initial condition data and physical constraints from the heat equation.

## Problem Description

The heat equation is a partial differential equation that describes the distribution of heat (or temperature) in a given region over time. In one spatial dimension, the heat equation with a source term can be written as:

$$ u_t = \alpha u_{xx} + Q(x) $$

Where:
- \( u(t, x) \) is the temperature distribution.
- \( \alpha \) is the thermal diffusivity constant.
- \( Q(x) \) is the heat source term.
  
In this implementation:
- The neural network learns to approximate \( u(t, x) \) by minimizing the error between its predictions and the heat equation.
  
## Model Architecture

The neural network consists of:
- 3 fully connected layers with ReLU activations.
- Inputs are the spatial coordinate \(x\) and time \(t\).
- Output is the predicted temperature \( u(t, x) \).

## Heat Equation Loss Function

The loss function includes two components:
1. **Data Loss**: Ensures that the network's prediction matches the initial temperature distribution.
2. **Physics Loss**: Ensures that the network's predictions satisfy the heat equation by computing the gradients of the predicted temperatures and penalizing deviations from the PDE.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/pinn-heat-equation.git
   cd pinn-heat-equation
