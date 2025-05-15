# Autonomous Driving Agents with Reinforcement Learning 🚗

# self-driving-technology-


## 1. Project Overview

The goal of this project is to compare the performance of different reinforcement learning algorithms in autonomous driving scenarios. Agents were trained in three driving environments and evaluated based on performance metrics such as mean episode reward and success rate. Various learning rates and discount factors were tested to understand their effect on learning behavior and stability.

Project Files: [Google Drive Link](https://drive.google.com/drive/folders/1djC_2D1YeeZIHfGqngXRkDqqzqLmlGGY?usp=sharing)


## 2. Environments Used

| Environment       | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| `highway-fast-v0` | High-speed driving, safe lane switching required                            |
| `intersection-v0` | Cross-traffic navigation at intersections                                    |
| `roundabout-v0`   | Merging into a circular stream of traffic and exiting safely                |

## 3. Algorithms Implemented

- DQN (Deep Q-Network)
- PPO (Proximal Policy Optimization)
- A2C (Advantage Actor-Critic)

Each algorithm was evaluated under different configurations of:
- Learning Rate (`lr`) ∈ {0.0005, 0.001}
- Discount Factor (`γ`) ∈ {0.8, 0.95}


## 4. Evaluation Metrics

| Metric              | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Mean Episode Reward | Average cumulative reward per episode                                       |
| Success Rate        | Percentage of episodes where the agent met success conditions               |

## 5. Summary of Key Findings

| Environment       | Best Algorithm(s) | Optimal γ | Optimal LR  | Notes                                                              |
|-------------------|-------------------|-----------|-------------|---------------------------------------------------------------------|
| highway-fast-v0   | DQN, PPO          | 0.8       | 0.0005–0.001| Short-term planning worked best                                    |
| intersection-v0   | PPO               | 0.95      | 0.001       | Long-term planning essential due to cross-traffic                  |
| roundabout-v0     | PPO, A2C          | 0.8–0.95  | 0.0005–0.001| Fast decision-making was critical, lower γ often outperformed      |


## 6. Observations by Algorithm

### DQN:
- Performs best in simpler environments (e.g., highway).
- Lower learning rate and lower discount factor resulted in better lane-switching behavior.
- Struggled in environments requiring long-term planning (e.g., intersections).

### PPO:
- Most versatile across environments.
- Requires tuning but excels in complex traffic conditions like roundabouts.
- Benefited from lower discount factors in fast-reactive environments.

### A2C:
- Sensitive to hyperparameters.
- Best used with low learning rates.
- Strong results in roundabouts and highways, struggled with intersections.

## 7. Challenges Faced

- High sensitivity to hyperparameters.
- Large amount of data and logs from training required detailed analysis.
- Initial difficulty in interpreting TensorBoard visualizations.
- Limited time to explore additional advanced algorithms (e.g., SAC).


## 8. Future Work

- Explore additional environments and traffic scenarios.
- Implement more advanced RL algorithms (e.g., SAC, TD3).
- Incorporate rule-based baselines for comparison.
- Improve reward shaping for more guided learning.

