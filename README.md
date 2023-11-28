# Forest Fire Propagation Model

This Python script models the propagation of a forest fire using a simple cellular automaton. It consists of two classes, `Tree` and `Forest`, that simulate the state of trees in a forest and the forest grid itself.

## Tree Class

The `Tree` class represents an individual tree in the forest. It has the following attributes and methods:
- `__init__(self)`: Constructor method to initialize a tree's state (0: Empty, 1: Healthy, 2: Burning, 3: Burned).
- `getState(self)`: Getter method to retrieve the tree's state.
- `setState(self, value)`: Setter method to change the tree's state.
- `__str__(self)`: Returns a symbol ('.', 'T', 'B', 'F') for displaying a tree on the console based on its state.
- `is_neighbour_burning_tree(self, is_burning)`: Updates the tree's state based on the presence of a burning tree in the neighborhood.

## Forest Class

The `Forest` class represents the entire forest grid. It has the following attributes and methods:
- `__init__(self, rows, cols, probability=None)`: Constructor method to initialize the forest grid.
- `rows` and `cols`: Properties to get the number of rows and columns in the grid.
- `grid`: Property to get the 2D grid of trees.
- `getCell(self, i, j)`: Method to retrieve a specific tree in the grid.
- `__str__(self)`: Returns a string representation of the forest grid.
- `set_cell_on_fire(self, i, j)`: Sets a specific tree on fire in the grid.
- `is_cell_neighbour_burning_tree(self, i, j)`: Checks if any neighboring tree is burning.
- `propagation_update(self, i, j)`: Updates the grid based on the rules of propagation.
- `tree_proportion(self)`: Calculates and returns the proportion of healthy trees in the forest.
- `generation_run(self, n_generation)`: Simulates the forest fire propagation for a specified number of generations.

## Usage

You can create an instance of the `Forest` class and use it to model the propagation of a forest fire. The script includes an example of setting healthy tree positions, starting a fire, and running one generation.

Feel free to modify the parameters and run multiple generations to see how the forest fire spreads.
