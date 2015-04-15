# DFS and BFS

[DFS](http://zh.wikipedia.org/zh-tw/%E6%B7%B1%E5%BA%A6%E4%BC%98%E5%85%88%E6%90%9C%E7%B4%A2) 和 [BFS](http://zh.wikipedia.org/zh-tw/%E5%B9%BF%E5%BA%A6%E4%BC%98%E5%85%88%E6%90%9C%E7%B4%A2) 在資料結構裡有教，是很基礎的演算法。

在 [Edd Mann 的網誌](http://eddmann.com/posts/depth-first-search-and-breadth-first-search-in-python/)上看到 Python 的實作，由其中學到 `yield from` 的用法。下面利用 `yield from` 的特性，將該網誌中提到的實作改寫成 generator 的型式。同步放在 Gist 上：[DFS](https://gist.github.com/changyuheng/08ffb779d83679393926)、[BFS](https://gist.github.com/changyuheng/97d320206af9a0018d7d)。

## DFS

```python
def dfs(graph, start, visited=None):
    if visited is None:
        visited = set()
    if start in visited:
        return
    yield start
    visited.add(start)
    for vertex in graph[start] - visited:
        yield from dfs(graph, vertex, visited=visited)


def dfs_paths(graph, start, goal, path=None):
    if path is None:
        path = [start]
    if start == goal:
        yield path
    for vertex in graph[start] - set(path):
        yield from dfs_paths(graph, vertex, goal, path=path + [vertex])


graph = {
    'A': set(['B', 'C']),
    'B': set(['A', 'D', 'E']),
    'C': set(['A', 'F']),
    'D': set(['B']),
    'E': set(['B', 'F']),
    'F': set(['C', 'E']),
}

print(repr([vertex for vertex in dfs(graph, 'A')]))
print(repr([path for path in dfs_paths(graph, 'A', 'F')]))
```

## BFS

```python
def bfs(graph, queue, visited=None):
    if visited is None:
        visited = set()
    if not queue:
        return
    start = queue.pop(0)
    yield start
    visited.add(start)
    queue += [vertex for vertex in graph[start] - set(queue) - visited]
    yield from bfs(graph, queue, visited=visited)


def bfs_paths(graph, queue, goal):
    if not queue:
        return
    (start, path) = queue.pop(0)
    if start == goal:
        yield path
    queue += [(vertex, path + [vertex]) for vertex in graph[start] - set(path)]
    yield from bfs_paths(graph, queue, goal)


graph = {
    'A': set(['B', 'C']),
    'B': set(['A', 'D', 'E']),
    'C': set(['A', 'F']),
    'D': set(['B']),
    'E': set(['B', 'F']),
    'F': set(['C', 'E']),
}

print(repr([vertex for vertex in bfs(graph, ['A'])]))
print(repr([path for path in bfs_paths(graph, [('A', ['A'])], 'F')]))
```