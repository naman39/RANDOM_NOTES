# Search

**1. Agents:** It is an entity that perceives its environment and acts upon that environment. (Car, person, AI)

**2. State:** A configuration of the agent and its environment
<img width="837" alt="Screenshot 2024-06-19 at 10 20 55 PM" src="https://github.com/naman39/CS50/assets/59209974/e9887c62-d753-44e5-a14d-f22b4e789130">

## Search Problems contain

**Initial State:** A state where agent begins

**Actions:** Choices that can be made in a state

Actions(s) returns the set of actions that can be executed in state s.

**Transition model:** A description of what state results from performing any applicable action in any state. 

Result(s,a) returns the state resulting from performing action a in state s

**State Space:** the set of all states reachable from the initial state by any sequence of actions.

**Goal Test:** Some way to test if a given state is a goal state.

**Path Cost:** Numerical cost associated with the given path.

**Solution:** A sequence of actions that leads from the initial state to the goal state.

**Optimal Solution:** Solution which has the lowest path cost of all the solutions.

## Node

A data structure that keeps track of
* a state
* a parent( a node that generated this node)
* an action ( action applied to parent to get to this node)
* a path cost( from initial state to node)

## Approach

We are going to look at the frontier(queue) and ask ourselves is this the goal if not remove it and expand the node. If it is we found the solution.

### Revised Approach

Start with a frontier(queue) that contains the initial state.
Start with an empty explored set
Repeat:
  If the frontier is empty no solution
  Remove a node from the frontier
  If node contains goal state, return the solution
  Add node to the explored set
  Expand node and add resulting nodes to the frontier if they arent already in the frontier or the explored set.
  
## UNINFORMED SEARCH

Search strategy that uses no problem-specific knowledge

### DEPTH-FIRST SEARCH
Search algorithm that always expands the deepest node in the frontier

**Stack:** Last in first out data type

### BREADTH-FIRST SEARCH
Search algorithm that always expands the shallowest node in the frontier

**queue:** first in first out data type

## INFORMED SEARCH

Search strategy that uses problem-specific knowledge to find solutions more efficiently.

### GREEDY BEST-FIRST SEARCH

Search algorithm that expands the node that is closest to the goal, as estimated by a heuristic function h(n).

### A* SEARCH 

Search algorithm that expands node with the lowest value of g(n) + h(n).
g(n) = cost to reach node
h(n) = estimated cost to goal

**A- Search is optimal if:**
- h(n) is admissible (never overestimates the true cost), and
- h(n) is consistent (for every node n and successor n' with step cost c, h(n) <= h(n') + c)


## MINMAX 
MAX(X) aims to maximize the score
MIN(O) aims to minimize the score

Given a state s:
  * MAX picks action a in ACTIONS(s) that produces highest value of MIN-VALUE(RESULTS(s,a))
  * MIN picks action a in ACTIONS(s) that produces smallest value of MAX-VALUE(RESULTS(s,a))

```function MAX-VALUE(state):
  if terminal(state):
    return utility(state)
  v = -infinity
  for action in ACTIONS(state):
    v = MAX(v, MIN-VALUE(RESULT(state, action)))
  return v```

```function MIN-VALUE(state):
  if terminal(state):
    return utility(state)
  v = infinity
  for action in ACTIONS(state):
    v = MIN(v, MAX-VALUE(RESULT(state, action)))
  return v```

## GAME

* So: Initial State
* Player(s): returns which player to move in state(s)
* Actions(s): returns legal moves in state s
* Result(s,a): returns state after action a is taken
* Terminal(s): checks if state s is a terminal state
* Utility(s): final numerical value for terminal state s

## OPTIMIZATIONS

ALPHA-BETA PRUNING REMOVING UNNECSARY CALCULATIONS

###DEPTH LIMITED MINIMAX

ONLY CONSIDER TO THE NEXT FOUR MOVES

###EVALUATION FUNCTION

FUNCTION THAT ESTIMATES THE EXPECTED UTILITY OF THE GAME FROM A GIVEN STATE
