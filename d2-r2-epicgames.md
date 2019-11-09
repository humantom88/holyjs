# The Art of Explicit and Consistent User Interfaces (Epic Games)
@farzad_yz
---
- implicit vs explicit state
- finite state vs infinite state
- logic

---
renderer (state) = view
---

One purpose, Multiple approaches
---

State management tools are containers
- deak wuth the architecture
- tell you how to store states
- tel you how to update states (mutable, immutable, observable)

1972 Smalltalk event-driven GUI 

event + action paradigm

MS Calculator  
implicitly handling the state

For Impossible States you should
- write tests
- add guards to avoid impossible states^ avoid mutually exclusive behaviors from happening simultaneously

Cyclomatic complexity of code grows faster than UX complexity

## Solution
- thinking about states explicitly
- discovering finite states
- conditional rendering based on finite state

Elements have finite states

Statecharts (David HAREL 1987) (a visual formalism for complex systems)*
- Extends fsm model
- stateswith relations
- several places to run side effects
- several types ofs side effects
- state + event => nextState + effect

Solution - XState <https://xstate.js.org>

Statecharts visualize logic
- generate directed graph
- showvase state paths
- QA
- Cross-complete tasks
- onboarding
- statechart visualization in PR

Recap:
- New Modeling Layer
- Levels solution complexity and problem complexity

Think in states!
===