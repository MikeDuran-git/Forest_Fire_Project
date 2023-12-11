# Forest Fire Simulation

This project is a simulation of the spread of a forest fire. It implements a grid model where each cell represents a tree that can be healthy, on fire, or burnt.

## Description
The project contains two main classes, Tree and Forest, along with a subclass ToricForest for simulating a toroidal (borderless) forest. Here's an overview of the main functionalities:

## Tree Class
The Tree class represents an individual tree in the forest. It includes the following attributes and methods:

- `__init__(self)`: Constructor method to initialize a tree's state (0: Empty, 1: Healthy, 2: Burning, 3: Burned).
getState(self): A property method to retrieve the tree's state.
setState(self, value): Method to change the tree's state.
- `__str__(self)`: Returns a symbol ('.', 'T', 'F', 'B') representing the tree's state for console display.
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


## ToricForestGui Class
The `ToricForestGui` class extends the `ToricForest` class to provide a graphical user interface for the simulation. It uses the Tkinter library to create a visual grid of the forest, allowing users to interactively start the fire and observe its spread. Key functionalities include:
- Interactive grid creation where each cell represents a tree with its state visually differentiated by color.
- Ability to start the fire by clicking on a tree in the grid.
- Real-time visual updates of the forest fire spread.
- Options to restart the simulation and close the application through GUI buttons.

It has the following methods:
- `__init__(self, rows, cols, probability=None)`: Constructor method that initializes the ToricForest with given rows, columns, and probability, and sets up the Tkinter window and essential GUI components.
- `run(self, n)`: Prepares and displays the forest grid in the GUI. It takes `n` as the number of generations for the simulation. Each cell in the grid represents a tree and is visualized as a label in Tkinter.
- `on_label_click(self, event, c, r, n)`: An event handler triggered when a tree (label) in the grid is clicked. It starts the fire from the clicked tree if it is healthy and begins the simulation for `n` generations.
- `update_visual_grid(self)`: Updates the colors of the labels in the GUI to reflect the current state of each tree in the forest, providing a real-time visualization of the fire spread.
- `widget_exists(self, widget)`: Utility method to check if a Tkinter widget exists. It helps in safely managing GUI components.
- `reset_game(self)`: Resets the game to its initial state. It clears the current grid and resets the forest state, then redraws the initial GUI layout for a new simulation.
- `end_the_game(self)`: Closes the Tkinter window and ends the application. This provides a way to exit the simulation.
- `generation_run(self, n_generation, current_generation=0)`: Handles the logic for running each generation of the simulation. It updates the forest state and the GUI, checks for the end of the simulation, and schedules the next generation update.

## Usage

Create an instance of the `Forest` or `ToricForest` class for a console-based simulation, or use the `ToricForestGui` class for a graphical representation. Set initial tree states, ignite specific trees, and run the simulation for a desired number of generations to observe the dynamics of forest fire spread.

Feel free to modify the parameters and run multiple generations to observe the dynamics of forest fire spread.