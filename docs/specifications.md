Environment
- 2D grid
- Resources are objects can be placed on the grid and have specific properties w.r.t. how agents may interact with them. Resources are not necessarily statically located, agents may have the option to move them on the grid.
- A "nest" is some area on the grid that can have special properties w.r.t. how agents my interact when occupying this area
- An "obstacle" is some area on the grid that can have properties w.r.t. how agents may interact with that area (e.g. can't move there, move slower there, some probability of danger for agents that are present there.
- Ordinary grid locations. Agents may traverse them, agents can place resources or communication signals upon them (pheromones). May have some properties associated with them such as how long a pheromone is allowed to last on them. Resource objects may also be placed on them.


Agent
- Contains a set of actions. Actions allow for dynamics between the agent and the environment.
- Internal store of resources, such as the abstract concept of "energy". Energy (or potentially other resources) is consumed over time or by using certain actions and can only be replenished by resources from the environment. 
- An agent is characterized by its set of actions and its capacity to contain resources. From an RL perspective, only the actions are a part of the agent and things like an energy level are viewed as part of the environment as the agent can only interact with them via an action. From the coding perspective however, I think it makes sense for these to be viewed as a property of the agent.
