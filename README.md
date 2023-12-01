# Forest Fire Simulation

This project is a simulation of the spread of a forest fire. It implements a grid model where each cell represents a tree that can be healthy, on fire, or burnt.

## Description
The project contains two main classes, Tree and Forest, along with a subclass ToricForest for simulating a toroidal (borderless) forest. Here's an overview of the main functionalities:

## Tree Class
The Tree class represents an individual tree in the forest. It includes the following attributes and methods:

- `__init__(self)`: Constructor method to initialize a tree's state (0: Empty, 1: Healthy, 2: Burning, 3: Burned).
getState(self): A property method to retrieve the tree's state.
setState(self, value): Method to change the tree's state.
- `__str__(self)`: Returns a symbol ('.', 'T', 'B', 'F') representing the tree's state for console display.
is_neighbour_burning_tree(self, is_burning): Updates the tree's state based on the presence of a burning tree in the neighborhood.

## Forest Class

The `Forest` class simulates the forest grid. It includes the following attributes and methods:

- `__init__(self, rows, cols, probability=None)`: Constructor method to initialize the forest grid.
- `rows` , `cols`, `probability`: Property methods to access the number of rows, columns, and the probability of having a healthy tree.
- `grid`: Property to get the 2D grid of trees.
- `getCell(self, i, j)`:  Method to retrieve a specific tree in the grid.
- `__str__(self)`:  Returns a string representation of the forest grid.
- `set_cell_on_fire(self, i, j)`:  Sets a specific tree on fire in the grid.
- `is_cell_neighbour_burning_tree(self, i, j)`: Checks if any neighboring tree is burning.
- `propagation_update(self, i, j)`: Updates the grid based on the rules of propagation.
- `tree_proportion(self)`: Calculates and returns the proportion of healthy trees in the forest.
- `generation_run(self, n_generation)`: Simulates the forest fire propagation for a specified number of generations.


## ToricForest Class
The `ToricForest` subclass extends the `Forest` class to simulate a forest with toroidal (borderless) edges. It overrides the `is_cell_neighbour_burning_tree(self, i, j)` method to account for the toroidal nature of the grid.

## Usage

You can create an instance of the `Forest` or `ToricForest` class and use it to model the propagation of a forest fire. The script includes functionalities for setting initial tree states, igniting specific trees, and running the simulation for a specified number of generations.

Feel free to modify the parameters and run multiple generations to observe the dynamics of forest fire spread.
