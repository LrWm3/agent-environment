# Architecture

An overview of the agent environment architecture.

## Overview

We don't really have a real architecture but here are some goals I can think of.

Before I go into the details, lets review some key terminology. As I have not read anything on this subject at this 
point, all of this is likely to be incorrect usage of terminology.

### Environment

An environment describes the context in which the agents operate. Agents themselves are also part of the environment. 
The state of the environment influences the outcomes of actions performed by agents.

### Actions

An action is something an agent can do. Any action carries both a cost in time and agent resources. Performing no action 
also costs both time and agent resources.

Each time interval, the action being performed consumes a portion of the required energy.

Ultimately, actions alter the state of the environment. Whether an action can be canceled, undone, or restarted
depends on how the action interacts with the environment as it is being performed.

### Agents

Agents are actors within environments which can perform actions. There are two types of state associated with an Agent;
the environmental state and agent state.

#### Agent Environmental State

The environmental state associated with an agent are the actual values corresponding to the agents' state. This would 
include things such as agent energy, age, lifespan, position within the environment and actions the agent can perform.

Under certain conditions, environmental factors will cause agents to transition between agent states. As an example,
an agent at the end of its lifespan will die.

> Initially, only basic agent state transitions will be supported.

#### Agent Memories

The agent state associated could also be described as the agents' memory. Agent memory contains information the agent
previously observed traversing an environment. Agent memory also contains information intrinsically known to agents 
about themselves, such as their energy.

> Initially, no limit on the memory of agents will be placed; agents will not need to be selective in what they recall.

#### Agent Information Exchange

In addition to acquiring information by traversing an environment, and agent can also acquire environmental memories by
requesting information from other agents in their immediate areas. Alternatively, agents may choose to offer up
information to other nearby agents without any request to do so.

The requesting or providing of agent memories between agents is known as information exchange. There are two types of
information exchange an agent can perform with another agent; subject-based and open-ended. 

As an example of subject-based communication; an agent may communicate to other nearby agents that it is low on energy. 
Nearby agents may share a memory of a location of an energy source to the agent. These are examples of subject-based
communication.

Open-ended communication is when an agent makes a request for other nearby agent memories. In this case, it is up to
nearby agents if they should respond, and what information to provide in their response.

Agents may also respond to information by changing what actions they take.

> Initially, only subject based information exchange will be supported.

Information exchange can be individual, partially-broadcast or fully-broadcast.

> Initially, only broadcast information exchange will be supported between agents.

The environment influences the amount of information agents may exchange within a given area. Information exchange 
within a certain area is limited up to a threshold. Once this threshold is reached, agents may not communicate in the 
area until the information has expired.

Requesting information of other agents and providing information to other agents are both actions. Receiving information
from other agents may be an action as well.

> Initially, receiving information may be free for agents to do. It depends I guess.
