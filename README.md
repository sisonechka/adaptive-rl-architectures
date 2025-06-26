# adaptive-rl-architectures
Adaptive NAS for RL agents using PPO in the DM Control Suite (Cheetah). The system auto-selects neural architectures based on performance, reducing manual tuning and compute cost. Applicable to robotics, autonomous systems, and AI research.

📌 Project Goals
- Automate neural architecture selection for RL agents
- Reduce manual tuning and computation cost
- Improve performance in dynamic and complex environments

🧩 Key Concepts
- Neural Architecture Search (NAS): A recurrent LSTM controller generates candidate architectures by varying layer count, size, and activation functions.
- Reinforcement Learning (RL): PPO is used to train agents on proposed architectures.
- Closed training loop: Architectures are generated → agents are trained → rewards are evaluated → controller is updated.

⚙️ Architecture Parameters
- Layers: 1 to 5
- Layer Sizes: 64, 128, 256
- Activations: ReLU, Leaky ReLU, Swish

Example generated architecture:
{'pi': [128, 128, 128, 128], 'vf': [128, 128, 128, 128], 'activation': 'relu'}


🚀 Training Flow

NAS controller generates candidate architectures

PPO agent is trained on each candidate for a short cycle

Top-performing architectures are selected based on average reward

Final architectures undergo longer training for evaluation

Controller is updated and loop repeats

📊 Metrics & Evaluation
- Main metric: Average reward over training steps
- Data and results are serialized to JSON for reproducibility
- Architecture filtering avoids redundant or weak candidates
- Best architecture achieved >5.5 reward at 5000 steps (55%+ gain vs baseline)

📈 Results
- Significant improvement over baseline architectures
- Efficient filtering reduced training overhead
- Confirmed generalization across different random seeds
- Potential for adaptation to more environments and real-world robotics tasks

🔮 Future Work
- Expand to more agents and environments
- Integrate advanced NAS algorithms and meta-learning
- Apply system to robotics and autonomous navigation

🛠️ Technologies Used
- Python, PyTorch
- DeepMind Control Suite (dm_control)
- Proximal Policy Optimization (PPO)
- LSTM-based NAS controller

📂 Project Structure

├── nas_controller/         # Architecture generator (LSTM)

├── ppo_agent/              # PPO training logic

├── environments/           # DM Control Suite integration

├── data/                   # JSON logs and architecture metrics

└── utils/                  # Helpers and visualization tools

👤 Author
S. O. Balaba
Supervisor: Assoc. Prof. M. V. Holovyanko




---

# 🧠 Adaptive Neural Architecture Search for RL Agents

This project implements an adaptive system for **automated neural network architecture search (NAS)** for agents in simulated environments using **reinforcement learning (RL)**. The system combines a NAS controller and a PPO-based RL agent trained in the **DeepMind Control Suite** (`cheetah` environment).

---

## 📌 Project Goals

* Automate neural architecture selection for RL agents
* Reduce manual tuning and computation cost
* Improve performance in dynamic and complex environments

---

## 🧩 Key Concepts

* **Neural Architecture Search (NAS):** A recurrent LSTM controller generates candidate architectures by varying layer count, size, and activation functions.
* **Reinforcement Learning (RL):** PPO is used to train agents on proposed architectures.
* **Closed training loop:** Architectures are generated → agents are trained → rewards are evaluated → controller is updated.

---

## ⚙️ Architecture Parameters

* **Layers:** 1 to 5
* **Layer Sizes:** 64, 128, 256
* **Activations:** ReLU, Leaky ReLU, Swish

Example generated architecture:

```json
{
  "layers": [128, 256, 256],
  "activation": "Swish"
}
```

---

## 🚀 Training Flow

1. NAS controller generates candidate architectures
2. PPO agent is trained on each candidate for a short cycle
3. Top-performing architectures are selected based on average reward
4. Final architectures undergo longer training for evaluation
5. Controller is updated and loop repeats

---

## 📊 Metrics & Evaluation

* **Main metric:** Average reward over training steps
* Data and results are serialized to JSON for reproducibility
* Architecture filtering avoids redundant or weak candidates
* Best architecture achieved >5.5 reward at 5000 steps (55%+ gain vs baseline)

---

## 📈 Results

* Significant improvement over baseline architectures
* Efficient filtering reduced training overhead
* Confirmed generalization across different random seeds
* Potential for adaptation to more environments and real-world robotics tasks

---

## 🔮 Future Work

* Expand to more agents and environments
* Integrate advanced NAS algorithms and meta-learning
* Apply system to robotics and autonomous navigation

---

## 🛠️ Technologies Used

* Python, PyTorch
* DeepMind Control Suite (`dm_control`)
* Proximal Policy Optimization (PPO)
* LSTM-based NAS controller

---

## 📂 Project Structure

```
├── nas_controller/         # Architecture generator (LSTM)
├── ppo_agent/              # PPO training logic
├── environments/           # DM Control Suite integration
├── data/                   # JSON logs and architecture metrics
└── utils/                  # Helpers and visualization tools
```

---

## 👤 Author

**S. O. Balaba**
Supervisor: Assoc. Prof. M. V. Holovyanko

---
