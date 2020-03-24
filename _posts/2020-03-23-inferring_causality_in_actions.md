# Inferring Causality in Actions of Cooperative Agents

{% include alert.html text="This post is in progress" %}

1. TOC
{:toc}

## Motivation

Comparisons of different algorithmic approaches to multi-agent systems often use reward metrics to quantify performances. For cooperative tasks, an algorithm is said to learn cooperative behavior if it achieves high rewards pursuing these tasks. The quantification of the influence of individual agents' actions on the actions of other agents of a team is rarely used as a metric. However, many algorithmic approaches to cooperative tasks use the mutual conditioning of individual actions on the actions of other agents in a team. Therefore we propose an approach to inferring causality in agents' actions and evaluate it in various games using an independent learner and a joint action learner. The games are designed to require cooperation at different levels, while the strength of the compared algorithms is either cooperation or independence.

## Related Work

## Background

### Dec-POMDP
    @book{oliehoek_concise_nodate,
      title={A concise introduction to decentralized {POMDPs}},
      author={Oliehoek, Frans A and Amato, Christopher and others},
      volume={1},
      year={2016},
      publisher={Springer}
    }

- **Dec-POMDP:** $$G = \langle A, S, U, \mathbb{T}, O, \mathbb{O}, R, h, \gamma \rangle$$.
- **Agents:** $$A = \{1,\dots,n\}$$
- **Global State:** $$s \in S$$  
- **Individual Action:** $$u^a_t \in U$$ (at each time step $$t$$, each agent $$a \in A$$) 
- **Joint Action:** All agents of a team form the joint action $$\mathbf{u} \in \mathbf{U} \equiv U^n$$. 
- **Transition probability function:** $$\mathbb{T}$$ that specifies $$P(s_{t+1} \mid s_t, \mathbf{u}):S \times \mathbf{U} \times S \rightarrow [0, 1]$$ (accorting to $$\mathbb{T}$$, the environment transitions into the next state $$s_{t+1}$$)
- **Individual observation:** For each state $$s_t$$, each agent $$a$$ receives an observation $$o^a_t \in O$$ according to the observation function.
- **Observation function:** $$\mathbb{O}(s,a):S \times A \rightarrow O$$
- **Reward function:** $$R(s, \mathbf{u}):S \times \mathbf{U} \rightarrow \mathbb{R}$$ is a reward function, shared among all agents. 
- **Horizon:** $$h$$ is the horizon, specifying the number of time steps during which the agent will interact with the environment before it terminates.
- **Discount factor**: $$\gamma \in [\,0,1)\,$$ is a discount factor.
- **Deterministic policy:** Each agent conditions a deterministic policy $$\pi^a: \overline{O}^a \rightarrow U$$ on its observation history $$\overline{o}^a_t = (o^a_0,\dots,o^a_t)$$.

### RJAL
        @article{article,
        author = {Posor, Jorrit and Belzner, Lenz and Knapp, Alexander},
        year = {2020},
        month = {01},
        pages = {79-84},
        title = {Joint Action Learning for Multi-Agent Cooperation using Recurrent Reinforcement Learning},
        volume = {4},
        journal = {Digitale Welt},
        doi = {10.1007/s42354-019-0239-y}
        }
        
- **The input sequence:** At each time step $$t$$, the input sequence contains $$n$$ elements. For agent $$a \in A$$, $$(o^a_t, f^a_t)$$ is an element of the input sequence.
- **Spatial individual observation:** $$o^a_t$$ is the spatial individual observation.
- **Non-spatial individual features:** $$f^a_t = (u^a_{t-1}, r^a_{t-1}, a, p^a_t, Q^{a-1}_t)$$ where $$u^a_{t-1}$$ and $$r^a_{t-1}$$ denote the last action and last reward, respectively. $$a$$ is the agent ID and $$p^a$$ is the relative position. $$Q^{a-1}_t$$ denotes the Q-values calculated for agent $$a-1$$.

## Central Idea

## Experimental Setup

## Results 

## Conclusion
