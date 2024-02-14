Detecting a cycle in Graph:

A graph has a cycle if it has a back edge. A back edge is an edge that connects a node with itself or an ancestor in the graph.
A cycle can be detected by both DFS and BFS in linear time O(V + E)

rough algorithm:
1. Perform DFS and maintain a map/array of the call stack of a node
2. If a node is seen in the call stack map/array before it finishes its won call then it is a back edge and the cycle exists in the graph

References:
MIT video: https://www.youtube.com/watch?v=tg96sZqhXyU&ab_channel=OnlineLearning