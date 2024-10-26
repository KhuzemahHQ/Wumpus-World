# Wumpus-World
Code for a Simple Reflex Agent and Model-Based Agent to solve a simplified variant of the Wumpus World Problem.

![wumpus world](https://github.com/user-attachments/assets/e32e6b94-87d1-4fc4-9204-88d289bbd548)

The agent starts with an initial cash amount of $5000. If the agent falls into a pit at some point, it can pay $1000 to exit and return to the room it previously came from and continue its search for the Gold. As an example, consider the following scenario:
The agent is initially at (1,1). It decides to move to the LEFT (to 1,0). After making this move, the agent falls into a pit. If the agent has money available, it can pay this “fine” of $1000 and exit the pit to return to the room at (1,1) and continue its journey. Otherwise, the agent dies, and it is game over.
In the Jupyter notebook, the starter code creates a random world (i.e., S, G and X are spawned randomly) on the grid. Now, since the world is randomly generated, there may be a few instances that are unsolvable (such as the ones below):

![unsolvable](https://github.com/user-attachments/assets/623ee7ac-871c-46d0-9c9b-906619de3df2)



1) Simple Reflex Agent:
Simple Reflex Agent
The Simple Reflex Agent operates solely on immediate perceptions, without any memory or model of the world. It chooses directions at each cell to move left, right, up, or down, and only reacts based on the current room’s state. If it falls into a pit, it returns to the last visited room without learning its location, and continues exploration with no adjustments for future decisions.

To prevent indefinite exploration in unsolvable grids, a time limit of 45 seconds is enforced. If the agent fails to reach the gold within this time, it stops and returns "unsolvable". In a solvable world, the agent will eventually reach the gold and return "Gold Found!".

2) Model-Based Agent
The Model-Based Agent constructs a world model as it navigates, recording each room's state (e.g., safe, pit, gold). Starting from an empty map, the agent updates its model with each room visited. If it encounters a pit, it pays a penalty and returns to the previous room, marking the pit location in its model to avoid it in future moves.

The agent aims to reach the gold with a minimum balance of $2000 by limiting pit penalties. If the gold is unreachable within 45 seconds after the entire world (minus the gold room) is explored, the agent concludes that the problem is "unsolvable" and outputs its final model state. In solvable cases, the agent reaches the gold and returns "Gold Found! x dollars left in the bank too!", where x represents the remaining funds.

