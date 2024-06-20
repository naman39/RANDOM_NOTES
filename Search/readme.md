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

**Stack:** Last in first out data type

## DEPTH-FIRST SEARCH
Search algorithm that always expands the deepest node in the frontier

## BREADTH-FIRST SEARCH
Search algorithm that always expands the shallowest node in the frontier
