# Maze Solver Using Q Learning Reinforcement Algorithm

## Abstract

This project utilizes the Q Learning Algorithm, a reinforcement learning method, to guide an agent through a maze to reach its target. The goal is to navigate the agent from a starting point to an endpoint by moving through the maze in the most efficient way possible, avoiding obstacles and seeking the shortest path.

## Keywords

Python, Numpy, Jupyter, PySimpleGUI, PyGame, Matplotlib, Maze, Agent, Situation, Action, Shortest Path, Grid, Q Learning, Reinforcement Learning, Rewarding, Episode, Training, Auxiliary Functions, Machine Learning, Bellman, Q Table, R Table

## Introduction

In this project, our agent (a simulated robot) must escape from obstacles and navigate through the maze using the Q learning algorithm. The agent must find the most cost-efficient route from the starting blue square to the endpoint without colliding with any red boxes to be considered successful. The agent can move in four directions: right, left, up, and down, from any white square. Each step is critical for the success of the mission, and rewards are given based on the agent's performance from start to finish.

## Concepts

The project is developed using the Python 3 programming language, with Jupyter Notebook as the development environment. PyGame is used for visualization, while the Numpy library supports the Q Learning process. PySimpleGUI helps with interface design, and Matplotlib is used for plotting.

![Libraries](https://raw.githubusercontent.com/edvujic/YAZLABII-3Project-Maze-Q-Learning/main/pictures/libraries.png)

## Methods

Q-Learning is a prominent algorithm in reinforcement learning. It involves assessing potential moves and calculating the associated rewards. A reward table holds these values, guiding the robot's decisions. Experiences are stored in a Q-Table, which the robot updates as it learns.

![Q and R Matrices](https://raw.githubusercontent.com/edvujic/YAZLABII-3Project-Maze-Q-Learning/main/pictures/QandRMatrices.png)

The environment for the Q Learning Algorithm consists of states, actions, and rewards:

- **States**: Each position in the grid represents a state, with each state corresponding to a row and column number. Red and green squares are terminal states.
- **Actions**: The agent can move up, down, right, or left, learning to avoid hitting red squares.
- **Rewards**: States have associated rewards, and the agent seeks to maximize these rewards.

![Grid States](https://raw.githubusercontent.com/edvujic/YAZLABII-3Project-Maze-Q-Learning/main/pictures/Grid_States.png)

Training involves episodes where the agent navigates the grid, with the Q table updated using the Bellman equation.

![Actions](https://raw.githubusercontent.com/edvujic/YAZLABII-3Project-Maze-Q-Learning/main/pictures/Actions.png)

`TD = r_t + (γ * Q_max(x,y)) - Q_old`

After sufficient training, the agent will have learned to navigate the maze efficiently.

## Auxiliary Functions

![Auxiliary Functions](https://raw.githubusercontent.com/edvujic/YAZLABII-3Project-Maze-Q-Learning/main/pictures/aux_func.png)

## Result

The agent successfully navigated from the start `(0,0)` to the end `(49,49)`.
