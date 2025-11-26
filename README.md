# Taxi-v3 Q-Learning Using OpenAI Gym and Streamlit Dashboard

This project implements the Q-Learning algorithm on the classic Taxi-v3 environment from OpenAI Gym. It includes a complete training pipeline, dataset generation, and an interactive Streamlit dashboard for visualizing the agent’s behavior step-by-step.

This repository is suitable for academic submissions, reinforcement learning learning, and demonstrations.

---

## Features

### Q-Learning Training Script (`taxi_with_dataset.py`)
- Implements Q-Learning with epsilon-greedy exploration  
- Trains the Taxi-v3 agent for 16,000 episodes  
- Stores:
  - Learned Q-table (`taxi_q_table.npy`)
  - Transition dataset (`taxi_transitions_train.csv`)
  - Episode reward summary (`taxi_episode_rewards.csv`)
  - Greedy-policy demonstration data (`taxi_policy_demo.csv`)
  - Training reward curve (`training_curve.png`)
- Optional environment rendering for evaluation

### Streamlit Dashboard (`taxi_dashboard.py`)
- Visual 5×5 grid showing:
  - Taxi position  
  - Passenger position  
  - Destination  
  - Landmark locations (R, G, Y, B)
- Controls for:
  - Reset  
  - Step-by-step execution  
  - Play and Pause  
  - Adjustable speed
- Displays episode statistics:
  - Rewards  
  - Steps  
  - Penalties  
  - Last action  
  - Cost interpretation panel  
- Transition log viewer  
- Dataset preview and download  
- Training curve viewer  

---

## Project Structure

```
Taxi-v3-Q-Learning/
│
├── taxi_dashboard.py
├── taxi_with_dataset.py
├── requirements.txt
├── LICENSE
└── README.md
```

Auto-generated after training:

```
taxi_output/
│── taxi_q_table.npy
│── taxi_transitions_train.csv
│── taxi_episode_rewards.csv
│── taxi_policy_demo.csv
└── training_curve.png
```

---

## Installation

```
pip install -r requirements.txt
```

---

## Training the Q-Learning Agent

Run the following command:

```
python taxi_with_dataset.py
```

This will generate the `taxi_output/` directory containing:
- Q-table  
- Training transitions dataset  
- Episode reward summary  
- Demonstration dataset  
- Training curve  

---

## Running the Streamlit Dashboard

```
streamlit run taxi_dashboard.py
```

This will launch the interactive dashboard in your browser.

---

## Reinforcement Learning Details

### State Representation
Taxi-v3 has 500 states, each encoded as:

```
(taxi_row, taxi_col, passenger_location, destination)
```

### Action Space
There are 6 actions:

| ID | Action  |
|----|----------|
| 0  | South    |
| 1  | North    |
| 2  | East     |
| 3  | West     |
| 4  | Pickup   |
| 5  | Dropoff  |

### Reward Structure

| Event                    | Reward |
|--------------------------|--------|
| Successful dropoff       | +20    |
| Illegal action           | -10    |
| Each step                | -1     |

### Q-Learning Update Rule

```
Q(s, a) = Q(s, a) + α * [ r + γ * max(Q(s'), :) - Q(s, a) ]
```

With:
- Learning rate (α): 0.1  
- Discount factor (γ): 0.99  
- Epsilon (ε): decays from 1.0 to 0.05  

---

## License

This project is licensed under the MIT License.

