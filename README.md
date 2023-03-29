# Maze Generator and Solver in C++ using Randomized DFS, Wall Follower, and A* Algorithm
This program generates mazes using Randomized Depth-First Search algorithm and solves them using two different algorithms: Wall Follower and A* Algorithm. The maze and solving process are visualized using GLFW OpenGL.

### Maze Generation
The maze is generated using Randomized Depth-First Search algorithm, which starts at a random cell and recursively explores all unvisited neighbors, marking them as visited and adding them to a stack. When no unvisited neighbours are found, the algorithm returns to the last cell with unvisited neighbours and continues exploring until all cells have been visited. Unfortunately, due to the recursive nature of Randomized DFS, mazes larger than 95x95 can cause stack overflow.

<video width="640" height="640" controls>
  <source src="https://user-images.githubusercontent.com/98267072/228512509-1b5c0617-9fd9-4efd-bc52-2f80fbc05f11.mp4" type="video/mp4">
</video>

### Maze Solving

The program uses two algorithms to solve the generated mazes:

#### Wall Follower
The Wall Follower algorithm follows the left or right wall of the maze until it reaches the exit. It always keeps the wall on its right (or left) side. This algorithm guarantees that it will find the exit if it exists and the maze is simply connected.

#### A* Algorithm
The A* Algorithm is a pathfinding algorithm that finds the shortest path between two points in a graph. In this program, the maze is represented as a graph, with each cell being a node and its neighboring cells being its edges. The A* Algorithm uses a heuristic function to estimate the distance from the current node to the goal node (in our case: manhattan distance) and chooses the node with the lowest total cost to explore next.

### Visualization
The generated maze and the solving process are visualized using GLFW OpenGL. The solving process is visualized by highlighting the visited cells and the current path being explored. Blue is for the Wall Following Algorithm and Yellow is for the A* Algorithm. Multithreading is used to draw the maze while it is being solved.

### Usage
To use this program, simply clone the repository and compile the main.cpp file using your preferred C++ compiler. The program requires GLFW and OpenGL libraries to be installed. 
