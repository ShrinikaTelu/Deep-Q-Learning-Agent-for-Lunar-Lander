# Deep Q-Learning Agent for Lunar Lander

A Deep Q-Network (DQN) trained to land a spacecraft in the OpenAI Gym
**LunarLander** environment — plus a **playable browser game** that visualizes
the exact environment the agent learns to solve.

🎮 **Play / watch the demo:** _add your GitHub Pages URL here_
📓 **Training notebook:** [`lunar_lander.ipynb`](lunar_lander.ipynb)

## The interactive demo

The agent itself is a TensorFlow model, so the browser demo (`web/index.html`)
re-creates the **environment** rather than running the trained network in-page:
a faithful LunarLander with the same 8-dimensional state vector and 4 discrete
actions the DQN reasons over. It's a single static HTML file — no build, no
backend, no dependencies.

- **You fly** — arrow keys drive the thrusters; feel why the control problem is
  hard (gravity, drift, a narrow pad).
- **Autopilot** — a clean hand-written policy that mimics what a converged DQN
  does: control descent rate, then steer horizontal velocity to the pad.
  (Verified to land 100% of randomized starts across 1,000 simulations.)
- **State-vector panel** — shows the live 8 numbers the agent observes
  (position, velocity, angle, leg contact) and highlights which of the 4
  actions is firing each frame. The demo doubles as an explainer of *what the
  agent sees and chooses*.

## The DQN agent (notebook)

The notebook implements the standard DQN algorithm:

- **Q-network + target network** — a second, slowly-updated network stabilizes
  the learning target (soft updates via Polyak averaging).
- **Experience replay** — transitions are stored in a buffer and sampled in
  mini-batches, breaking correlation between consecutive steps.
- **ε-greedy exploration** — exploration decays over training toward
  exploitation of the learned policy.
- **Bellman target** — `y = r + γ · maxₐ Q̂(s', a)` for non-terminal steps.

Network: 8-feature state → Dense(64, ReLU) → Dense(64, ReLU) → 4 Q-values.

> **Provenance:** this implementation is built on the reinforcement-learning
> lab from the DeepLearning.AI *Machine Learning Specialization*. The DQN
> structure follows that exercise; the interactive browser demo is original
> work built to visualize the environment.

## Run the notebook

LunarLander now lives in **Gymnasium** (the maintained successor to `gym`),
and the environment is `LunarLander-v3`:

```bash
pip install "gymnasium[box2d]" tensorflow numpy
jupyter notebook lunar_lander.ipynb
```

## Run the demo locally

```bash
cd web && python -m http.server 8000   # then open http://localhost:8000
```

---

Built by [Shrinika Telu](https://shrinikatelu.github.io/) — [LinkedIn](https://www.linkedin.com/in/shrinikatelu/)
