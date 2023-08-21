# AI-concepts
UCSD CSE 150B artificial intelligence
- all projects is coded in Python

## Project 1
[Watch the video](https://youtu.be/kFo-3NDZInM)
1. **DFS (Depth-First Search)**:
   Imagine exploring a maze by delving as far as possible down a path before retracing your steps. You keep choosing unexplored paths until you hit a dead end, and then you backtrack a bit to try another path. It's like descending deep into a tree and then coming back up.

   Uses Stack

3. **BFS (Breadth-First Search)**:
   Visualize BFS as if you're navigating a maze one level at a time. You start at the entrance and explore all the nearby paths before moving to those farther away. It's like systematically checking all the options at the current level before moving on to the next level.

  Uses Queue
  
5. **Uniform Cost Search**:
   Think of searching for the cheapest way to travel between places. Uniform Cost Search is akin to always selecting the path that has the lowest cost. You're meticulous in your selection, choosing the path with the smallest overall cost, making sure you spend your resources wisely.

  Uses Priority Queue
  
5. **A\* Search using Manhattan Distance as the heuristic**:
   Envision A\* Search as planning a journey with the assistance of a knowledgeable guide. The guide (heuristic) informs you how far you are from your destination in a straight line. So, you sum up your distance covered so far and the estimated remaining distance. It's like combining your current progress with the distance left to travel, ensuring you're on the right path to successfully reach your goal.

  Uses Priority Queue + heuristic

