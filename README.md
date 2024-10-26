# Wumpus-World
Code for a Simple Reflex Agent and Model-Based Agent to solve a simplified variant of the Wumpus World Problem.

![wumpus world](https://github.com/user-attachments/assets/e32e6b94-87d1-4fc4-9204-88d289bbd548)

The agent starts with an initial cash amount of $5000. If the agent falls into a pit at some point, it can pay $1000 to exit and return to the room it previously came from and continue its search for the Gold. As an example, consider the following scenario:
The agent is initially at (1,1). It decides to move to the LEFT (to 1,0). After making this move, the agent falls into a pit. If the agent has money available, it can pay this “fine” of $1000 and exit the pit to return to the room at (1,1) and continue its journey. Otherwise, the agent dies, and it is game over.
In the Jupyter notebook, the starter code creates a random world (i.e., S, G and X are spawned randomly) on the grid. Now, since the world is randomly generated, there may be a few instances that are unsolvable (such as the ones below):

![unsolvable](https://github.com/user-attachments/assets/623ee7ac-871c-46d0-9c9b-906619de3df2)

