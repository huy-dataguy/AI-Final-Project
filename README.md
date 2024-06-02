Welcome to the AI Final Project repository! This project contains implementations of three key algorithms developed for the Artificial Intelligence course's final project. These algorithms are applied to solve various tasks in the field of reinforcement learning and search algorithms.

Q-Learning
Introduction: Q-Learning is a reinforcement learning algorithm used for solving pathfinding problems in Markov Decision Process (MDP) environments. It estimates the value of each state-action pair in a given problem and updates these values based on experience gained from interacting with the environment.

Key Concepts:
Q-Value Table: Q-Learning uses a Q-Value table to estimate the value of each state-action pair in an MDP. These values are updated through experience gained by interacting with the environment.
Exploration and Exploitation: Q-Learning balances exploration (trying new actions) and exploitation (using known actions) to learn optimal strategies.
Experience Replay: Q-Learning with Experience Replay improves stability and performance by storing and randomly sampling experiences from a replay memory during the Q-Value update process.

The formula for updating the Q-value
Q(s, a) = Q(s, a) + α * [r + γ * max(Q(s', a')) - Q(s, a)]

Advantages:
Effective in many pathfinding problems.
Applicable to various complex environments.
Disadvantages:
Requires a large Q-Value table for environments with many states.
Difficulty in choosing values for learning rate (α) and discount factor (γ).

Online Depth-First Search (DFS)
Introduction: Online DFS, or Online Depth-First Search, is a variant of the Depth-First Search algorithm designed to operate in environments where the structure of the graph is not known beforehand or is gradually revealed during the search process.

Key Concepts:
Dynamic Exploration: Vertices and edges of the graph are explored step by step.
Memory-Efficient: Since only a portion of the graph is stored at any given time, Online DFS can use memory more efficiently compared to offline versions.
Adaptation to Changing Environments: Online DFS is especially suitable for dynamic graphs or in environments where the graph may change during the search process.

Pseudocode:
function ONLINE-DFS-AGENT(problem, s') returns an action
    s, a: states and actions, initially null
    result: table storing results of actions
    untried: table storing untried actions for each state
    unbacktracked: table storing states that agent has not yet backtracked from

    if GOAL-TEST(s') then return stop
    if s' is a new state (not in untried), add untried actions for s'
    if s is not null, record s and a in result and add s to unbacktracked[s']
    
    if untried[s'] is empty, select action from unbacktracked[s'] and assign to a
    else select action from untried[s'] and assign to a
    
    s' is updated, and return action a
    
Advantages:
Easy to understand and implement.
Fast in certain cases.
Uses relatively less memory compared to many other algorithms.
Disadvantages:
Does not guarantee finding the shortest path.
May fall into an infinite loop if the graph has cycles.
Not suitable for large graphs.

Learning Real-Time A* (LRTA*)
Introduction: Learning Real-Time A* (LRTA*) is an algorithm developed for real-time search in dynamic environments, interleaving planning and action execution in an online manner. It estimates the cost of reaching the goal from each state and selects actions based on these estimates.

Key Concepts:
Optimism under Uncertainty: LRTA* assumes untried actions will lead immediately to the goal with the lowest possible cost, encouraging exploration of potentially promising paths.
Heuristic-Based: Utilizes heuristic estimates of costs from the current state to the goal to guide decision-making.
Continuous Learning: Improves performance by continuously updating cost estimates and exploring new actions.

Pseudocode:
function LRTA*(problem, s') returns an action
    s: current state
    result: table storing results of actions
    H: table storing heuristic estimates
    a: selected action
    if GOAL-TEST(s') then return stop
    if s' is a new state (not in H), estimate cost from s' to goal using heuristic h
    if s is not the initial state (not null), update cost estimate for s
    select action a based on the lowest estimated cost using LRTA*-COST
    update current state s' and return action a

Advantages:
Guarantees finding a goal in finite spaces.

Dependencies:
Python 3.x
Gym library
Usage:
Clone the repository:
git clone https://github.com/your_username/AI-Final-Project.git
Navigate to the project directory:
cd AI-Final-Project

Open and run the Jupyter Notebook files to explore the implementations of each algorithm.
Thank you for exploring our AI Final Project! If you have any questions or feedback, feel free to reach out. Happy coding!

