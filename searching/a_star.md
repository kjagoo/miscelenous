## A* Search

- The A* search algorithm is an extension of Dijkstra's algorithm useful for finding the lowest cost path between two nodes (aka vertices) of a graph. 

![screenshot 2019-01-28 at 16 23 02](https://user-images.githubusercontent.com/8224798/51839009-02d24500-2319-11e9-9bf2-821f627b97f4.png)

```
from __future__ import print_function
import matplotlib.pyplot as plt
 
def heuristic(a, b):
    (x1, y1) = a
    (x2, y2) = b
    return abs(x1 - x2) + abs(y1 - y2)

def a_star_search(graph, start, goal):
    frontier = PriorityQueue()
    frontier.put(start, 0)
    came_from = {}
    cost_so_far = {}
    came_from[start] = None
    cost_so_far[start] = 0
    
    while not frontier.empty():
        current = frontier.get()
        
        if current == goal:
            break
        
        for next in graph.neighbors(current):
            new_cost = cost_so_far[current] + graph.cost(current, next)
            if next not in cost_so_far or new_cost < cost_so_far[next]:
                cost_so_far[next] = new_cost
                priority = new_cost + heuristic(goal, next)
                frontier.put(next, priority)
                came_from[next] = current
    
    return came_from, cost_so_far
```

Usage:
1. Finding the shortest path
2. Finding length of path.
