Market Simulation with Discrete Markov Chain
This Mathematica script simulates a market dynamic using a discrete Markov chain to model the interactions between buyers and sellers. It particularly focuses on the effect of opportunistic sellers on the buyers' perception of product quality.

Parameters
•	a = 0.4: Critical perception rate, the threshold below which buyers are reluctant to purchase high-quality products.
•	timeSteps = 1000: The total number of steps in the simulation, representing time or interactions in the market.
•	betaStart = 1: Initial perception rate, indicating perfect and symmetric information.
•	opportunisticRate = 0.02: Represents the 2% of the seller population that is opportunistic and may deceive the buyers.
•	movingAverageWindow = 100: The window size for the moving average used to smooth the frequency of high-quality product transactions over time.

Process
The simulation starts with an initial perception rate (beta) of 1. At each time step:
1.	beta may decrease by 0.1 if the buyer encounters an opportunistic seller, but not below the critical perception rate a.
2.	The market state transitions based on the current beta, with the probabilities defined in the transition matrix.
3.	The simulation records whether the market is in a High-quality (H) or Low-quality (L) state.

Behavior Modeling
simulateMarketBehavior[betaInitial_]: This function runs the market simulation with a given initial beta, tracking the market state over time and adjusting beta based on encounters with opportunistic sellers. It uses a moving average to smooth the transition frequencies of high-quality product states.

Visualization
The script generates 50 individual simulation runs and aggregates them into a single plot. This plot displays the evolving frequency of high-quality product transactions over time, smoothed with a moving average. Additionally, an "Initial Expectation" line shows the theoretical frequency of high-quality transactions based on the initial beta.

Output
•	frequencyHPlots: A plot of the frequency of high-quality product transactions over time for each simulation run.
•	initialExpPlot: A plot showing the initial expectation of high-quality product frequency.
The final display combines these plots, providing a comprehensive view of how market perceptions evolve, particularly under the influence of opportunistic seller behavior.
