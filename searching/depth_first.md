## Depth First Search
To traverse the graph in a depthwise motion:
 
![screenshot 2019-01-28 at 16 10 31](https://user-images.githubusercontent.com/8224798/51838877-a2db9e80-2318-11e9-8b69-917ea03da7ea.png)

```
def dfs(graph, start):
    visited, stack = set(), [start]
    while stack:
        vertex = stack.pop()
        if vertex not in visited:
            visited.add(vertex)
            stack.extend(graph[vertex] - visited)
    return visited

dfs(graph, 'A')
```
Application:
1. Detecting a cycle ina graph
2. Finding
3. Topological sorting
