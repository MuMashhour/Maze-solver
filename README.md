# Maze Generator and Solver in C++ using Randomized DFS, Wall Follower, and A* Algorithm
This program generates mazes using Randomized Depth-First Search algorithm and solves them using two different algorithms: Wall Follower and A* Algorithm. The maze and solving process are visualized using GLFW OpenGL.

### Maze Generation
The maze is generated using Randomized Depth-First Search algorithm, which starts at a random cell and recursively explores all unvisited neighbors, marking them as visited and adding them to a stack. When no unvisited neighbours are found, the algorithm returns to the last cell with unvisited neighbours and continues exploring until all cells have been visited. Unfortunately, due to the recursive nature of Randomized DFS, mazes larger than 95x95 can cause stack overflow.

<img src="https://user-images.githubusercontent.com/98267072/228526695-0124b31d-8c05-4919-ab10-6a4faa2d1763.gif" width="200px"/>

### Maze Solving

The program uses two algorithms to solve the generated mazes:

#### Wall Follower
The Wall Follower algorithm follows the left or right wall of the maze until it reaches the exit. It always keeps the wall on its right (or left) side. This algorithm guarantees that it will find the exit if it exists and the maze is simply connected.

<img src="https://user-images.githubusercontent.com/98267072/228530141-36a1dc65-603f-4517-bcca-60c39e977158.gif" width="200px"/>

#### A* Algorithm
The A* Algorithm is a pathfinding algorithm that finds the shortest path between two points in a graph. In this program, the maze is represented as a graph, with each cell being a node and its neighboring cells being its edges. The A* Algorithm uses a heuristic function to estimate the distance from the current node to the goal node (in our case: manhattan distance) and chooses the node with the lowest total cost to explore next.

<img src="https://user-images.githubusercontent.com/98267072/228533028-5b33d824-65d4-487a-8be1-21b8d02ccc14.gif" width="200px"/>

### Visualization
The generated maze and the solving process are visualized using GLFW OpenGL. The solving process is visualized by highlighting the visited cells and the current path being explored. Blue is for the Wall Following Algorithm and Yellow is for the A* Algorithm. Multithreading is used to draw the maze while it is being solved.

### Usage
To use this program, simply clone the repository and compile the main.cpp file using your preferred C++ compiler. The program requires GLFW and OpenGL libraries to be installed. 
