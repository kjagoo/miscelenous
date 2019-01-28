## Breadth First Search
Traversing a graph or tree one layer of nodes at a time from the start node. 

```
def breadth_first_search_1(graph, start):
    # print out what we find
    frontier = Queue()
    frontier.put(start)
    visited = {}
    visited[start] = True
    
    while not frontier.empty():
        current = frontier.get()
        print("Visiting %r" % current)
        for next in graph.neighbors(current):
            if next not in visited:
                frontier.put(next)
                visited[next] = True

breadth_first_search_1(example_graph, 'A')
```

Application:
1. Peer to Peer networks
2. Webcrawlers
3. Social Networking
4. GPS Navigation
5. Broadcasting