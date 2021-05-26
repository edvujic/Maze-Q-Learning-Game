# Software Laboratory II 3rd Project 
<h2> Maze Solver Using Q Learning Reinforcement Algorithm </h2>
<h3> Abstract </h3>

By using the Reinforcement Learning method (sub-branch of machine learning) the aim is to ensure that the agent in a maze reaches its target with the Q Learning Algorithm.
<h3> Keywords </h3>

Python, Numpy, Jupyter, PySimpleGUI, PyGame, Matplotlib, Maze, Agent, Situation, Action, Shortest Path, Grid, Q Learning, Reinforcement Learning, Rewarding, Section, Training, Auxiliary Functions, Machine Learning, Bellman, Q Table, R Table.

<h3> Introduction </h3> 

Our robot must use the Q learning algorithm to escape from the obstacles and travel through the white areas. If our robot starts from the blue square and reaches the end in the shortest (cost efficient) way without hitting the red boxes, it will be considered successful.
The robot can move right, left, up and down starting from any white square. The steps taken must be decisive and will succeed unless the agent hits an obstacle. As a result, the robot receives the reward from the starting point to the desired target.

<h3> Concepts </h3>

Python 3 language was used as the programming language. <br/>
Jupyter Notebook was used as the development environment. <br/>
PyGame was used for visualization. <br/>
Numpy library was used for Q Learning. <br/>
PySimpleGUI library was used for interface design. <br/>
Matplotlib library was used to draw plots. <br/>

<h3> Methods </h3>

The Q-Learning algorithm is one of the most well-known algorithms of reinforcement learning. The main purpose of the algorithm is to examine the next moves and calcuate the reward that will be earned according to the examination. <br/> <br/>
The reward values are kept in the reward table (which is randomly generated). The robot's experience will be shaped according to this reward table. On the way to the goal, the robot uses the experience gained in each iteration to maximize the places he can go. The robot keeps these experiences in a table called the Q-Table. <br/> <br/>
In this project, the aim is to find the shortest path in the grid for a start and exit point selected by the user. To achieve this, Q Learning Algorithm will be applied.
In order to apply the Q Learning Algorithm, the environment must first be defined. The environment consists of three components:
<ul>
  <li> States </li>
  <li> Actions </li>
  <li> Rewards </li>
</ul>
<br/> <br/>The agent is expected to take states and rewards as input and produce actions according to them.

