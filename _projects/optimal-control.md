---
title: "Optimal Control Using Physics Informed Neural Networks"
layout: project
---

*Mentor: [Suraj Kumar](https://www.linkedin.com/in/suraj-kumar-363b61a6/), UR Rao Satellite Centre, Indian Space Research Organisation*

---
### Objective

We aim to compute the **value function** corresponding to a **nonlinear dynamical system**.

The value function is denoted as $$ V(x) $$ and encodes the **optimal control policy** for the system. Specifically, it provides the optimal control input

$$
u \in U \subseteq \mathbb{R}^m
$$

at a given system state

$$
x \in \mathbb{R}^n.
$$

---

### Value Function and Hamilton–Jacobi Equation

The value function $$ V(x) $$ satisfies the **Hamilton–Jacobi Equation (HJE)**, which is a nonlinear partial differential equation (PDE).   By solving this PDE using a **Physics-Informed Neural Network (PINN)**, we obtain an approximation of the value function.

This learned value function can then be used to design a **nonlinear optimal controller**.

---

### Results and More Info
Checkout [this presentation](https://www.canva.com/design/DAG6YlWmPtk/A4OxgAm_G9T6oKV9zZcR5A/edit?utm_content=DAG6YlWmPtk&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton) for more information and results.

---

## References

1. **Furfaro, R., D’Ambrosio, A., Schiassi, E., & Scorsoglio, A. (2022).**  
   *Physics-Informed Neural Networks for Closed-Loop Guidance and Control in Aerospace Systems.*  
   **AIAA SCITECH 2022 Forum**, San Diego, CA & Virtual.  
   https://doi.org/10.2514/6.2022-0361

2. **Srinivasa, T. R., & Kumar, S. (2025).**  
   *Solving Infinite-Horizon Optimal Control Problems using the Extreme Theory of Functional Connections.*  
   Accepted at Indian Controls Conference; arXiv preprint **arXiv:2510.27187**.  
   https://doi.org/10.48550/arXiv.2510.27187


