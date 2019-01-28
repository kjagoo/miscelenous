## Depth First Search
To traverse the graph in a depthwise motion:
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