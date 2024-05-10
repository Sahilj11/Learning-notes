# AI and its Application
## Intro
Developing programs to solve complex problems by application of process that are analogous to human reasoning processes

## Knowledge
Knowledge is organised information , in other words it is a information which helps in decision making
Intelligence is abilty to draw useful inference from available from the available knowledge
Human expert has two type of knowledge
- Domain-specific :- deals with all kinds of knowledge about a particular domain. types of domain-specific knowledge
	- Knowledge about item or object:- this specifies the description and characteristics of object and its distinct marking for descriptive purpose
	- Knowledge about events:- For this, knowledge is set of procedures . eg. what will happen if mentos droped in softdrink
	- Knowledge about task performance :- knowledge about capacity of various objects and limitation of each .  eg. is jeep good for hilly areas
	- Knowledge about knowledge (Meta knowledge):- it helps in controlling and planning the reasoning process. it has two parts . Meta assertion and Meta rules
![](../../statics/Pasted%20image%2020240510063027.png)
Layers of knowledge
- Layer 1:- Factual Knowledge
- Layer 2:- Heuristic 
- Layer 3:- Meta knowledge

## AI Problems
AI problems refer to the various types of challenges and tasks that artificial intelligence (AI) systems aim to solve or address. These problems span a wide range of domains and applications, each requiring different techniques, algorithms, and approaches for effective solutions. Here are some key points about AI problems:

1. **Classification**:
   - A **classification** problem is about assigning one or more categories to a document, product, person, or image—essentially anything. Examples include:
	- Categorizing incoming support tickets by relevant topics
	- Classifying images of silicon wafers as containing defects or no defects
2. Regression:- A **regression problem** is about estimating _numerical_ values given some input. For example, trying to predict the number of months before a machine needs service given the conditions of the current machine, or predicting how specific drug dosage affects blood pressure.
3. Recommendation:- A **recommendation problem** is about providing personalized content or products to a group of people. Examples include:
	- Product recommendation
	- Recommendations on who to follow
	- Recommendations on jobs to apply for
	- Recommendations on articles to read
4. Search relevance:- A **search relevance** problem is about improving the rankings of search results shown to users. Often search relevance improvement starts with the analysis of search logs to diagnose problems using hard data. Search improvement may or may not require heavy use of machine learning
5. Information extraction:- An **information extraction** problem is about extracting specific information from large volumes of text data. One of the goals of information extraction is to fill templates using data extracted from raw text. Examples include:
	- Extracting patient symptoms from large volumes of clinical notes
6. Entity Recognition:- **Entity recognition** is about detecting and extracting _specific_ information from unstructured data. This specific information is often pre-defined. This can include:
	- Names of places
	- Organizations
7. Sentiment analysis:- **Sentiment Analysis** is about discovering emotions in text data such as user reviews, social media comments, and surveys. For example, automatically detecting customer sentiment in social media channels after a new product release.

## AI Application
- Games
- Vision and speech 
- Natural language processing
- Robotics
## AI Techniques
Artificial intelligence (AI) techniques refer to the methods, algorithms, and approaches used to develop intelligent systems that can perceive, reason, learn, and act in complex environments. These techniques encompass a wide range of methodologies across different areas of AI research and application. Here are some key notes on AI techniques:

1. **Search Algorithms**:
   - Search algorithms are used to find solutions to problems by exploring a search space.
   - Examples include depth-first search, breadth-first search, A* search, hill climbing, genetic algorithms, and simulated annealing.
   - Search algorithms are commonly used in problem-solving tasks such as route planning, scheduling, and optimization.

2. **Knowledge Representation and Reasoning**:
   - Knowledge representation involves encoding knowledge about the world in a format suitable for computational reasoning.
   - Techniques include propositional logic, predicate logic, semantic networks, frames, ontologies, and description logics.
   - Reasoning techniques include deductive reasoning, inductive reasoning, abductive reasoning, and probabilistic reasoning.

3. **Machine Learning**:
   - Machine learning is a subfield of AI that focuses on developing algorithms and models that enable computers to learn from data.
   - Techniques include supervised learning, unsupervised learning, reinforcement learning, and deep learning.
   - Machine learning is used in various applications such as classification, regression, clustering, anomaly detection, and natural language processing.

4. **Natural Language Processing (NLP)**:
   - NLP involves developing algorithms and models for understanding, interpreting, and generating human language.
   - Techniques include parsing, semantic analysis, sentiment analysis, machine translation, question-answering, and text generation.
   - NLP is used in applications such as chatbots, virtual assistants, sentiment analysis, and language translation.

5. **Computer Vision**:
   - Computer vision focuses on developing algorithms and systems that enable computers to understand and interpret visual information from images or videos.
   - Techniques include object detection, image classification, image segmentation, and scene understanding.
   - Computer vision is used in applications such as autonomous vehicles, surveillance systems, medical image analysis, and augmented reality.
## Problem representation
- Types of representation 
	- State Space Representation 
	- Problem reduction
### State space representation
- A set of all possible states of a given problem is known as state space of the problem. one need initial state , set of operators(operators often refer to functions or procedures that manipulate or transform data or representations within an algorithm or model) and goal state
- ![](../../statics/Pasted%20image%2020240510071922.png)
#### Features
1. **States**: The state space comprises all possible states that the system can occupy. States represent the configurations of the system at a particular point in time. These states can be discrete, continuous, or a combination of both.
2. **State Variables**: State variables are the quantities used to describe the state of the system. They capture relevant information about the system's configuration, such as position, velocity, temperature, etc. State variables can be scalar, vector, or even more complex data structures.
3. **Actions**: Actions are the possible transitions that the system can make from one state to another. These actions represent the decisions or interventions that can be taken to change the system's state. In AI, actions are often associated with agents or controllers that interact with the environment.
4. **Transitions**: Transitions describe how the system moves from one state to another based on the actions taken. A transition function or dynamics model specifies the probability or deterministically how the system evolves over time. These transitions can be stochastic or deterministic, depending on the nature of the system.
5. **Initial State**: The initial state of the system represents its configuration at the beginning of the process or problem-solving task. It serves as the starting point for exploring the state space and finding solutions.
6. **Goal State**: The goal state defines the desired configuration or outcome that the system aims to achieve. In problem-solving tasks, the goal state represents the solution or the desired end result.
7. **Constraints**: State space representation can incorporate constraints that limit the set of permissible states or actions. These constraints may arise from physical limitations, resource constraints, or domain-specific requirements.

#### Pros and cons of state space
##### Importance:

1. **Problem Formulation**: State space representation helps in formulating a problem by defining its states, actions, transitions, and goals. This structured representation facilitates the understanding of the problem domain.
2. **Algorithm Design**: Many AI algorithms, such as search algorithms (e.g., breadth-first search, depth-first search, A*), planning algorithms (e.g., STRIPS, Graphplan), and reinforcement learning algorithms, operate on state spaces. They use state transitions and goals to find solutions or make decisions.
3. **Complex Systems Modeling**: State space representation is crucial for modeling complex systems, where the interactions between different components lead to emergent behavior. By representing the system's state and the transitions between states, AI systems can simulate and predict the system's behavior.
4. **Problem Solving**: AI agents can navigate through the state space to find solutions or make decisions that achieve desired goals. This is applicable in various domains such as robotics, game playing, logistics, scheduling, and natural language processing.
5. **Efficiency**: Well-designed state space representations can lead to more efficient problem-solving algorithms. By pruning unnecessary states or optimizing search strategies, AI systems can find solutions more quickly.

##### Limitations:
1. **State Explosion**: In complex problem domains, the state space can become prohibitively large. As the number of states and transitions increases, the computational resources required to explore the entire space grow exponentially. This can make problem-solving infeasible or computationally expensive.
2. **Intractability**: Some problems may have state spaces that are too large to explore exhaustively or even to represent explicitly. In such cases, approximation techniques or heuristics may be necessary, which can lead to suboptimal solutions.
3. **Incomplete Information**: State space representations may not capture all relevant aspects of the problem domain, leading to incomplete or inaccurate models. This can result in suboptimal solutions or failure to find solutions altogether.
4. **Dynamic Environments**: In dynamic environments where states and transitions change over time, maintaining an accurate representation of the state space can be challenging. This can affect the effectiveness of planning and decision-making algorithms.
5. **Curse of Dimensionality**: In high-dimensional state spaces, the density of states decreases exponentially with the number of dimensions. This can make it difficult to explore the space effectively and to generalize solutions across different states.
### Problem reduction
- In this complex problem is broken down or decomposed into set of premitive sub-problems . Solution for these primitive sub-problems are easily obtained . the solution of all sub problems collectively give the solution for complex problem
#### AND/OR Tree
- Initial complex probelm is parent node and primitive sub-problems form the leaf node
- In AND - solution of problem obtained by solving all of sub problem
- In OR - any of sub problem
![](../../statics/Pasted%20image%2020240510080301.png)
## Production system
### Intro
- Production systems are rules of form C->A where LHS  is known as condition and RHS is known as Action
- LHS describe applicability of rule and RHS describe operation to be performed
- Formal definition:- if one adopts a system with production rules and rules interpreter then that system known as production system
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
### Types of production system
- Monotonic:-  Production system in which application of a rule **never** prevents later application of another rule that could have been applied at first time rule was selected . below has 1 and 2 rule , some steps of 1 is done and after that some of 2 is done 
	- ![](../../statics/Pasted%20image%2020240510073817.png)
- Non Monotonic:- Production system in which application of a rule  prevents later application of another rule that could have been applied at first time rule was selected 
- Partial commutative:- This system states that if application of a particular rule transform state x into y then permutation of those rules also transform state x to y
- Commutative :- it is both monotonic and partial commutative
#### Relations (showing what type of system good for what type of problem)
![](../../statics/Pasted%20image%2020240510074533.png)
## Components of AI
![](../../statics/Pasted%20image%2020240510080426.png)
## Searching 
### Intro
- At every stage in state space generating algo that we need to apply to reach goal state . search is systematic examination to find goal state
- Things needed for search
	- Initial state description of problem
	- set of legal operators that changes the state. In chess , it is the rule
	- final or goal state
### Types 
#### Uninformed (Brute force)
- these explore all alternative during the search process . they do not domain specific knowledge. All they need initial state , legal operators and goal state
- DFS and BFS
##### DFS
Depth-First Search is one the important technique of Brute Force Search  
In Depth-First Search, search begins by expanding the initial node, i.e., by using an operator, generate all successors of the 
initial node and test them

**Steps** 
1. Put the initial node on the list of START.
2. If (START is empty) or (START = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them and add them at the beginning of START.
6. Go to step 2.

![](../../statics/Pasted%20image%2020240309152904.png)

Time Complexity :- amt of time needed is proportional to the depth that and branching factor that for DFS seach the total amt of time needed O(b<sup>d</sup>)
Space Complexity:- DFS only store the path it is currently pursing hence space complexity is linear function of depth O(d)
**Features**
1. **Exploration of Entire Branches:** DFS traverses one branch of a graph as deeply as possible before backtracking, making it suitable for problems requiring exhaustive exploration of paths.
2. **Backtracking:** DFS efficiently explores alternative paths by backtracking when it reaches a dead-end, ensuring thorough exploration of the graph without duplicating efforts.
3. **Memory Efficiency:** DFS typically requires less memory compared to other traversal algorithms like Breadth-First Search (BFS), making it suitable for memory-constrained environments or large graphs.
4. **Recursion:** DFS can be implemented using recursion, simplifying its implementation and resulting in concise and elegant code for exploring graph structures.
5. **Applications:** DFS has diverse applications in various domains, including pathfinding, network analysis, topological sorting, identifying strongly connected components, and more, showcasing its versatility and usefulness in solving graph-related problems.
**Pros and Cons**

**Advantages:**
1. **Simplicity:** DFS is relatively easy to understand and implement. It follows a simple approach of exploring deeper into the graph before backtracking.
2. **Memory Efficiency:** DFS typically uses less memory compared to Breadth-First Search (BFS), as it only needs to store information about the current path from the starting node to the current node.
3. **Space Efficiency:** In many cases, DFS can be more space-efficient than BFS. This is particularly true when the graph has a large number of nodes but only a few paths between them.
4. **Applications:** DFS has various applications in graph theory and computer science, including topological sorting, finding strongly connected components, solving puzzles, and more.
5. **Speed:** In certain situations, DFS can be faster than BFS, especially when the search space is large and solutions are located deep in the graph. DFS tends to go deep quickly before exploring alternatives, which can lead to faster solutions in some scenarios.

**Disadvantages:**
1. **Completeness:** DFS does not guarantee finding the shortest path between two nodes. It may find a solution, but it might not be the optimal one. This can be a disadvantage if finding the shortest path is critical.
2. **Non-Optimality:** Due to its nature, DFS might traverse deep into one branch of the graph before considering other branches. This can lead to non-optimal solutions in some cases, especially if the goal is to find the shortest path or the solution closest to the root.
3. **Stack Overflow:** DFS is implemented using recursion or an explicit stack. In cases of deep or infinite graphs, DFS may lead to stack overflow errors, especially in recursive implementations, as it goes deeper and deeper into the graph without finding a solution or backtracking.
4. **Disconnected Graphs:** In the case of disconnected graphs, DFS may not visit all nodes unless modified to do so. It can get stuck exploring one connected component and may not explore others unless explicitly instructed.
5. **Time Complexity:** Although DFS can be fast in certain scenarios, its time complexity can be high in dense graphs or graphs with cycles. In such cases, DFS may visit many nodes repeatedly, leading to longer execution times.
##### BFS
Breadth first search is also like depth first search. Here searching progresses level by level. Unlike depth first search, which goes deep into the tree. An operator employed to generate all possible children of a node

**Steps**
1. Put the initial node on the list of START.
2. If (START is empty) or (START = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them and add them at the tail of START.
6. Go to step 2.

![](../../statics/Pasted%20image%2020240309153024.png)

time complexity: - Same as DFS
Space complexity:- same as time complexity of BFS (It has to remember every node it is generated)

**Issues**
1. Amount of time needed to generate all the nodes is considerable because of the time complexity.
2. Memory constraint is also a major hurdle because of space complexity.
3. The Searching process remembers all unwanted nodes, which is of no practical use for the search

#### Informed Search(Heuristics)
- The basic idea of heuristic search is that, rather than trying all possible search paths, you try and focus on paths that seem to be getting you nearer your goal state
- Used when
	- Problems for which no exact algorithms are known and one need to find approximate and appropritate solution . For eg. Computer vision
	- Problem for which exact solution are known but computationally not feasible For eg. rubiks cube
**Heuristic Function**
- A heuristic function, also known as a heuristic evaluation function or simply a heuristic, is a function that provides an estimate of how close a given state is to the goal state. 
- Heuristic functions are designed to exploit domain-specific knowledge or rules of thumb to prioritize exploration of states that are likely to lead to a solution.
**Hill Climbing**

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
![](../../statics/Pasted%20image%2020240510101953.png)
**Sol**
- Backtracking for local maximum: Backtracking helps in undoing what has been done so far and permits to try a totally different path to attain the global peak.
- A big jump is the solution to escape from the plateau. it is recommended because in plateau all neghbiour plateau points have same value
- Trying different paths at the same time is the solution for circumventing ridges

#### Best First Search 
Best first search is a little like hill climbing, in that it uses an evaluation function and always chooses the next node to be that with the best score. The heuristic function used here (evaluation function) is an indicator of how far the node is from the goal node. Goal nodes have an evaluation function value of zero.
**Steps**
1. Put the initial node on the list of START.
2. If (START is empty) or (START = GOAL) terminate search.
3. Remove the first node from the list of START. Call this node d.
4. If (d = GOAL) terminate search with success.
5. Else if node d has successors, generate all of them. Find out how far they are from the goal node. Sort all the children generated so far by the remaining distance from the goal.
6. Name this list as START 1.
7. Replace START with START 1.
8. Go to step 2.

#### A\* 
![](../../statics/Pasted%20image%2020240510105820.png)
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
#### AO\*
![](../../statics/Pasted%20image%2020240510110259.png)
![](../../statics/Pasted%20image%2020240510110504.png)
![](../../statics/Pasted%20image%2020240510110555.png)

#### Generate and test
![](../../statics/Pasted%20image%2020240510111621.png)
## Minimax
Minimax is a decision-making algorithm commonly used in game theory, specifically in two-player zero-sum games, such as chess, checkers, or tic-tac-toe. Here are some notes on the minimax algorithm:
Time complexity :- O(b<sup>d</sup>) , here b is number of child and d is depth

The main objective of minimax is to find the optimal move for a player, assuming that the opponent will also play optimally. It aims to minimize the potential loss (for the worst case scenario) while maximizing the potential gain.
The plausible move generator generates necessary states for further evaluation and static function ranks each of the state
![](../../statics/Pasted%20image%2020240510133812.png)
![](../../statics/Pasted%20image%2020240510133824.png)
![](../../statics/Pasted%20image%2020240510133902.png)
**Issues**
1. **Exponential Growth:** The minimax algorithm explores the entire game tree, which can lead to exponential growth in the number of nodes to be evaluated, especially in complex games with a large branching factor and depth.
2. **Computational Complexity:** As the depth of the game tree increases, the computational cost of evaluating all possible moves becomes prohibitive, making it impractical for real-time decision-making in complex games.
3. **Redundant Evaluations:** Minimax may evaluate the same game state multiple times, leading to redundant computations and wasted resources. This inefficiency becomes more pronounced as the size of the game tree increases.
4. **Memory Requirements:** Storing the entire game tree in memory for evaluation can require a significant amount of memory, especially for games with large branching factors and deep search depths.
5. **Optimality Assumption:** Minimax assumes that both players play optimally, which may not always hold true in practice, especially in games with imperfect information or stochastic elements.
### Alpha-beta pruning 
Alpha-beta pruning is an optimization technique used in the minimax algorithm to reduce the number of nodes evaluated in the search tree. Here are some notes on alpha-beta pruning:
![](../../statics/Pasted%20image%2020240510134535.png)

1. **Objective**: The main goal of alpha-beta pruning is to eliminate branches of the search tree that cannot possibly influence the final decision. By doing so, it reduces the number of nodes that need to be evaluated, thereby improving the efficiency of the minimax algorithm.

2. **Pruning Condition**: Alpha-beta pruning relies on two parameters: alpha and beta. Alpha represents the best value found so far for the maximizing player (Max), while beta represents the best value found so far for the minimizing player (Min). Pruning occurs when the current node's value falls outside the range defined by alpha and beta.

3. **Pruning Rules**:
   - If the value of a node is greater than or equal to beta (for Max), or less than or equal to alpha (for Min), pruning occurs because it implies that the opposing player already has a better move available elsewhere in the tree.
   - When pruning occurs, the evaluation of the subtree rooted at that node is skipped, and the algorithm moves on to explore other branches of the tree.

4. **Improvement over Minimax**: Alpha-beta pruning improves upon the minimax algorithm by effectively reducing the search space without affecting the final decision. It allows the algorithm to explore only the most promising branches of the game tree, leading to significant performance gains, especially in games with large state spaces.

5. **Optimality**: Alpha-beta pruning does not affect the optimality of the minimax algorithm. It preserves the correctness of the search by ensuring that the final decision remains the same as if the entire search tree were explored.

6. **Efficiency**: The efficiency of alpha-beta pruning depends on the order in which nodes are evaluated. By evaluating more promising nodes first, the likelihood of pruning occurring increases, resulting in greater efficiency. However, even with a random evaluation order, alpha-beta pruning still provides significant performance improvements over the basic minimax algorithm.

7. **Application**: Alpha-beta pruning is commonly used in various two-player zero-sum games, such as chess, checkers, and Go, where it dramatically reduces the computational overhead of searching through large game trees.

8. **Parallelization**: Alpha-beta pruning can be parallelized to explore multiple branches of the game tree concurrently. This further enhances its efficiency, especially on multi-core or distributed computing systems.
## Constraint Satisfaction Problem
![](../../statics/Pasted%20image%2020240309180628.png)
Constraint Satisfaction Problems (CSPs) are a class of problems in Artificial Intelligence (AI) where variables must be assigned values while satisfying a set of constraints. Here are some notes on CSPs:

1. **Definition**: A CSP consists of a set of variables, each with a domain of possible values, and a set of constraints that specify the allowable combinations of values for subsets of variables.

2. **Variables**: Variables represent unknowns in the problem that need to be assigned values. Each variable has a domain, which is the set of possible values it can take.

3. **Domains**: Domains define the allowable values for each variable. Domains can be finite or infinite, discrete or continuous, depending on the problem domain.

4. **Constraints**: Constraints specify restrictions on the allowable combinations of values for subsets of variables. Constraints can be unary (acting on a single variable), binary (acting on two variables), or higher-order (acting on more than two variables).

5. **Satisfaction**: A solution to a CSP is an assignment of values to variables such that all constraints are satisfied. A solution must respect the domains of the variables and satisfy all constraints.

6. **Examples**: CSPs are used in various AI applications, including scheduling problems, timetabling, configuration problems, logistics, and resource allocation.

7. **Search Algorithms**: CSPs can be solved using various search algorithms, such as backtracking, constraint propagation, and local search methods like hill climbing or simulated annealing.

8. **Backtracking**: Backtracking is a widely used algorithm for solving CSPs. It systematically explores the search space by assigning values to variables and backtracking when a dead-end is reached. It uses depth-first search and can be augmented with heuristics to improve efficiency.

9. **Constraint Propagation**: Constraint propagation techniques, such as arc consistency and forward checking, aim to reduce the search space by eliminating values from domains that cannot participate in any solution. This is achieved by propagating constraints and updating domains accordingly.

10. **Local Search Methods**: Local search algorithms, like hill climbing and simulated annealing, iteratively improve a solution by making small changes to assignments. These methods are useful for large and complex CSPs where complete search algorithms may be impractical.

11. **Complexity**: The complexity of solving CSPs depends on factors such as the size of the search space, the structure of constraints, and the efficiency of the search algorithm. In general, CSPs are NP-complete, meaning that there is no known polynomial-time algorithm to solve them in the worst case.
## What is Uninformed Search and how differ from informed
Uniformed search, also known as blind search, is a class of search algorithms that explore the search space without using any domain-specific knowledge about the problem. These algorithms rely solely on the structure of the search space, such as the arrangement of states and the transitions between them. Examples of uniformed search algorithms include Breadth-First Search (BFS), Depth-First Search (DFS), and Iterative Deepening Depth-First Search (IDDFS).

**Advantages of Uniformed Search:**

1. **Completeness**: Uniformed search algorithms are guaranteed to find a solution if one exists, given sufficient time and memory resources. This property ensures that the algorithm will not overlook a solution.

2. **Simplicity**: Uniformed search algorithms are often simple to implement and understand. They typically involve basic data structures and straightforward exploration strategies.

3. **No Heuristic Bias**: Since uniformed search algorithms do not use domain-specific knowledge or heuristics, they avoid any potential biases introduced by heuristic information. This can be beneficial in situations where heuristic estimates are unreliable or unavailable.

**Disadvantages of Uniformed Search:**

1. **Inefficiency**: Uniformed search algorithms may explore a large portion of the search space before finding a solution, especially in cases where the search space is vast or the goal state is located far from the initial state. This can result in high time and memory requirements.

2. **Lack of Guidance**: Uniformed search algorithms do not use any information about the goal state or the structure of the search space beyond what is explicitly provided by the problem definition. As a result, they may waste time exploring unpromising paths that lead away from the goal.

3. **Optimality**: While uniformed search algorithms guarantee completeness, they do not necessarily guarantee optimality. In some cases, they may find a suboptimal solution before finding the optimal one. This is particularly true for algorithms like DFS, which may prioritize exploration of deep branches of the search tree.

In contrast, informed search algorithms, also known as heuristic search, use domain-specific knowledge to guide the search process more efficiently. By incorporating heuristic information, these algorithms can prioritize exploration of more promising paths and often find solutions more quickly than uniformed search algorithms. However, informed search algorithms may not guarantee completeness or optimality, and their performance depends heavily on the accuracy of the heuristic information provided.

## Problem Representation and its Types
Problem representation plays a crucial role in artificial intelligence (AI) as it defines how a problem is formulated and solved. Here are various types of problem representations along with their advantages and disadvantages:

1. **State Space Representation**:
   - **Description**: Represents the problem as a set of states, along with the possible transitions between states.
   - **Advantages**:
     - Provides a clear and intuitive representation of the problem's dynamics.
     - Facilitates the use of search algorithms such as depth-first search, breadth-first search, and A* search.
   - **Disadvantages**:
     - May lead to a large and complex search space, especially for problems with many states or continuous state spaces.
     - Requires careful modeling of state transitions, which can be challenging for some problems.

2. **Predicate Logic Representation**:
   - **Description**: Represents the problem using logical predicates, variables, and quantifiers.
   - **Advantages**:
     - Allows for precise and formal representation of relationships and constraints within the problem domain.
     - Supports logical inference and reasoning, enabling deduction and problem-solving.
   - **Disadvantages**:
     - Can be cumbersome and verbose, especially for complex problems with many variables and constraints.
     - May suffer from computational complexity, particularly in cases with large or infinite domains.

3. **Network Representation**:
   - **Description**: Represents the problem using a network or graph structure, where nodes represent entities or states, and edges represent relationships or transitions.
   - **Advantages**:
     - Well-suited for modeling problems involving interconnected entities and complex dependencies.
     - Provides a graphical visualization of the problem, aiding in understanding and analysis.
   - **Disadvantages**:
     - May lack explicit representation of states and transitions, making it challenging to apply certain search algorithms directly.
     - Can become unwieldy and difficult to interpret for large and complex networks.

4. **Feature-Based Representation**:
   - **Description**: Represents the problem by focusing on relevant features or attributes.
   - **Advantages**:
     - Simplifies the problem by abstracting away irrelevant details and focusing on essential aspects.
     - Enables the use of machine learning techniques for problem-solving and decision-making.
   - **Disadvantages**:
     - Requires careful selection and design of features, which may not always capture the essence of the problem.
     - May lead to information loss if important features are overlooked or misrepresented.
## Difference b/w Depth first search and Breath first search
Depth First Search (DFS) and Breadth First Search (BFS) are two fundamental search algorithms used to traverse and explore graph or tree structures. Here are the main differences between DFS and BFS:

1. **Strategy**:
   - **DFS**: Explores as far as possible along each branch before backtracking. It goes deep into the graph before exploring other branches.
   - **BFS**: Explores neighbors of a node before moving on to explore further neighbors. It systematically explores nodes level by level, starting from the initial node.

2. **Order of Exploration**:
   - **DFS**: Prioritizes exploration of the deepest unexplored node first. It follows a depth-first traversal order, visiting nodes along the current path until it reaches a dead-end before backtracking.
   - **BFS**: Prioritizes exploration of all neighboring nodes at the current level before moving on to nodes at the next level. It follows a breadth-first traversal order, visiting nodes level by level.

3. **Data Structure**:
   - **DFS**: Uses a stack data structure to keep track of nodes to be explored. It utilizes recursion or an explicit stack to manage backtracking.
   - **BFS**: Uses a queue data structure to keep track of nodes to be explored. It ensures that nodes are explored in the order they are discovered, leading to a level-wise traversal.

4. **Completeness**:
   - **DFS**: May not find a solution if the search space is infinite or if the graph contains cycles, as it can get trapped in infinite loops.
   - **BFS**: Guarantees to find the shortest path to a solution if one exists, provided that the graph is finite and there are no cycles.

5. **Space Complexity**:
   - **DFS**: Consumes less memory compared to BFS as it only needs to keep track of a single path at a time. However, it may require more space in the case of deep or infinite trees/graphs due to recursive calls.
   - **BFS**: Consumes more memory compared to DFS as it needs to store all nodes at the current level in the queue. It may require significantly more memory for wide and shallow trees/graphs.

6. **Time Complexity**:
   - **DFS**: Generally has a lower time complexity compared to BFS, especially in cases where the solution is located deep within the search space.
   - **BFS**: Generally has a higher time complexity compared to DFS, especially in cases where the solution is located near the beginning of the search space.
# Knowledge Representation
![](../../statics/Pasted%20image%2020240310090216.png)
Knowledge representation in AI refers to the process of structuring and organizing knowledge in a form that can be effectively utilized by intelligent systems, such as expert systems, reasoning engines, and cognitive agents. It involves encoding knowledge about the world, problem-solving methods, and domain-specific expertise in a format that can be manipulated and reasoned about by computational systems.

Key aspects of knowledge representation in AI include:
- Logic:- Predicate and Propositional Logic
- Rules:- If Then
- Semantic Net:- Google Graph
- Frames:- Slots and Filler
- Script

Certainly! Let's explain each of these knowledge representation techniques:

1. **Rules**:
   - **Description**: Rules represent conditional relationships between events or states. They typically take the form of "If-Then" statements, where the "If" part specifies the condition or premise, and the "Then" part specifies the consequence or action to be taken if the condition is satisfied.
   - **Example**: If it is raining (condition), then take an umbrella (action).
   - **Usage**: Rules are used to encode procedural knowledge and inferential reasoning in expert systems, decision-making systems, and rule-based engines.

2. **Semantic Net**:
   - **Description**: Semantic nets, also known as semantic networks or concept maps, represent knowledge using nodes (representing concepts or entities) and labeled arcs (representing relationships between concepts). They provide a graphical representation of knowledge, showing how concepts are related to each other.
   - **Example**: In a semantic net about animals, nodes could represent animals (e.g., cat, dog) connected by arcs representing relationships like "is a" (e.g., "cat" is a "mammal").
   - **Usage**: Semantic nets are used for organizing and representing hierarchical and associative knowledge, facilitating semantic understanding and reasoning in various AI applications, including natural language processing, knowledge representation, and cognitive modeling.

3. **Frames**:
   - **Description**: Frames represent knowledge using a structured format consisting of slots and fillers. A frame represents a conceptual entity or object, where slots represent attributes or properties of the object, and fillers provide values or descriptions for these attributes.
   - **Example**: A frame representing a car may have slots such as "make", "model", "year", and "color", with corresponding fillers providing specific values for each slot.
   - **Usage**: Frames are used for organizing and representing structured knowledge in a domain-specific manner, enabling efficient storage, retrieval, and reasoning about objects and their attributes in AI systems. They are commonly used in expert systems, knowledge-based systems, and database management.

4. **Script**:
   - **Description**: Scripts represent stereotypical sequences of events or actions that occur in a particular context or situation. They capture common knowledge about typical scenarios, including the sequence of events, roles of participants, and expectations of outcomes.
   - **Example**: A restaurant script may include actions like "entering the restaurant", "ordering food", "eating", and "paying the bill", along with expectations of events like receiving a menu and being seated.
   - **Usage**: Scripts are used for modeling procedural knowledge and understanding complex, goal-directed behaviors in AI systems, such as natural language understanding, planning, and simulation.


## Differ b/w Propositional and predicate

| Feature             | Propositional Logic                                                                                 | Predicate Logic                                                                                                          |
| ------------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Representation      | Deals with propositions (statements) that are either true or false.                                 | Deals with predicates (relationships) and quantified statements involving variables and objects.                         |
| Expressiveness      | Less expressive, as it does not allow for quantification over variables or relations.               | More expressive, allows for quantification over variables and relations, enabling reasoning about properties of objects. |
| Variables           | Does not have variables.                                                                            | Has variables to represent objects or individuals in the domain.                                                         |
| Quantifiers         | Does not have quantifiers (e.g., ∀ for universal quantification, ∃ for existential quantification). | Includes quantifiers to express statements about all objects or some objects in the domain.                              |
| Logical Connectives | Uses logical connectives like ∧ (AND), ∨ (OR), ¬ (NOT), → (IMPLIES), ↔ (BICONDITIONAL).             | Uses the same logical connectives as propositional logic, along with quantifiers ∀ (for all) and ∃ (there exists).       |
| Example             | P ∧ Q → R                                                                                           | ∀x (Human(x) → Mortal(x))                                                                                                |
| Application         | Commonly used for basic logical reasoning, circuit design, and theorem proving.                     | Widely used in AI, knowledge representation, database querying, and formal logic reasoning systems.                      |

In summary, while propositional logic deals with simple true/false statements and logical connectives, predicate logic extends this by introducing variables, quantifiers, and predicates, allowing for more expressive representations and reasoning about relationships between objects in a domain.
### Propositional Logic
![](../../statics/Pasted%20image%2020240310081759.png)
Propositional logic, also known as sentential logic or propositional calculus, is a fundamental component of artificial intelligence (AI) and logic-based reasoning systems. Here are some key points about propositional logic in AI:

1. **Basic Elements**: Propositional logic deals with propositions, which are statements that can be either true or false. These propositions are represented using variables (p, q, r, etc.), logical connectives, and parentheses to form complex logical expressions.

2. **Logical Connectives**:
   - **AND (∧)**: Represents conjunction or logical "and". The compound proposition is true only if both operands are true.
   - **OR (∨)**: Represents disjunction or logical "or". The compound proposition is true if at least one of the operands is true.
   - **NOT (¬)**: Represents negation or logical "not". Negates the truth value of the operand.
   - **IMPLICATION (→)**: Represents material implication. The compound proposition is false only if the antecedent is true and the consequent is false.
   - **BICONDITIONAL (↔)**: Represents logical equivalence. The compound proposition is true if both operands have the same truth value.

3. **Syntax and Semantics**: Propositional logic has well-defined syntax and semantics. The syntax specifies how to form valid logical expressions, while the semantics define the meaning of these expressions in terms of truth values.

4. **Truth Tables**: Truth tables are used to enumerate all possible truth value assignments to the variables in a propositional expression and determine the truth value of the entire expression under each assignment. This technique allows for systematic evaluation of logical expressions.

5. **Inference Rules**: Propositional logic provides a set of inference rules for deriving new propositions from existing ones. Common inference rules include modus ponens, modus tollens, conjunction elimination, and disjunction introduction.

6. **Applications**:
   - Propositional logic forms the basis for knowledge representation in AI, where logical statements are used to encode facts, rules, and constraints about a domain.
   - It is widely used in automated reasoning systems, theorem proving, and formal verification to make logical deductions and prove theorems.
   - Propositional logic also serves as the foundation for more complex logical formalisms, such as first-order logic and modal logic, which extend its expressive power.

7. **Limitations**: Propositional logic has limitations in expressing quantification and dealing with complex relationships involving objects and properties. It lacks the ability to reason about variables, functions, and quantifiers, which are addressed in higher-order logics.

In summary, propositional logic is a fundamental tool in AI for representing knowledge, making logical deductions, and performing automated reasoning. Its simplicity and rigor make it well-suited for formalizing logical reasoning tasks and building intelligent systems that operate based on logical principles.

### Predicate Logic 
Predicate logic, also known as first-order logic or predicate calculus, is a formal system for representing and reasoning about relationships, properties, and quantified statements in artificial intelligence (AI) and logic-based systems. Here are some key points about predicate logic in AI:

1. **Predicates**: Predicate logic extends propositional logic by introducing predicates, which are functions that represent properties or relationships between objects in the domain. Predicates can take one or more arguments and can be true or false depending on the values of their arguments.

2. **Quantifiers**: Predicate logic introduces quantifiers to express statements about the entire domain of discourse. There are two main quantifiers:
   - **Universal Quantifier (∀)**: Denotes "for all" or "for every". It asserts that a statement holds true for all objects in the domain.
   - **Existential Quantifier (∃)**: Denotes "there exists" or "there is at least one". It asserts that a statement holds true for at least one object in the domain.

3. **Variables**: Predicate logic uses variables to represent objects or individuals in the domain. Variables can be universally quantified or existentially quantified within a logical expression.

4. **Syntax and Semantics**: Predicate logic has a well-defined syntax for constructing logical expressions using predicates, variables, quantifiers, and logical connectives. The semantics of predicate logic define the meaning of these expressions in terms of truth values over interpretations or models of the domain.

5. **Terms and Formulas**: Predicate logic distinguishes between terms, which represent objects or individuals, and formulas, which represent statements or assertions about these objects. Formulas in predicate logic can be atomic (predicates applied to terms) or compound (formed by combining atomic formulas with logical connectives and quantifiers).

6. **Inference and Deduction**: Predicate logic supports various inference rules and deduction mechanisms for deriving new logical conclusions from existing premises. Common inference rules include universal instantiation, existential instantiation, universal generalization, and existential generalization.

7. **Applications**:
   - Predicate logic is widely used in knowledge representation and reasoning tasks in AI, where it provides a rich and expressive formalism for encoding facts, rules, constraints, and relationships in a domain.
   - It serves as the basis for logical programming languages like Prolog, which use predicate logic for defining programs and querying knowledge bases.
   - Predicate logic is also used in automated theorem proving, natural language understanding, semantic web technologies, and formal verification of software and hardware systems.

8. **Expressive Power**: Predicate logic has greater expressive power than propositional logic, as it allows for the representation of complex relationships, quantification over variables, and reasoning about properties of objects and individuals in a domain.

In summary, predicate logic is a powerful formalism in AI for representing and reasoning about relationships, properties, and quantified statements in a domain. Its expressive capabilities and formal semantics make it well-suited for various knowledge-intensive tasks and logical reasoning applications.
## Resolution principle
![](../../statics/Pasted%20image%2020240310084341.png)
Resolution aims to prove the validity or satisfiability of a logical statement (conclusion) by finding a contradiction when the negation of that statement is combined with other known statements (premises). If a contradiction is derived, it implies that the original statement must be true.

### Propositional Logic Resolution
1. Convert all the propositions of F to clause form.
2. Negate P and convert the result to clause form. Add it to the set of clauses obtained in step 1.
3. Repeat until either a contradiction is found or no progress can be made:
   a. Select two clauses. Call these the parent clauses.
   b. Resolve them together. The resulting clause, called the resolvent, will be the disjunction of all of the literals of both of the parent clauses with the following exception: If there are any pairs of literals L and ¬ L such that one of the parent clauses contains L and the other contains ¬L, then select one such pair and eliminate both L and ¬ L from the resolvent.
   c. If the resolvent is the empty clause, then a contradiction has been found. If it is not, then adding it to the set of classes available to the procedure
### Unification
Unification is a fundamental concept in artificial intelligence (AI) and logic-based reasoning systems that involves finding substitutions for variables in logical expressions to make them syntactically equivalent. It is commonly used in various AI tasks, including automated theorem proving, natural language processing, and symbolic computation. Here's a note on unification and the unification algorithm in AI:

1. **Definition**: Unification is the process of finding a substitution that makes two terms or expressions syntactically identical. In other words, it seeks to find values for variables in the terms such that they become equal. For example, unifying the terms f(x, y) and f(a, b) would yield the substitution {x/a, y/b}.

2. **Unification Algorithm**:
   - **Occurs Check**: Before unifying two terms, the unification algorithm checks for occurrences of variables within each term to avoid infinite loops caused by circular dependencies. This is known as the occurs check.
   - **Most General Unifier (MGU)**: The goal of the unification algorithm is to find the most general unifier (MGU), which is the most general substitution that makes the terms syntactically equivalent. The MGU is unique if it exists.
   - **Recursive Process**: The unification algorithm proceeds recursively, considering different cases based on the structure of the terms being unified. It handles unification of atomic terms, compound terms, and variables separately, applying substitutions as necessary to make them match.
   - **Backtracking**: If the unification algorithm encounters conflicts or contradictions during the unification process, it may need to backtrack and explore alternative paths. Backtracking ensures completeness in finding the MGU.
   - **Optimizations**: Various optimizations can be applied to improve the efficiency of the unification algorithm, such as occurs check optimizations, constraint propagation techniques, and memoization.

3. **Applications in AI**:
   - **Automated Theorem Proving**: Unification is used in theorem proving systems to unify hypotheses and resolve conflicts during the proof search process.
   - **Natural Language Processing**: In natural language processing, unification is employed in parsing and semantic analysis to match syntactic structures and resolve semantic ambiguities.
   - **Symbolic Computation**: Unification is utilized in symbolic computation systems to manipulate algebraic expressions, equations, and constraints.

4. **Limitations and Challenges**:
   - **Efficiency**: The efficiency of the unification algorithm can degrade for complex terms or expressions with a large number of variables and constraints.
   - **Undecidability**: Unification is undecidable in the presence of certain constructs, such as higher-order functions or recursive types. In such cases, approximate or heuristic methods may be employed.

### Predicate Resolution
1. Convert all the statements of F to clause form.
2. Negate P and convert the result to clause form. Add it to the set of clauses obtained in 1.
3. Repeat until a contradiction found, no progress can make, or a predetermined amount of effort has expanded.
    a. Select two clauses. Call these the parent clauses.
    b. Resolve them together. The resolvent will the disjunction of all the literals of both parent clauses with appropriate substitutions performed and with the following exception: If there is one pair of literals T1 and ¬T2 such that one of the parent clauses contains T2 and the other contains T1 and if T1 and T2 are unifiable, then neither T1 nor T2 should appear in the resolvent. We call T1 and T2 Complementary literals. Use the substitution produced by the unification to create the resolvent. If there is more than one pair of complementary literals, only one pair should omit from the resolvent.
    c. If the resolvent is an empty clause, then a contradiction has found. Moreover, if it is not, then adding it to the set of classes available to the procedure.


## Declarative vs Procedural 

| Feature                | Procedural Knowledge                                  | Declarative Knowledge                              |
|------------------------|-------------------------------------------------------|---------------------------------------------------|
| Nature                 | Knowledge about how to do something.                  | Knowledge about what is true or how things are.  |
| Representation         | Typically represented as algorithms, procedures, or rules that specify a sequence of steps or actions to achieve a goal. | Represented as facts, statements, or rules that describe relationships, properties, or constraints in a domain. |
| Focus                  | Emphasizes processes, actions, and procedures for performing tasks or solving problems. | Emphasizes facts, descriptions, and relationships between entities or concepts. |
| Example                | A sorting algorithm (e.g., bubble sort, merge sort)   | A fact about the world (e.g., "The sun rises in the east.") |
| Knowledge Acquisition  | Acquired through learning by doing, experience, or instruction. | Acquired through observation, learning from examples, or formal education. |
| Usage                  | Used for guiding actions, decision-making, and problem-solving by specifying how tasks should be performed. | Used for reasoning, inference, and understanding by describing the state of the world and relationships between entities. |
| Change Management      | Typically requires modification or reprogramming of procedures or algorithms to adapt to changes or new requirements. | Often requires updating or adding new facts or rules to accommodate changes in the domain or knowledge base. |
| Execution Efficiency   | Procedural knowledge can be executed directly by a computer, often requiring less computational effort. | Declarative knowledge may require additional inference or reasoning to derive conclusions or make decisions. |
| Example AI Application | Expert systems, procedural generation algorithms, robotics control systems. | Knowledge representation, natural language understanding, semantic web technologies. |
## Logic Programming
Logic programming is a programming paradigm that is based on formal logic. It uses logical inference rules to express programs and solve problems. In logic programming, computation is performed by deriving logical conclusions from a set of logical statements (also known as rules or clauses) that define the problem domain.

The key features of logic programming include:

1. **Declarative Style**: Logic programming emphasizes a declarative programming style, where programs specify what needs to be achieved rather than how to achieve it. Programs consist of a set of logical statements that describe relationships, constraints, and rules in the problem domain.

2. **Rule-based Programming**: Logic programs are composed of rules in the form of logical clauses. These rules represent relationships between entities in the problem domain and define how new information can be inferred from existing knowledge.

3. **Logical Inference**: Computation in logic programming is driven by logical inference. Programs use logical deduction to derive new conclusions from the given set of rules and facts. The inference process applies logical resolution and unification techniques to match patterns and derive new information.

4. **Horn Clauses**: Logic programming languages typically use a subset of first-order logic known as Horn clauses. Horn clauses are logical statements with at most one positive literal and any number of negative literals. This restriction ensures that programs are computationally tractable and allows for efficient inference.

5. **Backtracking Search**: Many logic programming languages employ backtracking search algorithms to explore different branches of the logical search space and find solutions to the problem. Backtracking involves exploring alternative choices when the current path fails, allowing the program to backtrack and try different paths.

6. **Example Languages**: Prolog (Programming in Logic) is one of the most well-known logic programming languages. It provides a declarative syntax for defining logical rules and queries, along with built-in mechanisms for logical inference and backtracking search.

Logic programming is particularly well-suited for problems involving logical reasoning, constraint satisfaction, and symbolic computation. It has applications in various fields, including artificial intelligence, expert systems, natural language processing, and automated reasoning. Its declarative nature and powerful inference capabilities make it a valuable tool for solving complex problems in these domains.


## Forward vs Backward Reasoning
Here's a comparison between forward and backward reasoning presented in a table format:

| Feature        | Forward Reasoning                                                                                            | Backward Reasoning                                                                                                       |
| -------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------ |
| Definition     | Starts with known facts and uses inference rules to derive new conclusions until a goal is reached.          | Starts with a goal or hypothesis and works backward, using inference rules to determine if known facts support the goal. |
| Directionality | Proceeds from premises to conclusions.                                                                       | Proceeds from conclusions to premises.                                                                                   |
| Strategy       | Follows a top-down approach, starting with initial facts and applying inference rules to derive new facts.   | Follows a bottom-up approach, starting with the goal and using inference rules to find supporting facts.                 |
| Goal           | Typically used when the goal is known and the objective is to derive conclusions from available information. | Often used when the goal is to prove a hypothesis or satisfy a query by finding evidence or support for it.              |
| Example        | Given the premises "All humans are mortal" and "Socrates is a human", infer "Socrates is mortal".            | Given the goal "Socrates is mortal", determine if there are known facts or rules that support this conclusion.           |
| Efficiency     | May generate a large number of intermediate conclusions before reaching the desired goal.                    | More targeted and efficient, as it focuses on finding evidence directly relevant to the goal.                            |
| Applicability  | Commonly used in expert systems, decision support systems, and rule-based reasoning engines.                 | Commonly used in theorem proving, query answering, and goal-driven reasoning tasks.                                      |
| Implementation | Often implemented using forward chaining algorithms, such as the Rete algorithm in rule-based systems.       | Implemented using backward chaining algorithms, such as goal-driven search or depth-first search.                        |
| Knowledge Base | Requires a complete or partially complete knowledge base containing facts and inference rules.               | Requires access to a knowledge base or database that contains relevant information for deriving conclusions.             |
## Control Knowledge
Control knowledge in artificial intelligence (AI) refers to the knowledge or strategies used by intelligent systems to manage and regulate their problem-solving processes. It encompasses the mechanisms and heuristics employed by AI systems to determine which actions to take, when to take them, and how to allocate computational resources efficiently. Here are some key points about control knowledge in AI:

1. **Task Management**: Control knowledge guides the overall management of tasks and goals within an AI system. It involves strategies for selecting appropriate tasks to work on, prioritizing tasks based on importance or urgency, and coordinating the execution of multiple tasks concurrently.

2. **Search Strategies**: In problem-solving tasks, control knowledge governs the search strategies used to explore the solution space effectively. This includes selecting appropriate search algorithms (e.g., depth-first search, breadth-first search, heuristic search), setting search parameters (e.g., search depth, branching factor), and adapting search strategies based on problem characteristics.

3. **Heuristic Knowledge**: Control knowledge often incorporates domain-specific heuristics or rules of thumb to guide decision-making and problem-solving processes. These heuristics provide guidance on which actions to prioritize, which paths to explore first, and which solutions are likely to be more promising.

4. **Resource Allocation**: Control knowledge helps in managing computational resources efficiently, such as memory, processing power, and time. It involves strategies for allocating resources dynamically based on task requirements, system constraints, and performance considerations.

5. **Learning and Adaptation**: Control knowledge may include mechanisms for learning and adaptation, allowing AI systems to improve their performance over time through experience. This may involve techniques such as reinforcement learning, online learning, or self-adaptation to adjust control strategies based on feedback from the environment.

6. **Problem Decomposition**: Control knowledge plays a role in decomposing complex problems into simpler subproblems, organizing problem-solving processes into manageable steps, and coordinating the interaction between different components of the system.
# Unit 3
## Monotonic system in realm of logic reasoning
In logical reasoning, a monotonic system refers to a system where adding new knowledge or premises never invalidates previous conclusions. This means that once a conclusion is reached based on a set of premises, adding more premises will either strengthen that conclusion or leave it unchanged, but it will never weaken or invalidate it.
### Limitation of monotonic , it cannot work in real environment
- Information available is always incomplete
- As process goes by , situation changes , so is the solution
- Default assumption are made in order to reduce search time
### Basic Concepts of non-monotonic system 
- A non-monotonic logic system is a formal logical system where the addition of new information can lead to the retraction, revision, or qualification of previously drawn conclusions. In traditional, monotonic logic, adding new premises can only strengthen existing conclusions or leave them unchanged.
- generally default assumption and inference are made for data and knowledge.
- if rohini is bird (then default assumptions are it can fly)
#### Golden rule of default reasoning
- ![](../../statics/Pasted%20image%2020240416111031.png)
## circumscription
- If there is something that is not mentioned explicitly in problem then it should not be taken into consideration 
- meaning avoiding unnecessary details and taking into consideration only those information which are necessary. for example . ram go to bus stand on two wheeler . here unnecessary detail is two wheeler has fuel
## Probability based reasoning 
- Real world is the source of uncertanities and to tackle these , probability is the oldest technique which is useful in this scenario , but it is only good for mutually exclusive events, if events are depended on one another then something like bayes theorem is there.

### Bayes theorem 
### Reasoning using certainty factor(Important and remaining)
- Probablity based reasoning adopted bayes to handle uncertainity , but it is not always possible to calculate prior important for bayes formula
- Reasoning using certainty factors is a method used in artificial intelligence and expert systems to handle uncertain or probabilistic information. Certainty factors are numerical values that represent the degree of belief or certainty in a proposition being true or false. Here's how reasoning with certainty factors typically works:

1. **Basic Structure**:
   - Each proposition or statement is assigned a certainty factor (CF) that ranges between -1.0 (completely false) to +1.0 (completely true).
   - CF values between -1.0 and 0.0 typically represent varying degrees of disbelief or uncertainty in the truth of the proposition.
   - CF values between 0.0 and +1.0 represent varying degrees of belief or certainty in the truth of the proposition.

2. **Combining Certainty Factors**:
   - When combining multiple pieces of evidence or propositions, the overall certainty factor of a conclusion is computed using rules for combining certainty factors. Common rules include:
     - **Min rule (or conjunction rule)**: This rule combines the CFs of independent pieces of evidence supporting the same conclusion.
     - **Product rule**: This rule is used when combining CFs for related evidence. It's especially useful when there's dependency or overlap between evidence.

3. **Inference**:
   - Certainty factors are used to infer conclusions from known facts and evidence. Inference involves combining CFs according to specific rules to compute the CF of the conclusion.

4. **Example**:
   - Let's say we want to determine if it's going to rain tomorrow based on various sources of evidence:
     - Weather forecast says there's a 70% chance of rain (CF = +0.7).
     - Historical data suggests that April usually has rainy days (CF = +0.4).
   - Using the product rule, we can combine these CFs:
     - Overall CF for "It will rain tomorrow" = CF(forecast) × CF(historical data) = 0.7 × 0.4 = +0.28.
   - Therefore, we conclude with a certainty factor of +0.28, indicating moderate belief that it will rain tomorrow.

6. **Limitations**:
   - Certainty factors rely on the assumption of independence and linearity, which may not hold in all cases.
   - Handling complex relationships between evidence can be challenging, especially when dealing with non-linear dependencies or indirect evidence.
#### Measures of belief
![](../../statics/Pasted%20image%2020240417151532.png)
#### Measure of disbelief
![](../../statics/Pasted%20image%2020240417151622.png)


![](../../statics/Pasted%20image%2020240417151724.png)
![](../../statics/Pasted%20image%2020240417151809.png)
![](../../statics/Pasted%20image%2020240417152123.png)
## Fuzzy based reasoning
### Why need 
- Boolean nature of probablity theory
- Assumption of probablity theory that real numbers are always correct

![](../../statics/Pasted%20image%2020240417153032.png)
### Some brief
1. **Handling Uncertainty**: Fuzzy logic is employed in AI to handle uncertainty and imprecision in data and decision-making. Unlike traditional logic, which deals with binary true/false values, fuzzy logic allows for the representation of degrees of truth. This is particularly useful in situations where concepts are vague or ambiguous.

2. **Fuzzy Sets and Membership Functions**: Fuzzy logic relies on fuzzy sets, where elements have degrees of membership ranging from 0 to 1. Membership functions define how elements are assigned membership degrees based on their characteristics. These functions can be triangular, trapezoidal, Gaussian, or other shapes, depending on the nature of the problem.

3. **Fuzzy Rules**: In fuzzy logic systems, rules are expressed in the form of "if-then" statements, where the conditions and conclusions can be fuzzy propositions. For example, "If the temperature is cold and the humidity is high, then increase the heating." These rules capture the fuzzy relationships between inputs and outputs.

4. **Fuzzy Inference**: Fuzzy inference is the process of deriving crisp decisions or actions from fuzzy inputs and rules. It involves fuzzification (converting crisp inputs to fuzzy sets), applying fuzzy rules to these fuzzy inputs, and then defuzzification (converting fuzzy outputs back to crisp values). Various inference methods like Mamdani and Sugeno are used for this purpose.

5. **Applications**: Fuzzy logic finds applications in various AI domains, including control systems, pattern recognition, decision-making, expert systems, and natural language processing. It is particularly useful in situations where precise mathematical models are difficult to formulate due to uncertainty or complexity.

6. **Advantages**: Fuzzy logic allows for the modeling of human-like reasoning, where decisions are made based on vague or incomplete information. It provides a flexible framework for handling real-world problems that are inherently fuzzy in nature. Additionally, fuzzy systems can be easier to understand and interpret compared to traditional mathematical models.

7. **Challenges**: Despite its advantages, fuzzy logic also poses challenges, such as the selection and tuning of membership functions and rules, as well as computational complexity, especially in systems with large numbers of variables and rules. Additionally, interpreting and explaining fuzzy logic-based decisions to users can sometimes be challenging.

### Fuzzy set
A fuzzy set is a mathematical concept that generalizes the idea of a classical set by allowing elements to have degrees of membership rather than just being either in the set or not. In a classical set, an element either belongs to the set (membership degree of 1) or does not belong to the set (membership degree of 0). 

In contrast, in a fuzzy set, each element has a membership degree that indicates the degree to which the element belongs to the set. Membership degrees range between 0 and 1, where 0 indicates no membership (completely outside the set) and 1 indicates full membership (completely inside the set). Membership degrees between 0 and 1 represent varying degrees of partial membership or uncertainty.

Imagine we have a set representing "tallness" in humans. In a classical set, we might define the set of tall people as those whose height is greater than 6 feet. So, someone who is exactly 6 feet tall would not be considered tall, and someone who is 6 feet and 1 inch tall would be considered tall.

Now, let's convert this classical set into a fuzzy set to account for degrees of tallness. Instead of defining tallness as a binary condition (either tall or not tall), we assign membership degrees to individuals based on how tall they are.

For example:

- Person A: 5 feet 10 inches tall
  - Membership degree in the set of tall people: 0.2
  - Interpretation: Person A is somewhat tall, but not very tall.

- Person B: 6 feet tall
  - Membership degree in the set of tall people: 0.7
  - Interpretation: Person B is fairly tall.

- Person C: 6 feet 5 inches tall
  - Membership degree in the set of tall people: 0.9
  - Interpretation: Person C is very tall.

- Person D: 5 feet 5 inches tall
  - Membership degree in the set of tall people: 0.1
  - Interpretation: Person D is not very tall.

In this fuzzy set representation, individuals can have varying degrees of membership in the set of tall people, reflecting the fact that tallness is not a binary attribute but exists on a continuum. This allows us to capture the nuances and uncertainties associated with defining concepts like "tallness" more accurately.

### Fuzzy operations
![](../../statics/Pasted%20image%2020240417154017.png)
### Bayesian network
![](../../statics/Pasted%20image%2020240417154505.png)

# UNIT 4 
## Planning 
Planning in artificial intelligence is about decision-making actions performed by robots or computer programs to achieve a specific goal.

Execution of the plan is about choosing a sequence of tasks with a high probability of accomplishing a specific task.
We require domain description, task specification, and goal description for any planning system. A plan is considered a sequence of actions, and each action has its preconditions that must be satisfied before it can act and some effects that can be positive or negative
![](../../statics/Pasted%20image%2020240417155409.png)
- FSSP:-  given an initial state S in any domain, we perform some necessary actions and obtain a new state S' (which also contains some new terms), called a progression. It continues until we reach the target position. Action should be taken in this matter.
- BSSP:-  we move from the target state g to the sub-goal g, tracing the previous action to achieve that goal. This process is called regression (going back to the previous goal or sub-goal). These sub-goals should also be checked for consistency. The action should be relevant in this case.
- 