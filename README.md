👑 8-Queens Problem Solver

This C++ program provides a solution to the classic N-Queens puzzle, specifically configured for the 8-Queens problem. It utilizes a Breadth-First Search (BFS) algorithm to find all possible configurations where eight queens can be placed on an 8x8 chessboard such that no two queens threaten each other.

✨ Features

Finds all 92 unique solutions to the 8-Queens problem.

Employs a Breadth-First Search (BFS) algorithm for state space exploration.

Counts and displays the total number of solutions found.

Counts and displays the total number of non-attacking states explored during the search.

Optionally prints all valid chessboard configurations upon user request.

⚙️ How It Works

The program implements a Breadth-First Search (BFS) to explore the state space of possible queen placements.

State Representation: Each state is represented as an 8x8 chessboard using std::vector<std::string>, where . denotes an empty square and Q denotes a queen.

search_tree Function (BFS Core):

Initializes with an empty board state and the first row (r=0).

Uses a std::queue (open for states, row for corresponding current rows) to manage the states to be explored.

In each step, it dequeues a state and its current row (r).

It checks if the dequeued state is a goal state (all 8 queens placed). If so, it increments the solution count and stores the board.

If not a goal state, it calls succ to generate all valid successor states for the next row (r+1).

For each valid successor, it enqueues the new state and the incremented row (r+1).

The BFS continues until the queue is empty, meaning all reachable states have been explored.

safe Function:

Determines if placing a queen at a specific (row, col) position on the board is safe.

It checks three conditions:

No other queen in the same column.

No other queen in the upper-left diagonal.

No other queen in the upper-right diagonal.

Since queens are placed row by row, there's no need to check the current or lower rows, or horizontal conflicts (as only one queen is placed per row).

succ Function:

Generates all valid successor states from a given state and the current row (r) where a queen is to be placed.

It iterates through each column i in the current row r.

If safe(r, i, state) returns true, it creates a new board state with a queen at (r, i), adds it to the list of non_attacking_states, and includes it in the list of succ_states to be returned.

goal Function:

A simple check to see if all N queens have been successfully placed. This occurs when the current row r reaches N (i.e., r == N).

🚀 Getting Started
Prerequisites

A C++ compiler (e.g., g++, Clang)

Compilation

Save the provided code as 8_queens_solver.cpp.

Open a terminal or command prompt.

Navigate to the directory where you saved the file.

Compile the program using your C++ compiler:

Generated bash
g++ 8_queens_solver.cpp -o 8_queens_solver

Execution

Run the compiled executable:

Generated bash
./8_queens_solver
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
Bash
IGNORE_WHEN_COPYING_END
🎮 Usage

After running the program, you will be prompted to enter a number:

Generated code
_
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
IGNORE_WHEN_COPYING_END

Enter 1: To view all the 92 distinct chessboard configurations that are valid solutions. Each solution will be printed sequentially, followed by an empty line.

Enter any other number (e.g., 0, 2, etc.): The program will skip printing the individual boards but will still display the total count of solutions and non-attacking states.

Finally, the program will output the total number of solutions and the total number of non-attacking states explored:

Generated code
no. of solutions :92
no. of non-attacking states :[some_number_usually_around_1854]
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
IGNORE_WHEN_COPYING_END
Example Output (entering 1):
Generated code
. Q . . . . . .
. . . . Q . . .
. . . . . . . Q
. . . . . Q . .
. . Q . . . . .
Q . . . . . . .
. . . Q . . . .
. . . . . . Q .

. . Q . . . . .
. . . . . . Q .
. . . . Q . . .
. . . . . . . Q
Q . . . . . . .
. . . Q . . . .
. Q . . . . . .
. . . . . Q . .

(many more boards will be printed)

no. of solutions :92
no. of non-attacking states :1854
IGNORE_WHEN_COPYING_START
content_copy
download
Use code with caution.
IGNORE_WHEN_COPYING_END
📖 Dependencies

Standard C++ Library (<bits/stdc++.h> for convenience, but specifically queue, string, vector, iostream are used).
