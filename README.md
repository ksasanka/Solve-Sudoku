# Solve-Sudoku
This repository has code which uses AI to solve Sudoku

Welcome to the Solve-Sudoku wiki! Note: Some of the material below is from AI course on Udaicty and from "Artificial Intelligence: A Modern Approach by Stuart Russell" The code uses two of the basic components of AI search - Constraint propagation and Depth first search.

Basic blocks used in the code**

Boxes: The individual squares at the intersection of rows and columns will be called boxes. These boxes will have labels 'A1', 'A2', ..., 'I9 Units: The complete rows, columns, and 3x3 squares, will be called units. Thus, each unit is a set of 9 boxes, and there are 27 units in total Peers: For a particular box (such as 'A1'), its peers will be all other boxes that belong to a common unit (namely, those that belong to the same row, column, or 3x3 square)

Note: The above definitions are from the Artificial Intelligence course on Udacity.

Constraint propagation**

Constraint Propagation is all about using local constraints in a space to reduce the search space. As we enforce each constraint, we see how it introduces new constraints for other parts of the board that can help us further reduce the number of possibilities. Specific constraints for Sudoku (in the code) are:

Elimination: Each empty box has a possible values from 1-9. We start with this scenario and eliminate values based on values already confirmed for the peer boxes
Only choice: If there is only one box in a unit which would allow a certain digit, then that box must be assigned that digit
Depth First search**

Depth-first Search (DFS) is an algorithm for searching a graph or tree data structure. The algorithm starts at the root (top) node of a tree and goes as far as it can down a given branch (path), and then performs similar operation on adjacent node. The algorithm does this on various nodes, until it finds s viable solution.

Code structure:

utils.py has the basic utility functions defined where functions are in place to set up the board (create boxes, units, and peers) sudoku.py takes the sudoku as a string input (e.g '2.............62....1....7...6..8...3...9...7...6..4...4....8....52.............3') and solves the sudoku and displays the output. The code can solve only diagonal sudoku's. If it were to solve non-diagonal sudoku's, comment out the code from line 11-14
