# Inferring Causality in Actions of Cooperative Agent

Comparisons of different algorithmic approaches to multi-agent systems often use reward metrics to quantify performances. For cooperative tasks, an algorithm is said to learn cooperative behavior if it achieves high rewards pursuing these tasks. The quantification of the influence of individual agents' actions on the actions of other agents of a team is rarely used as a metric. However, many algorithmic approaches to cooperative tasks use the mutual conditioning of individual actions on the actions of other agents in a team. Therefore we propose an approach to inferring causality in agents' actions and evaluate it in various games using an independent learner and a joint action learner. The games are designed to require cooperation at different levels, while the strength of the compared algorithms is either cooperation or independence.

1. TOC
{:toc}

## Motivation

## Related Work

## Background

- **Dec-POMDP:** $$G = \langle A, S, U, \mathbb{T}, O, \mathbb{O}, R, h, \gamma \rangle$$.
- **Agents:** $$A = \{1,\dots,n\}$$
- **Global State:** $$s \in S$$  
- **Individual Action:** $$u^a_t \in U$$ (at each time step $$t$$, each agent $$a \in A$$) 
- **Joint Action:** All agents of a team form the joint action $\mathbf{u} \in \mathbf{U} \equiv U^n$. 
- **Transition probability function:** $\mathbb{T}$ that specifies $P(s_{t+1}|s_t, \mathbf{u}):S \times \mathbf{U} \times S \rightarrow [0, 1]$ (accorting to $\mathbb{T}$, the environment transitions into the next state $s_{t+1}$)
- **Individual observation:** For each state $s_t$, each agent $a$ receives an observation $o^a_t \in O$ according to the observation function.
- **Observation function:** $\mathbb{O}(s,a):S \times A \rightarrow O$
- **Reward function:** $R(s, \mathbf{u}):S \times \mathbf{U} \rightarrow \mathbb{R}$ is a reward function, shared among all agents. 
- **Horizon:** $h$ is the horizon, specifying the number of time steps during which the agent will interact with the environment before it terminates.
- **Discount factor**: $\gamma \in [\,0,1)\,$ is a discount factor.
- **Deterministic policy:** Each agent conditions a deterministic policy $\pi^a: \overline{O}^a \rightarrow U$ on its observation history $\overline{o}^a_t = (o^a_0,\dots,o^a_t)$.

## Central Idea

## Experimental Setup

## Results 

## Conclusion
