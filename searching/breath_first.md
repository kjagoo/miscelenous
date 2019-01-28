## Breadth First Search
Traversing a graph or tree one layer of nodes at a time from the start node. 

- ![screenshot 2019-01-28 at 16 21 23](https://user-images.githubusercontent.com/8224798/51838935-c9013e80-2318-11e9-8faa-68cc1e30033a.png)

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
