A complete Q-Learning implementation for the OpenAI Gym Taxi-v3 environment, along with a fully interactive Streamlit dashboard for visualizing how the trained taxi agent behaves, earns rewards, and optimizes routes.

This project is great for learning reinforcement learning and understanding how Q-learning works on a discrete action/state environment.

🎯 Features
🧠 Q-Learning Training (taxi_with_dataset.py)

Trains the Taxi-v3 agent for 16,000 episodes

Automatically saves:

Q-table

Training transitions dataset

Episode rewards

Training reward curve

Greedy policy dataset

Renders evaluation episodes after training

📊 Interactive Dashboard (taxi_dashboard.py)

Live 5×5 grid environment

Taxi position, passenger, destination indicators

Step-by-step or autoplay mode

Rewards, penalties, step cost, base fare, net profit

Full episode transition log

Training curve viewer

Greedy policy dataset viewer

📁 Project Structure
Taxi-v3-Q-Learning/
│
├── taxi_dashboard.py                # Streamlit dashboard
├── taxi_with_dataset.py             # Q-learning training script
├── requirements.txt                 # Dependencies
├── LICENSE                          # MIT License
└── README.md                        # Documentation


Auto-generated after training:

taxi_output/
│── taxi_q_table.npy
│── taxi_episode_rewards.csv
│── taxi_transitions_train.csv
│── taxi_policy_demo.csv
└── training_curve.png

⚙️ Installation
git clone https://github.com/Avijal/Taxi-v3-Q-Learning.git
cd Taxi-v3-Q-Learning
pip install -r requirements.txt

🏋️ Train the Q-Learning Agent

Run the training script:

python taxi_with_dataset.py


This will create the taxi_output/ folder containing:

Q-table

Training datasets

Training curve (PNG)

Greedy policy dataset

🎮 Launch the Dashboard

After training:

streamlit run taxi_dashboard.py


The dashboard will load the trained Q-table and display a live simulation of the taxi agent.

🧠 Advanced Explanation
🔹 State Representation

Each of the 500 states is encoded as:

(taxi_row, taxi_col, passenger_location, destination)


5 rows

5 columns

5 passenger positions (4 landmarks + inside taxi)

4 destinations

🔹 Action Space
ID	Action
0	South
1	North
2	East
3	West
4	Pickup
5	Dropoff
🔹 Reward System
Action	Reward
Successful dropoff	+20
Illegal pickup/dropoff	-10
Every step	-1
🔹 Q-Learning Update Rule
Q(s,a) ← Q(s,a) + α [ r + γ max(Q(s'),:) – Q(s,a) ]


Training uses:

α = 0.1

γ = 0.99

ε-greedy exploration (1.0 → 0.05)

📝 License

This project is licensed under the MIT License.

⭐ Support

If this project helped you, consider giving the repository a star on GitHub!
