# Software Laboratory II 3rd Project 
<h2> Maze Solver Using Q Learning Reinforcement Algorithm </h2>
<h3> Abstract </h3>

By using the Reinforcement Learning method (sub-branch of machine learning) the aim is to ensure that the agent in a maze reaches its target with the Q Learning Algorithm.
<h3> Keywords </h3>

Python, Numpy, Jupyter, PySimpleGUI, PyGame, Matplotlib, Maze, Agent, Situation, Action, Shortest Path, Grid, Q Learning, Reinforcement Learning, Rewarding, Section, Training, Auxiliary Functions, Machine Learning, Bellman, Q Table, R Table.

<h3> Introduction </h3> 

Our robot (agent) must use the Q learning algorithm to escape from the obstacles and travel through the white areas. If our robot starts from the blue square and reaches the end in the shortest (cost efficient) way without hitting the red boxes, it will be considered successful.
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
<br/>The agent is expected to take states and rewards as input and produce actions according to them.
<br/> <br/>
<p> Red squares in the grid represent obstacles, blue squares agent, green squares exit (target), white squares represent paths through which the agent can pass.
Each position (square) in the grid is a state. Each situation has a row and column number. Red and green squares are called terminal states.
A training episode will end when the agent gets to the red or green square. If it reaches the green square, the agent has arrived at its target, but if it reaches a red square, it will fail due to the wrong move. When it comes to a white square, it will move to another square
</p>

<p>There are 4 actions in this scenario. The agent can go up, down, right or left. Naturally, the agent is expected to learn not to hit the red squares. </p>
<p>In order for the agent to learn, each state must have a rewarding coefficient. The agent can start on any white square, but his goal is always the same - to maximize reward. In this case, the concept of negative rewarding is encountered. Negative reward is punishment and is used for every state except the exit (target) state. This helps the agent find the shortcut because the agent always tries to minimize the punishment. </p>

<p>The number of steps and rewards are calculated for each episode. After the starting position of the agent is taken, the Q table is updated by using Bellman equation in each episode for the actions that the agent randomly chooses until the agent reaches a red square. Temporary difference is calculated with Bellman equation.</p>

<img src="https://latex.codecogs.com/gif.latex?TD&space;=&space;r_{t}&space;&plus;&space;(\gamma&space;*&space;Q_{max}(x,y))&space;-&space;Q_{old}" title="TD = r_{t} + (\gamma * Q_{max}(x,y)) - Q_{old}" />

<p>Once this has been done for 100,000 episodes, the agent may have been adequately trained. If it is not sufficiently trained, this code snippet must be rerun.</p>


<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;Electron\&quot; modified=\&quot;2021-05-26T13:24:38.259Z\&quot; agent=\&quot;5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) draw.io/14.6.13 Chrome/89.0.4389.128 Electron/12.0.7 Safari/537.36\&quot; etag=\&quot;luZ1BeFiG2TApeh60yfr\&quot; version=\&quot;14.6.13\&quot; type=\&quot;device\&quot;&gt;&lt;diagram id=\&quot;HGXxsyEd32zGRZps0r9z\&quot; name=\&quot;Page-1\&quot;&gt;3ZpLd6IwFMc/jcvOMUREl6O200XnnJ7pYmaWKYmQFgknhKr99BMkUTDo9KUhriQ3T37/m8eV9OB0sfrBURb/ZJgkPa+PVz0463ke6HsD+VNa1pXFD0BliDjFqtDO8EBfia6prAXFJG8UFIwlgmZNY8jSlISiYUOcs2Wz2JwlzV4zFBHD8BCixLT+pljElXXk93f2W0KjWPcM+ipngXRhZchjhNmyZoLXPTjljInqabGakqSEp7lU9W4O5G4Hxkkq3lLhns6fshv+Am9BNCqe72bjILtSrbygpFAvrAYr1ppAxFmRmZ3pmoQLsmqTAj3qFnZvK92EsAURfC3LqVoQKkDKQzxNcLnjDcbKFtdZayNSGkfbtncY5IMi8Q4qnkHlChpcljEV5CFDYZleSu/vwUksFrKjGZCPKM8qf5zTFZGdTUyERxXZ52ryq/GBLXjgqehAJ+io3IHpTGeFNTBh+Z+GNadJMmUJ45vqcI7wGPvSngvOnkktB5EBgN4J8QZju3h9l3wRAMu0hk7RGlqeusGFTt11N1bGkUvOOGieUWyzG7vETu8RHWGnI4savM9P64gjTCW32gQeB7gfBOaUxz4Z4UHblB95j3A4PMcG1BUpzPCjw3683ZC6Qs+NMEXRGtmm5WTY0hV4LWFMd+HtbTjW4bkZpHSFXkvQchHH8AO7inXeLWFPB71V0QKebVwuhzH26bkcyFinp/u/2KURdA240/GKfXxOBSzW/3/0WiKWS5re+5uRdd4uBzn26Tkd5djH5+a3mc7gM6OW+yKlebwo33wfo3xLsUcuoVEqn0NZnMgFcFKyoCFKvquMBcW4rD7hJKev6m5DX6YzRlOxeR1/0vNnZVuFYHl1kaVses5Soe61AF+n1VhaLnG8WwuoZ57WouV/ye2tlLoY3snEME/1v8gScdwBIbbgTWG+QAsf7GnRMi+Cc0qhJ1yNOWdFisvVYUONcRGziKUouWMsU2SeiBBrhaaE2JSIrKj4U1b/5qvUX9VY+Txb1RNrlTjINmcFD8kxZ6rKCcQjcmwN0ysAwY0LXaZUnCRI0BfSGMbXgwcG+HJk2v9Slm582IYWh096h86GH1dv4Kh63lnVA3Xttkq+Ub3tV8ND3xmPfZv8uLL6M+r/pR2fSVqZ3N2m3OTV7qTC638=&lt;/diagram&gt;&lt;/mxfile&gt;&quot;}"></div>

