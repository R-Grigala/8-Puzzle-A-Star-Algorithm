# 8-Puzzle-A-Star-Algorithm
8 Puzzle Python Implementation Using A* Algorithm

# Rules for solving the puzzle.
Instead of moving the tiles in the empty space, we can visualize moving the empty space in place of the tile, basically swapping the tile with the empty space. The empty space can only move in four directions viz.,

1. Up
2. Down
3. Right or
4. Left

The empty space cannot move diagonally and can take only one step at a time (i.e. move the empty space one position at a time)

# A* Algorithm

A* is a computer algorithm that is widely used in pathfinding and graph traversal, 
the process of plotting an efficiently traversable path between multiple points, called nodes. 
Noted for its performance and accuracy, it enjoys widespread use.
The key feature of the A* algorithm is that it keeps a track of each visited node 
which helps in ignoring the nodes that are already visited, saving a huge amount of time. 
It also has a list that holds all the nodes that are left to be explored and it chooses the most optimal node from this list, 
thus saving time not exploring unnecessary or less optimal nodes.

# Comments and Analysis

1. The code implements the A* algorithm to solve a puzzle. The puzzle is represented as an n x n matrix, where each element can be a number or the underscore character _ representing the empty space.
2. The Node class represents a node in the search tree. It has attributes for the node's data (the puzzle state), level (the depth of the node in the tree), and fval (the calculated f-value for the node).
3. The generate_child method of the Node class generates child nodes by moving the empty space in four directions: up, down, left, and right. It returns a list of child nodes.
4. The shuffle method of the Node class moves the empty space in a given direction and returns the modified puzzle state. If the move is invalid (out of bounds), it returns None.
5. The copy method of the Node class creates a deep copy of a puzzle state matrix.
6. The find method of the Node class finds the position of the empty space in a puzzle state matrix.
7. The Puzzle class represents the puzzle-solving process. It has attributes for the puzzle size, open list (nodes to be explored), and closed list (nodes already explored).
8. The accept method of the Puzzle class accepts the start and goal puzzle states from the user.
9. The f method of the Puzzle class calculates the heuristic value f(x) for a given node using the heuristic function h(x) + g(x). Here, h(x) calculates the difference between the given puzzles, and g(x) is the level (depth) of the node.
10. The h method of the Puzzle class calculates the number of misplaced tiles (excluding the empty space) between two puzzle states.
11. The process method of the Puzzle class performs the A* algorithm. It initializes the start node, calculates its f-value, and adds it to the open list. Then, it enters a loop where it selects the node with the lowest f-value from the open list, generates its child nodes, calculates their f-values, and adds them to the open list. The current node is moved to the closed list. The loop continues until the goal node is reached (the difference between the current and goal nodes is 0).
12. The open list is sorted based on f-value in each iteration, ensuring that the node with the lowest f-value is selected next


# Time Complexity Analysis:

The time complexity of the A* algorithm depends on the size of the puzzle (n) and the number of nodes expanded.
In the worst case, the algorithm explores all possible states until it finds the goal state.
Assuming there are k possible states reachable from each node, the worst-case time complexity can be approximated as O(k^d), 
where d is the depth of the goal state from the start state.
In this case, k is at most 4 (four possible directions to move the empty space), and d is unknown beforehand.

# Space Complexity Analysis:

The space complexity of the A* algorithm depends on the maximum number of nodes stored in the open and closed lists during the search.
In the worst case, where all nodes need to be explored, the maximum number of nodes in the open list is proportional to the number of expanded nodes.
Therefore, the worst-case space complexity can be approximated as O(k^d), similar to the time complexity.

Note: The actual time and space complexity may vary depending on the specific puzzle instance and the efficiency of the heuristic function.

Overall, the code is well-structured and implements the A* algorithm for solving puzzles.
It would be helpful to have additional information about the specific puzzle being solved to provide more accurate time and space complexity analysis.