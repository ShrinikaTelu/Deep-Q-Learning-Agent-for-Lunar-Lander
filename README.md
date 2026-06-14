# Deep Q-Learning Agent for Lunar Lander

A Deep Q-Network (DQN) trained to land a spacecraft in the **LunarLander-v3** environment, with an interactive browser demo that visualizes the exact environment the agent learns to solve.

## 🎮 [**Play the Live Demo**](https://shrinikatelu.github.io/Deep-Q-Learning-Agent-for-Lunar-Lander/)

Fly the lander yourself or watch an autopilot policy. See the live 8-number state vector and 4 discrete actions the agent uses.

## What's Inside

- **Training Notebook** ([`lunar_lander.ipynb`](lunar_lander.ipynb)) — DQN implementation with experience replay, target network, and ε-greedy exploration
- **Interactive Demo** — Playable browser game recreating the environment with manual controls and autopilot mode
- **State Visualization** — Real-time display of the 8-dimensional observation space (position, velocity, angle, leg contact)

## The DQN Agent

**Architecture:** 8-state input → Dense(64, ReLU) → Dense(64, ReLU) → 4 Q-values

**Key Features:**
- Target network with soft updates (Polyak averaging)
- Experience replay buffer for breaking temporal correlation
- ε-greedy exploration with decay
- Bellman equation for Q-learning: `y = r + γ · maxₐ Q̂(s', a)`

## Run Locally

**Notebook:**
```bash
pip install "gymnasium[box2d]" tensorflow numpy
jupyter notebook lunar_lander.ipynb
```

**Demo:**
```bash
python -m http.server 8000
# Open http://localhost:8000
```

---

**Provenance:** Built on the reinforcement learning lab from DeepLearning.AI's Machine Learning Specialization. Interactive demo is original work.

Built by [Shrinika Telu](https://shrinikatelu.github.io/) · [LinkedIn](https://www.linkedin.com/in/shrinikatelu/)
