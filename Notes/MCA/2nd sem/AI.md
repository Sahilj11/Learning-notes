# AI and its Application
## Intro
Artificial Intelligence is the part of computer science with designing intelligent computer systems, that is, systems that exhibit the characteristics we associate with intelligence in human behavior.
## AI Techniques
## Production system
A production system in artificial intelligence (AI) is a knowledge-based approach to problem-solving and decision-making. It's a rule-based system that operates by applying a set of rules or productions to a given set of inputs, leading to the derivation of new information or actions. Here are some key notes on production systems in AI:

![](../../statics/Pasted%20image%2020240309151332.png)

1. **Components**:
   - **Production Rules**: These are conditional statements or rules in the form of "if-then" clauses. Each production rule specifies a condition (antecedent) and an action (consequent).
   - **Working Memory**: Also known as the database or working store, it stores the current state of the system, including facts, data, and goals.
   - **Inference Engine**: This is the reasoning mechanism that controls the application of production rules to the working memory. It selects rules whose conditions match the current state of the system and fires them to produce new conclusions or actions.
   - **Conflict Resolution Strategy**: When multiple rules are applicable, a conflict resolution strategy is used to determine which rule to apply first. Common strategies include prioritizing rules based on specificity, recency, or predefined priorities.
   - **Knowledge Base**: This contains the set of production rules and any associated knowledge or facts that the system uses for problem-solving.

2. **Execution Cycle**:
   - **Match**: The inference engine matches the conditions of production rules with the contents of the working memory.
   - **Select**: If multiple rules match, the inference engine selects a rule based on the conflict resolution strategy.
   - **Execute**: The selected rule is executed, resulting in modifications to the working memory, such as adding new facts or updating existing ones.
   - **Repeat**: The cycle continues iteratively until no further rules can be applied or until a termination condition is met.

3. **Applications**:
   - Production systems are widely used in expert systems, which are AI systems designed to mimic the decision-making capabilities of human experts in specific domains.
   - They are also used in areas such as natural language processing, diagnostic systems, planning and scheduling, and robotics.

The classifications you've mentioned pertain to different characteristics of production systems in terms of their behavior during problem-solving processes. Let's explore each of them:

1. **Monotonic Production System**:
   - In a monotonic production system, the application of production rules does not change the system's state or the conclusions already drawn. Once a rule is applied and a conclusion is derived, it remains valid and cannot be retracted or modified.
   - Monotonicity ensures that new information does not contradict or invalidate previously derived conclusions.

2. **Non-monotonic Production System**:
   - Unlike monotonic systems, non-monotonic production systems allow for the retraction or modification of previously derived conclusions.
   - New information may cause revisions to existing conclusions, even if those conclusions were previously considered valid.
   - Non-monotonicity provides greater flexibility in reasoning and decision-making, allowing for adaptive responses to changing circumstances or new evidence.

3. **Partially Commutative Production System**:
   - In a partially commutative production system, the order in which rules are applied can affect the outcome, but not all rules are sensitive to the order of application.
   - Some rules may have dependencies or interactions that require specific sequencing, while others may be applied independently of the order.
   - Partial commutativity allows for a balance between flexibility and control in rule application.

4. **Commutative Production System**:
   - A commutative production system is one in which the order of rule application does not affect the final outcome.
   - All rules are independent of the order in which they are applied, and the system's behavior is invariant under permutations of rule application sequences.
   - Commutativity simplifies reasoning and facilitates parallel or distributed processing, as the system's behavior is deterministic regardless of the execution order.


**Advantages and disadvantages of production systems in AI:**

**Advantages:**

1. **Modularity**: Production systems allow for the decomposition of knowledge into discrete, reusable rules, making it easy to update and maintain the system.
   
2. **Flexibility**: The rule-based nature of production systems allows for easy modification and adaptation to changing requirements or environments.
   
3. **Transparency**: The explicit representation of rules makes the reasoning process transparent and understandable, aiding in system debugging, validation, and explanation.
   
4. **Scalability**: Production systems can handle large amounts of knowledge and complex problem-solving tasks by decomposing them into smaller, manageable rules.
   
5. **Incremental Development**: Systems can be built incrementally by adding rules gradually, allowing for the gradual refinement and improvement of the system over time.
   
6. **Domain Independence**: Production systems can be applied to a wide range of domains, from simple decision-making tasks to complex expert systems.

**Disadvantages:**

1. **Brittleness**: Production systems can suffer from brittleness, where small changes in the input or rules can lead to unexpected or erroneous behavior, especially in complex systems.
   
2. **Complexity**: As the number of rules and interactions between rules grows, the system's behavior may become difficult to understand, debug, and maintain.
   
3. **Inefficiency**: In some cases, production systems may suffer from inefficiencies due to redundant rule firing or inefficient conflict resolution strategies.
   
4. **Difficulty in Learning**: Learning from data or experience can be challenging in rule-based systems, as incorporating new knowledge may require manual intervention to update or create new rules.
   
5. **Expressiveness Limitation**: Production systems may have limitations in representing certain types of knowledge or reasoning, especially those requiring complex relationships or probabilistic reasoning.
   
6. **Knowledge Acquisition Bottleneck**: Developing a comprehensive set of production rules often requires significant domain expertise and effort, leading to a bottleneck in knowledge acquisition.

Despite these disadvantages, production systems remain a powerful and widely used approach in AI, particularly in expert systems and rule-based reasoning applications, due to their modularity, transparency, and flexibility.

# Problem Solving in AI

## Steps 
### State Space Representation
A set of all possible states for a given problem is known as state space of the problem

### Search Space Control
The searching process in AI can be broadly classified into two major types. Viz. Brute Force Search and Heuristics Search. Brute Force Search do not have any domain specific knowledge. All they need is initial state, the final state and a set of legal operators. 

#### Depth First Search
Depth-First Search is one the important technique of Brute Force Search  
In Depth-First Search, search begins by expanding the initial node, i.e., by using an operator, generate all successors of the 
initial node and test them

##### Steps 
1. Put the initial node on the list of START.
2. If (START is empty) or (START = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them and add them at the beginning of START.
6. Go to step 2.

![](../../statics/Pasted%20image%2020240309152904.png)

#### Breath First Search
Breadth first search is also like depth first search. Here searching progresses level by level. Unlike depth first search, which goes deep into the tree. An operator employed to generate all possible children of a node

##### Steps
1. Put the initial node on the list of START.
2. If (START is empty) or (START = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them and add them at the tail of START.
6. Go to step 2.

![](../../statics/Pasted%20image%2020240309153024.png)

**Issues**
1. Amount of time needed to generate all the nodes is considerable because of the time complexity.
2. Memory constraint is also a major hurdle because of space complexity.
3. The Searching process remembers all unwanted nodes, which is of no practical use for the search

## Heuristic Search technique
The basic idea of heuristic search is that, rather than trying all possible search paths, you try and focus on paths that seem to be getting you nearer your goal state

**Heuristic Function**
A heuristic function, also known as a heuristic evaluation function or simply a heuristic, is a function that provides an estimate of how close a given state is to the goal state.
Heuristic functions are designed to exploit domain-specific knowledge or rules of thumb to prioritize exploration of states that are likely to lead to a solution.

### Types 
#### Hill Climbing
Hill climbing uses a simple heuristic function viz., the amount of distance the node is from the goal. This algorithm is also called Discrete Optimization Algorithm. 
**Steps**
1. Put the initial node on the list of START.
2. If (START is empty) or (STRAT = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them. Find out how far they are from the goal node. Sort them by the remaining distance from the goal and add them to the beginning of START.
6. Go to step 2.
![](../../statics/Pasted%20image%2020240309153847.png)
**Problems**
- Local Maximum: A state that is better than all its neighbours but no so when compared to the states that are farther away.
- Plateau: A flat area of search space, in which all the neighbours have the same value.
- Ridge: Described as a long and narrow stretch of elevated ground or narrow elevation or raised part running along or across a surface by the Oxford English Dictionary
**Sol**
- Backtracking for local maximum: Backtracking helps in undoing what has been done so far and permits to try a totally different path to attain the global peak.
- A big jump is the solution to escape from the plateau.
- Trying different paths at the same time is the solution for circumventing ridges

#### Best First Search 
Best first search is a little like hill climbing, in that it uses an evaluation function and always chooses the next node to be that with the best score. The heuristic function used here (evaluation function) is an indicator of how far the node is from the goal node. Goal nodes have an evaluation function value of zero.
**Steps**
1. Put the initial node on the list of START.
2. If (START is empty) or (STRAT = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them. Find out how far they are from the goal node. Sort all the children generated so far by the remaining distance from the goal.
6. Name this list as START 1.
7. Replace START with START 1.
8. Go to step 2.

#### A\* 
Each time A* enters a state, it calculates the cost f(n), (n being the neighboring node), to travel to all of the neighboring nodes, and then enters the node with the lowest value of f(n).
f(n) = g(n) + h(n)
g(n) being the value of the shortest path from the start node to node n, and h(n) being a heuristic approximation of the node’s value.
The efficiency of A* is highly dependent on the heuristic value h(n), and depending on the type of problem, we may need to use a different heuristic function for it to find the optimal solution.

In the context of the A* algorithm, heuristic functions can possess two fundamental properties: admissibility and consistency. These properties are crucial for ensuring the effectiveness and optimality of the A* algorithm in finding the shortest path from the start node to the goal node. Let's discuss each property:

1. **Admissibility**:
   - A heuristic function is admissible if it never overestimates the true cost to reach the goal from any given node.
   - Formally, for all nodes \(n\) in the search space, the heuristic value \(h(n)\) is less than or equal to the true cost from \(n\) to the goal.
   - Mathematically, \(h(n) \leq h^*(n)\), where \(h^*(n)\) represents the true cost to reach the goal from node \(n\).
   - Admissible heuristic functions provide an optimistic estimate of the remaining cost to reach the goal, guiding the A* algorithm to explore promising paths while guaranteeing that the optimal path will be found.

2. **Consistency (or Monotonicity)**:
   - A heuristic function is consistent, or monotonic, if the estimated cost from any given node to its successor nodes, plus the heuristic estimate of the cost from those successor nodes to the goal, is never less than the heuristic estimate of the cost from the current node to the goal.
   - Formally, for all nodes \(n\) and its successor \(n'\) connected by an edge with cost \(c\), the following inequality holds: \(h(n) \leq c + h(n')\).
   - Mathematically, if \(f\) is the total estimated cost to reach the goal through node \(n'\), then \(f(n) \leq f(n') + c\).
   - Consistent heuristic functions maintain a property known as the "triangle inequality," which ensures that the estimated cost of reaching the goal from any node is non-decreasing along the path.
   - Consistency guarantees that the A* algorithm will always find the optimal solution, even in the presence of cycles or redundant paths in the search space.
## Problem reduction
Problem reduction is a problem-solving strategy used in artificial intelligence (AI) and computer science to solve complex problems by breaking them down into smaller, more manageable subproblems. This approach involves transforming the original problem into simpler forms until a solution can be easily derived. Here are some key notes on problem reduction in AI:

1. **Basic Idea**:
   - Problem reduction involves decomposing a complex problem into a series of simpler subproblems, each of which is easier to solve.
   - The solution to the original problem is obtained by solving the subproblems and combining their solutions in a systematic manner.

2. **Steps**:
   - **Identify Subproblems**: Break down the original problem into smaller, more manageable subproblems. Each subproblem should represent a distinct aspect or component of the original problem.
   - **Solve Subproblems**: Solve each subproblem independently using appropriate problem-solving techniques or algorithms. This may involve applying specific algorithms, heuristics, or domain-specific knowledge.
   - **Combine Solutions**: Combine the solutions to the subproblems to obtain a solution to the original problem. This step may involve integrating or synthesizing the individual solutions in a coherent manner.

3. **Example**:
   - Consider the problem of finding the shortest path from a start node to a goal node in a graph. Problem reduction can be applied by decomposing this problem into smaller subproblems, such as finding the shortest path from the start node to each intermediate node along the way. Once the shortest paths to the intermediate nodes are determined, the overall shortest path can be obtained by combining these solutions.

4. **Benefits**:
   - **Simplicity**: Problem reduction simplifies complex problems by breaking them down into smaller, more understandable components.
   - **Modularity**: Each subproblem can be solved independently, allowing for modular design and implementation.
   - **Efficiency**: Solving smaller subproblems can be computationally more efficient than tackling the entire problem at once, especially for large and complex problem domains.
   - **Scalability**: Problem reduction facilitates scalability by enabling the solution of large-scale problems through incremental decomposition.

5. **Applications**:
   - Problem reduction is used in various AI applications, including planning and scheduling, theorem proving, optimization, and decision making.
   - It is particularly useful in domains where problems can be decomposed into smaller, more tractable components, such as logistics, engineering, and operations research.

6. **Challenges**:
   - Identifying appropriate subproblems and determining how to combine their solutions effectively can be challenging, especially for highly interconnected or interdependent problem domains.
   - The decomposition of the original problem may introduce additional complexity or overhead, requiring careful consideration of trade-offs.

### Relationship among Sub Problems(AND-OR)
![](../../statics/Pasted%20image%2020240309162728.png)

In problem reduction, particularly in the context of AI planning and reasoning, And-Or graphs are often used to represent the relationships among subproblems. An And-Or graph is a directed graph where nodes represent subproblems, and edges represent the relationships among these subproblems. There are two types of edges: And edges and Or edges.

1. **And Edges**:
   - An And edge represents a dependency or conjunction between subproblems.
   - If a node (A) is connected to multiple nodes (B1,B2,B3...) by And edges, it means that all of these subproblems must be solved in order to solve ( A ).
   - In other words, the solutions to all connected subproblems must be combined or satisfied to progress to the next level.

2. **Or Edges**:
   - An Or edge represents a choice or disjunction between subproblems.
   - If a node ( A ) is connected to multiple nodes ( B1, B2, ..., Bn ) by Or edges, it means that any one of these subproblems can be solved to progress to the next level.
   - In other words, the solutions to any one of the connected subproblems are sufficient to satisfy the requirements of \( A \).

3. **Combining Subproblems**:
   - In an And-Or graph, the combination of subproblems occurs at And nodes.
   - At an And node, the solutions to all connected subproblems are combined in some way to satisfy the requirements of the parent node.
   - The combination may involve aggregation, merging, synchronization, or other operations depending on the problem domain.

4. **Efficiency**:
   - And-Or graphs provide a structured representation of the relationships among subproblems, which can facilitate efficient problem-solving algorithms.
   - By carefully analyzing the graph structure, it is possible to develop algorithms that exploit the dependencies and choices among subproblems to minimize the search space and computation time.

5. **Applications**:
   - And-Or graphs are commonly used in AI planning, theorem proving, decision making, and other areas where problems can be decomposed into a hierarchy of subproblems with complex dependencies and choices.

In summary, And-Or graphs provide a useful framework for representing and reasoning about the relationships among subproblems in problem reduction. They allow for the explicit representation of dependencies and choices, enabling more efficient and systematic problem-solving algorithms.

**Steps for AO\***
1. Place the start node on open.
2. Using the search tree, compute the most promising solution tree TP.
3. Select node n that is both on open and a part of tp, remove n from open and place it no closed.
4. If n is a goal node, label n as solved. If the start node is solved, exit with success where tp is the solution tree, remove all nodes from open with a solved ancestor.
5. If n is not solvable node, label n as unsolvable. If the start node is labeled as unsolvable, exit with failure. Remove all nodes from open, with unsolvable ancestors.
6. Otherwise, expand node n generating all of its successor compute the cost of for each newly generated node and place all such nodes on open.
7. Go back to step (2)