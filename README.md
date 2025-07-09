# Reinforcement Learning

This repository contains notes, concepts, and code related to Reinforcement Learning (RL).

---

## Overview

Reinforcement Learning problems are often modeled using a **Markov Decision Process (MDP)**, which is defined by four components:  
**S** (States), **A** (Actions), **R** (Rewards), and **P** (Transition Probabilities).

A key property of MDPs is the **Markov assumption**:  
> The next state depends only on the current state and action, **not** on the sequence of past states (i.e., history-independent).

### Types of MDPs:
- **Finite vs Infinite MDPs** – depending on the number of states/actions
- **Episodic vs Continuing MDPs** – whether episodes have an end or go on indefinitely

---

## Core Concepts

- **Trajectory** vs **Episode**  
  A trajectory is a sequence of states, actions, and rewards; an episode ends in a terminal state.

- **Reward** vs **Return**  
  Reward is the immediate feedback, while return is the sum of future rewards (possibly discounted).

- **Discount Factor (γ)**  
  Determines how much future rewards are taken into account. A value close to 1 means long-term rewards are prioritized.

- **Policy (π)**  
  A strategy used by the agent to choose actions:
  - **Deterministic**: Always picks the same action for a given state  
  - **Stochastic**: Samples actions from a probability distribution over actions

- **Value Functions**  
  - **State-value function**: *v(s)* — expected return from state *s*  
  - **Action-value function**: *q(s, a)* — expected return from state *s* taking action *a*

- **Goal of RL**  
  Learn a policy that **maximizes the expected sum of discounted rewards** over time.

---

## Bellman Equations

Bellman equations provide recursive definitions of value functions:

- **For state-value function**:  
  v(s) = Σₐ π(a|s) Σₛ′,r P(s′, r | s, a) [r + γ · v(s′)]

- **For action-value function**:  
  q(s, a) = Σₛ′,r P(s′, r | s, a) [r + γ · Σₐ′ π(a′|s′) · q(s′, a′)]


---
**Why does the value at the current state depend on the next state?**

Because in Reinforcement Learning, the value of being in a state is not just about the immediate reward, but also about the future rewards the agent expects after taking an action


