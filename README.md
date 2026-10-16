# SLE-4 :
**System Title:** BFS vs DFS – Maze Path-Finding Profiling

## 1. Introduction

SLE-4 focuses on preparing an Architecture Decision Record (ADR) to explain and justify an important design decision in the BFS vs DFS Maze Path-Finding project.

The project compares Breadth-First Search (BFS) and Depth-First Search (DFS) using execution time, nodes expanded, and path length across different maze sizes.

## 2. Objective

- To compare BFS and DFS algorithms.
- To understand the trade-off between execution speed and shortest-path accuracy.
- To document an important architecture and algorithm decision using an ADR.
- To justify the decision using profiling results from SLE-2.
- To connect the decision with the C4 architecture diagrams created in SLE-3.

## 3. Architecture Decision Record (ADR)

**ADR Title:** Choosing BFS for Shortest-Path Finding in an Unweighted Maze

**Status:** Accepted

### Context
The project compares BFS and DFS on randomly generated mazes of sizes 11×11, 21×21, and 31×31. The results showed that DFS was faster, while BFS consistently found the shortest path.

### Decision
BFS is preferred when finding the shortest path in an unweighted maze is the main requirement. DFS is retained for performance comparison and path exploration.

### Alternatives Considered
1. **DFS:** Faster in the tested cases, but returned longer paths.
2. **A* Search:** A possible future alternative that uses a heuristic to guide the search.
3. **Using both BFS and DFS:** Allows comparison of speed, node expansion, and path quality.

### Justification
- BFS explores nodes level by level.
- BFS guarantees the shortest path in an unweighted maze when all movements have equal cost.
- DFS explores one branch deeply before backtracking.
- DFS was faster in the reported experiments but did not always find the shortest path.
- The Performance Profiler helps compare execution time, nodes expanded, and path length.

### Consequences

**Advantages:**
- Finds the shortest path in an unweighted maze.
- Makes algorithm comparison easier.
- Supports decisions using experimental results.

**Limitations:**
- BFS can consume more memory than DFS.
- BFS took longer than DFS in the tested cases.
- Larger mazes may require evaluating other search strategies.

## 4. Connection with Previous SLEs

### SLE-1: StudyBot
Developed a simple rule-based student chatbot that provides study guidance, exam preparation tips, revision suggestions, and motivation.

### SLE-2: Profiling Report
Compared BFS and DFS using execution time, nodes expanded, and path length across three maze sizes.

### SLE-3: C4 Architecture
Created Context, Container, Component, and Code diagrams to explain the system architecture and separate its responsibilities.

### SLE-4: ADR
Documented and justified the decision to prefer BFS when shortest-path accuracy is important, using profiling results and architecture design.

## 5. Technologies and Concepts Used

- Python
- Breadth-First Search (BFS)
- Depth-First Search (DFS)
- Maze generation and pathfinding
- Performance profiling
- C4 Architecture Model
- Architecture Decision Record (ADR)
- AI-assisted development

## 6. AI Contribution

**AI tools used:** Claude and ChatGPT.

AI tools supported code development and profiling, report preparation, understanding C4 architecture, organizing the ADR, and preparing for the viva.

The project decisions and reported results were reviewed to explain the trade-off between execution speed and path optimality.

## 7. Conclusion

This assignment helped me understand how to document and defend a technical decision. The profiling results showed that DFS was faster in the tested cases, while BFS consistently found the shortest path. Therefore, BFS is the preferred algorithm when shortest-path accuracy is more important than execution speed.

## 8. References

- SLE-2: Profiling Report — BFS vs DFS Maze Path-Finding
- SLE-3: Architectural Design Using the Full C4 Model
- Project functions: `generate_maze()`, `get_neighbors()`, `bfs()`, `dfs()`, and `reconstruct_path()`
