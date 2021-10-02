- Give [[Kruskal's Algorithm]] a significant improvement in runtime, which is used to solve [[The Minimum Spanning Tree Problem]]
- Implementing [[Kruskal's Algorithm]] without union-find.
  collapsed:: true
	- What would be the first step in the implementation of Kruskal's Algorithm?
	  collapsed:: true
		- Sort the edges.
	- What is the runtime of this step?
	  collapsed:: true
		- $\Theta(m \log m)$
	- How do we determine if an edge creates a cycle?
	  collapsed:: true
		- When adding edge $\langle u,v \rangle$, run BFS or DFS from $u$ on the MST-so-far to see if there is already a path from $u$ to $v$. If so, don't add the edge.
	- What's the runtime of this implementation?
	  collapsed:: true
		- $\Theta(mn)$. We can do better, but we're going to need a new data structure.
- What operations do the [[Union-Find ADT]] support?
	- `Find(v)`, which returns the name of the set containing node $v$ is in. If `Find(u) == Find(v)`, then `v` and `u` are in the same set/component, and we don't want to add edge $\langle u, v \rangle$.
	- `Union(u,v)`, which combines the components of node $u$ and node $v$ into the same component. We use this when we add edge $\langle u, v \rangle$.
- ![image.png](../assets/image_1622153312667_0.png)
- Runtime of [[Kruskal's Algorithm]]
  collapsed:: true
	- Sorting takes $\Theta(m \log m)$
	- `Find` is called $2m$ times
	- `Union` is called $n-1$ times, because there is at most $n-1$ edges on the graph
	- Runtime $= \Theta(m \log m + m \cdot Find + n \cdot Union)$
## Implementing Union-Find
	- Every node points to a "parent" node that is in the same component.
	- The root of the component has no parent, and is the "captain", or "identifier", of the component.
	- Runtime
		- `Union(u,v)` will be $\Theta(1)$, since we just assign the parent pointer.
		- `Find(v)` will potentially be $\Theta(n)$, if the parent pointers form a linked list.
	- How could we modify Union to ensure the runtime of Find is minimized
		- Always point the smaller-depth tree to the larger depth tree.
		- By doing this, we reduce the runtime of Find to $\Theta(\log n)$