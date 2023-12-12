[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=12742740&assignment_repo_type=AssignmentRepo)
# Dijkstra's Algorithm

Recall the pseudocode for Dijkstra's algorithm:
- initialize the dist to each vertex to $\infty$, source to 0
- while there are unmarked vertices left in the graph
    - select the unmarked vertex $v$ with the lowest dist
    - mark $v$ with distance dist
    - for each edge $(v,w)$
        - dist($w$) = min $\left(\textrm{dist}(w), \textrm{dist}(v) + \textrm{weight of }(v, w)\right)$

Implement Dijkstra's algorithm. Start with the template I provided in `code.js`
and test your new function. I have not provided any test code, but you can base
yours on test code from other exercises.

The choice of data structures is up to you -- your implementation does not have
to be the most efficient one!

## Runtime Analysis

What is the big $\Theta$ complexity of your implementation? Add your
answer, including your reasoning, to this markdown file.

## Answer

The algorithm uses a while loop to iterate through all vertices in the graph, and for each vertex, it performs a linear search to find the vertex with the minimum distance from the source node. In the worst case, this linear search involves checking distances for all vertices in each iteration of the while loop. In this case, the while loop runs for each vertex in the graph ($V$ times), and for each vertex, it checks distances for all vertices again ($V$ times). So a total of $V * V = V^2$ comparisons. In the best case, if the minimum distance is such that the vertex is always found quickly, the while loop still iterates through all vertices once ($V$ times), and for each vertex it checks distances for all vertices ($V$ times), resulting in the same time of $V^2$ comparisons. The outer while loop and inner for loop are the main contributors to this complexity. So the time complexity for both bounds worse case and best case is $O(V^2)$. 

I read that Dijkstra's algorithm can be optimized to $O(V log V)$ using a priorty queue or a min-heap. This might be something I look into for the wildcard assignment. 
