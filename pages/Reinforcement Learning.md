alias:: RL

- [[Markov Decision Process]] is a mathematical formulation to describe an ideal environment in RL.
	- > The full MDP can be defined by a 6-tuple $\cal{M} = (\cal{S}, \cal{A}, T, d_0, r, \gamma)$, where $\cal{S}$ denotes the state space, $\cal{A}$ denotes the action space, $T(s_{t+1} | s_t, a_t)$ denotes the state transition distribution, $r(s_t, a_t)$ denotes the reward function, and $\gamma \in (0,1]$ the discount factor.
	- The objective is to find a policy $\pi(a_t | s_t)$, which denotes the probability of taking action $a_t$ conditioned on the current state $s_t$.