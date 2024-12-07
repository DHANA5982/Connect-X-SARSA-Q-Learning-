## Introduction
This project involves using the Kaggle Environment to play Connect X, also known as Connect 4. The default grid size is 6x7 with a requirement of 4 in a row to determine the winner. The environment supports multiple players. A 4x5 grid and a 3-in-a-row rule were used for this project, with two players competing. The objective is to place a player's mark three times in a row vertically, horizontally, or diagonally to win. The game was played against two default agents: 'random' (easy) and 'negamax' (hard).

## Environment Setup
- Grid size: 4x5
- Win condition: 3 in a row
- Players: Two
- Opponents: 'random' and 'negamax'

## Working Style of Environment and Default Agent
The ConnectX environment places pieces vertically, while indices are counted row-wise. This setup makes the game challenging against the 'negamax' player, which uses the mini-max algorithm based on the principle that one player's gain is another player's loss.

## Possible Actions
Strategies to approach the game include:
1. Focusing on placing pieces 3 in a row rather than blocking the opponent, especially as the first player.
2. Placing pieces in the same column if it's not full, then using nearby columns to create more winning opportunities.
3. Using random actions.
4. Using learned policies.

## Learning Policies
Three methods were used to update policies:
1. Randomly generated actions.
2. SARSA-derived policy.
3. Q-Learning-derived policy.

Learning policies from the opponent's ('negamax') actions for each observation proved to be the best strategy. Initial attempts to create policies using random actions with SARSA and Q-Learning methods were only effective against the 'random' agent. Tracking and interpreting the opponent's actions require a logical approach and effective policy update techniques, which proved time-consuming due to the 60-second limit per move.

## Methodology

### RandomAgent
- **Act Function**: Uses random actions unless a condition (epsilon) is met, then switches to learned policy.
- **Learn Function**: Stores randomly generated actions for each observation to update the policy.
- **Performance**: Moderately effective against 'random', not effective against 'negamax'.

### SARSA Agent
- **Act Function**: Uses random actions unless a condition (epsilon) is met, then switches to learned policy.
- **Learn Function**: Updates observation and action values using the SARSA policy update method.
- **Performance**: Moderately effective against 'random', not effective against 'negamax'.

### Q-Learning Agent
- **Act Function**: Uses random actions unless a condition (epsilon) is met, then switches to learned policy.
- **Learn Function**: Updates observation and action values using the Q-Learning policy update method.
- **Performance**: Moderately effective against 'random', not effective against 'negamax'.

## Chosen Algorithm
All three algorithms (RandomAgent2, SARSA, Q-Learning) are considered for further development. The ConnectX environment differs significantly from simpler environments like the frozen lake, making it challenging to observe and track the second player's moves. The sequential use of actions is crucial, and current limitations include the inability to pass desired actions in sequence.

## Conclusion
This project provided valuable insights into the ConnectX environment and the challenges of developing effective agents. Despite some progress, time constraints limited the full implementation of the desired changes. Future work involves refining these agents to play at an intermediate level against 'negamax'. Although the reward increased over time against 'random', the learning rate was insufficient to beat 'negamax'. Further improvements and a deeper understanding of the environment are necessary for better performance.

Thank you for your attention.
