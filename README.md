<picture>
 <source media="(prefers-color-scheme: dark)" srcset="[YOUR-DARKMODE-IMAGE](https://i.ytimg.com/vi/og_reuAtIXc/maxresdefault.jpg)">
 <source media="(prefers-color-scheme: light)" srcset="[YOUR-LIGHTMODE-IMAGE](https://i.ytimg.com/vi/og_reuAtIXc/maxresdefault.jpg)">
 <img alt="YOUR-ALT-TEXT" src="YOUR-DEFAULT-IMAGE">
</picture>



# A-Star-Ambulances-Pacients
Heuristic informed search algorithm: what is the traversal for an ambulance in a city to pick up the most patients on a single ride and take them to the hospital?

Python Version: 3.8+

Execution:
If you want to execute all test maps and heuristics then run the ASTAR-calls.sh script: bash ASTAR-calls.sh 
bash 

Input:
Tiles -

• Cell marked with a N: Address of patient without infectious diseases.
• Cell marked with a C: Address of a patient with infectious diseases.
• Cell marked with a CC: Care center of patients with infectious diseases.
• Cell marked with a CN: Care center of patients without infectious diseases.
• Cell marked with a P: Location of the parking.
• Cell marked with a number (1, 2, 3...): time (energy cost) to travel through that location. The time/cost
necessary to move through cells without value (N, C, CC, CN or P) will be one unit.
• Cell marked with a X: non-traversable positions.


Rules: 
#The vehicle is electric therefore the costs tile represents energy. We optimize with respect to energy cost.

• It must leave the parking and end there. It can pick up, without exceeding the vehicle’s capacity, as many
patients as necessary in a single trip to take them to their respective care centers.

• The vehicle has 10 seats in total, with 2 of them specially enabled for contagious patients. Noncontagious patients may also use these two seats as long as contagious patients are not transported on the
same trip at any time.

• The vehicle has 50 units of energy at maximum load. Use as many energy units as indicated in each cell
on the map (as mentioned above) and, if a charge of 50 units is not enough to make all the necessary trips,
you must go through the parking to recharge. This recharge action is immediate and has no additional
cost.

• Contagious patients are the last to be picked up from their home and the first to be dropped off at their
respective care centers on each journey in which they intervene.

• Whenever the vehicle passes by a patient’s home, and the conditions allow for pick-up, the patient will
board the vehicle.

• The vehicle can only move either horizontally or vertically to adjacent cells.


Grid of nxm 

Example:

N;1;1;1;1;1;
1;C;P;1;X;X;
1;1;X;2;CN;1;
1;1;X;2;CC;1;
1;1;X;2;2;2;


Output: Path traversal
