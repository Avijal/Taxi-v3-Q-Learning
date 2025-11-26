Taxi-v3 Q-Learning Using OpenAI Gym and Streamlit Dashboard
This project implements the Q-Learning algorithm on the classic Taxi-v3 environment from OpenAI Gym. It includes a complete training pipeline, dataset generation, and an interactive Streamlit dashboard for visualizing the agent’s behavior step-by-step.

This repository is suitable for academic submissions, reinforcement learning learning, and demonstrations.

Features
Q-Learning Training Script (taxi_with_dataset.py)
Implements Q-Learning with epsilon-greedy exploration
Trains the Taxi-v3 agent for configurable episodes
Stores:
Learned Q-table (taxi_q_table.npy)
Transition data (taxi_transitions_train.csv)
Episode reward summary (taxi_episode_rewards.csv)
Greedy-policy demonstration dataset (taxi_policy_demo.csv)
Training reward curve (training_curve.png)
Optional environment rendering for evaluation
Streamlit Dashboard (taxi_dashboard.py)
Visual 5x5 grid showing:
Taxi position
Passenger position
Destination
Landmark locations (R, G, Y, B)
Controls for:
Reset
Step-by-step execution
Play and Pause
Adjustable speed
Displays episode statistics:
Rewards
Steps
Penalties
Last action
Cost interpretation panel
Transition log viewer
Dataset preview and download
Training curve viewer
Project Structure
. ├── taxi_with_dataset.py # Q-learning training and dataset generation ├── taxi_dashboard.py # Streamlit-based interactive dashboard ├── requirements.txt └── taxi_output/ # Generated after training ├── taxi_q_table.npy ├── taxi_transitions_train.csv ├── taxi_episode_rewards.csv ├── taxi_policy_demo.csv └── training_curve.png

Installation
Install required dependencies:

pip install -r requirements.txt

Training the Agent
Run the training script:

python taxi_with_dataset.py

This will generate the taxi_output folder automatically.

Running the Dashboard
Launch the Streamlit dashboard:

streamlit run taxi_dashboard.py

This opens an interactive UI in your browser where you can visualize the Taxi agent step by step.

Q-Learning Formula
Q(s, a) = Q(s, a) + α * [ r + γ * max(Q(s', a')) - Q(s, a) ]

Where:

α (alpha) is the learning rate
γ (gamma) is the discount factor
ε-greedy is used for exploration
Files Generated After Training
File	Description
taxi_q_table.npy	The learned Q-table
taxi_transitions_train.csv	Full transition log for all training steps
taxi_episode_rewards.csv	Total reward for each episode
training_curve.png	Training progress plotted over episodes
taxi_policy_demo.csv	Greedy-policy demonstration dataset
Requirements
Python 3.8 or higher
Streamlit
Gymnasium (+ toy_text)
NumPy
Pandas
Matplotlib
See requirements.txt for full details.
