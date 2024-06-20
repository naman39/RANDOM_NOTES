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
