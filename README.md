# AI-concepts
UCSD CSE 150B artificial intelligence
- all projects is coded in Python

## Project 1
[Watch the video](https://youtu.be/kFo-3NDZInM)
1. **DFS (Depth-First Search)**:
   Imagine exploring a maze by delving as far as possible down a path before retracing your steps. You keep choosing unexplored paths until you hit a dead end, and then you backtrack a bit to try another path. It's like descending deep into a tree and then coming back up.

   Uses Stack

2. **BFS (Breadth-First Search)**:
   Visualize BFS as if you're navigating a maze one level at a time. You start at the entrance and explore all the nearby paths before moving to those farther away. It's like systematically checking all the options at the current level before moving on to the next level.

     Uses Queue
  
3. **Uniform Cost Search**:
   Think of searching for the cheapest way to travel between places. Uniform Cost Search is akin to always selecting the path that has the lowest cost. You're meticulous in your selection, choosing the path with the smallest overall cost, making sure you spend your resources wisely.

     Uses Priority Queue
  
4. **A\* Search using Manhattan Distance as the heuristic**:
   Envision A\* Search as planning a journey with the assistance of a knowledgeable guide. The guide (heuristic) informs you how far you are from your destination in a straight line. So, you sum up your distance covered so far and the estimated remaining distance. It's like combining your current progress with the distance left to travel, ensuring you're on the right path to successfully reach your goal.

     Uses Priority Queue + heuristic

## Project 2
[Watch the video](https://youtu.be/ZeCWr1Sipyk)

**Using expectimax tree**

A depth-3 game tree means the tree should have the following levels: 

- root: player
- level 1: computer 
- level 2: player
- level 3: terminal with payoff (note that we say "terminal" to mean the leaf nodes in the shallow game tree, not the termination of the game itself)

This tree represents all the game states of a player-computer-player sequence (the player makes a move, the computer places a tile, and then the player makes another move, and then evaluate the score) from the current state. Compute the expectimax values of all the nodes in the game tree, and return the optimal move for the player. In the starter code, the AI just returns a random move.

The payoff is the sum of all numbers. 

## Project 3
[Watch the video](https://youtu.be/gDzzhPBbXKk)

### Policy Evaluation: 
Learning Values of a policy: Given a policy, evaluate how good (or bad) it is.

The policy to evaluate: Hit if sum of cards is below 14, and Stand otherwise

#### - Monte Carlo Policy Evaluation 

**Basic Idea:** At each iteration, simulate one episode (i.e. sequence). Update the average reward-to-go for each state in the episode

Reward-to-go Algorithm:

![G(s_x) = \sum_{i=k}^{T} \gamma^{i-k} R(s_i)](https://latex.codecogs.com/svg.image?G(s_x)=\sum_{i=k}^{T}\gamma^{i-k}R(s_i))

The MC value for each state is simply the average of all rewards-to-go you have calculated for the state.

#### - Temporal-Difference Policy Evaluation

**Basic Idea:** Instead waiting for an episode to terminate, take the advantage of Bellman Equation and updating the running average

update rule:

![V^π(s_0) = V^π(s_0) + \alpha (R(s_0) + \gamma V^π(s_1) - V^π(s_0))](https://latex.codecogs.com/svg.image?V^\pi(s_0)=V^\pi(s_0)&plus;\alpha(R(s_0)&plus;\gamma&space;V^\pi(s_1)-V^\pi(s_0)))


### Policy Improvement: 
Learning Policy: Improve or optimize a given policy

#### - Q-Learning

Implement the Q-learning algorithm. Use epsilon=0.4 in the epsilon-strategy in your final submission, but you are encouraged to check the behavior difference for various choices of epsilon. After learning, AutoPlay will follow the Q-learning values to make decisions. 

Basic Idea: pick an action based on epsilon greedy, and update Q
value for the original state and picked action

Epsilon greedy: with probability=ε, the action is picked at random;
other, pick action greedily (0 < ε <= 1)

update formula:
![Q(s,a) = Q(s,a) + \alpha (R(s) + \gamma \cdot \max_{\dot{a}} Q(\dot{s},\dot{a}) - Q(s,a))](https://latex.codecogs.com/svg.image?Q(s,a)=Q(s,a)&plus;\alpha(R(s)&plus;\gamma*(max)_{\dot{a}}Q(\dot{s},\dot{a})-Q(s,a)))

At convergence,
● Optimal policy: follows the best action - argmax_a Q*(s,a)

● Value: V(s) = max_a Q*(s,a)
