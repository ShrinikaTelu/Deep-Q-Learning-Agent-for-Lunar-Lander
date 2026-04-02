# 🚀 Deep Q-Learning Agent for Lunar Lander

This project implements a **Deep Q-Network (DQN)** agent to successfully land a lunar module on a landing pad using reinforcement learning.

The agent learns optimal actions through **experience replay** and a **target network**, stabilizing training in a continuous state space environment.

---

## 🎯 Objective

Train an intelligent agent to safely land a spacecraft on the Moon using the OpenAI Gym **LunarLander-v2** environment.

---

## 🧠 Key Concepts Used

- Deep Q-Learning (DQN)
- Bellman Equation
- Experience Replay
- Target Network (Soft Updates)
- ε-Greedy Policy
- Neural Networks (TensorFlow/Keras)

---

## 🏗️ Model Architecture

- Input Layer: State vector (8 features)
- Dense Layer: 64 units (ReLU)
- Dense Layer: 64 units (ReLU)
- Output Layer: Q-values for each action (4 actions)

---

## ⚙️ Tech Stack

- Python 3
- TensorFlow / Keras
- OpenAI Gym
- NumPy

---

## 📊 Training Details

| Parameter              | Value       |
|------------------------|------------|
| Episodes               | 2000       |
| Learning Rate (α)      | 0.001      |
| Discount Factor (γ)    | 0.995      |
| Memory Size            | 100,000    |
| Update Frequency       | Every 4 steps |

---

## 🧪 Features Implemented

✔ Deep Q-Network (DQN)  
✔ Experience Replay Buffer  
✔ Target Network with Soft Updates  
✔ ε-Greedy Exploration Strategy  
✔ Custom Training Loop using TensorFlow  

---

## 📈 Results

- Agent successfully learns to land the lunar module.
- Achieves **average reward ≥ 200** (environment solved condition).
- Training stabilizes using replay buffer and target network.

---

## 🎥 Demo

> Add your video here (optional)

---

## 📁 Project Structure


---

## 🚀 How to Run

```bash
pip install gym tensorflow numpy
python lunar_lander.ipynb
