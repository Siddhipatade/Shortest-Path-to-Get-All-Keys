# Shortest Path to Get All Keys

## Problem Description
You are given an `m x n` grid `grid` where:
- `'.'` is an empty cell.
- `'#'` is a wall.
- `'@'` is the starting point.
- Lowercase letters represent keys.
- Uppercase letters represent locks.

You start at the starting point and one move consists of walking one space in one of the four cardinal directions. You cannot walk outside the grid or walk into a wall.

For some `1 <= k <= 6`, there is exactly one lowercase and one uppercase letter of the first `k` letters of the English alphabet in the grid. This means that there is exactly one key for each lock, and one lock for each key, and the letters used to represent the keys and locks were chosen in the same order as the English alphabet.

The goal is to find the lowest number of moves required to acquire all keys. If it is impossible to acquire all keys, return `-1`.

## Solution Approach
To solve this problem, we can use a Breadth-First Search (BFS) algorithm. The general idea is to explore the grid while keeping track of the keys collected and the locks encountered. We can use a queue to perform the BFS traversal.

The steps for the BFS algorithm are as follows:
1. Identify the starting point, collect all the keys, and keep track of the locks.
2. Initialize a queue and a map to store visited cells.
3. Enqueue the starting point into the queue along with the key state and the distance traveled.
4. While the queue is not empty, dequeue a cell and its corresponding key state and distance.
5. Explore all four adjacent cells (up, down, left, right):
   - If the cell is a key, check if it has been collected before. If not, collect the key, update the key state, and check if all keys are collected.
   - If the cell is a lock and the corresponding key is not collected, continue to the next adjacent cell.
   - If the cell is reachable and has not been visited before with the same key state, mark it as visited and enqueue it into the queue along with the updated key state and distance.
6. If all keys are collected, return the distance traveled. Otherwise, return `-1` to indicate it is impossible to acquire all keys.

## Example
Let's consider the following grid as an example:
```
4 7
#######
#.@.b.#
#A#####
#######
```

- The grid has 4 rows and 7 columns.
- The starting point is represented by `'@'`.
- There is one key `'b'` and one lock `'A'`.
- The wall is represented by `'#'`.

The shortest path to acquire all keys in this example is 6.

## Running the Code
To run the code, provide the input in the console as follows:
1. Enter the number of rows.
2. Enter each row of the grid.
3. The code will display the shortest path to acquire all keys as the output.

#### Example 1
![image](https://github.com/Siddhipatade/Shortest-Path-to-Get-All-Keys/assets/91780318/f60e3cc0-98e7-4318-beb1-22703db06542)

```
Enter the number of rows: 3
Enter the grid rows:
@.a..
###.#
b.A.B
Shortest Path to Acquire All Keys: 8
```
#### Example 2
```
Enter the number of rows: 3
Enter the grid rows:

#@.##
#####A
Shortest Path to Acquire All Keys: -1
```

---

This is just a basic example to illustrate the problem and solution approach. The code can be extended and optimized further based on specific requirements or additional constraints.

Feel free to modify the code or refer to the comments within the code for a better understanding of the implementation details.
