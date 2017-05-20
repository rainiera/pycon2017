## Introduction to Reinforcement Learning

speaker: Jessica Forde  
time: Saturday 1:40 pm - 2:25 pm  
[description](https://us.pycon.org/2017/schedule/presentation/708/) 
[code](https://github.com/jzf2101/intro_rl)

**Intro**

- Machine learning for policies

**Mathematical definition of regret**

- Regret: opportunity loss for not following optimal policy

- Exploration vs. Exploitation
    - Need to understand reward for each state
    - Need to get best policy

**Bandit Problems**

- Compared to A/B testing/RCT/statistical testing
- Difference boils down to exploration vs. exploitation divide

- Epsilon-Greedy algorithms
- Explore tradeoffs between reward

- Markov Decision Process
    - Way for us to understand out actions change the environment
    - Transitions have probabilities
    - Can be solved using dynamic programming

**Dynamic Programming in RL**

- "If you know what will happen tomorrow, you can plan accurately today"
- State
- Action
- Reward
- Transition - a probability distribution
- Discount factor
- Goal is to optimize over a value function
    - Q
    - V

Markov Decision Process Example

- DP requires the transition probabilities between states to be known
- What if you can't do dynamic programming?
- SARSA: State, Action, Reward, State, Action
- SARSA is both model-free and on-policy

Tabular RL Problems

- Lookup table representation
- Easy to store and interpret
- Fast at test time


[cartpole](https://openai.com/requests-for-research/#cartpole)
[parlai code](https://github.com/facebookresearch/ParlAI)
[parlai](https://code.facebook.com/posts/266433647155520/parlai-a-new-software-platform-for-dialog-research/)

**Can you solve your problem with RL?"**

- Tips
    - Parametr setting matters
    - Evaluate results across multiple runs

**Resources**

- Sutton and Barto
- Mnih et al., 2015
- UC Berkeley CS 188

