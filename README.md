# mdp-parking-agent
An MDP-based reinforcement learning project where an agent learns to parallel-park on an  8 × 5 grid using Value Iteration. It finds the optimal policy under stochastic movement, tests robustness with obstacles, and proposes an extension for multi-agent navigation.

# MDP Parking Agent

This project implements a reinforcement learning agent using **Markov Decision Processes (MDPs)** and **Value Iteration** to solve a stochastic parallel-parking problem on an 8×5 grid. The agent must navigate from one of seven start states to a designated parking space while avoiding two hazard cells representing parked cars.

## 🚗 Project Overview

The environment is modeled as a gridworld where:

- Two **hazards** at `(1,1)` and `(1,5)` give a large negative reward (–1000).
- A **goal** (parking spot) at `(1,3)` gives a large positive reward (+1000).
- Seven **start states** are located along row 5: `(2,5)` to `(8,5)`.
- Movement is stochastic with **noise = 0.1**:
  - 90% chance of moving in the intended direction  
  - 10% distributed across allowed neighboring directions (excluding 180° opposite)
- Live-in reward `r` is varied in `[-20, 0]` to find the optimal policy.

The agent uses **Value Iteration** to compute utility values and derive an optimal policy that maximizes expected cumulative reward.

## 📌 Requirements Completed

### **R1 – Best Policy on Original Environment**
- Value Iteration is run for all `r ∈ [-20, 0]`.
- The **best policy** is produced when `r = 0`.
- The resulting policy directs the agent toward the parking goal while avoiding both hazards.

### **R2 – Modified Environment with Obstacle**
- A new obstacle is added at `(4,3)`.
- Value Iteration is recomputed.
- The updated policy changes only near the new obstacle, demonstrating local sensitivity.

### **R3 – Multi-Agent Extension**
A conceptual extension is provided where the transition model incorporates a **dynamic occupancy probability** to handle multiple moving agents sharing the grid.

## 📁 Files Included
- `Project3.ipynb` – Jupyter/Colab-ready notebook with full implementation  
- `report.pdf` – Written answers and policy visualizations  
- `README.md` – Project overview  
- `src/` – Python source code (optional structure)

## ▶️ How to Run

Open the notebook in **Google Colab** or **VS Code** with Jupyter to run it.
