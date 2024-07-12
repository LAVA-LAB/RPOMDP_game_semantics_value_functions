# README

The files in this repository can be used to simulate the value functions of the RPOMDPs used in the appendix of the paper ***Imprecise Probabilities Meet Partial Observability:  Game Semantics for Robust POMDPs*** (https://arxiv.org/abs/2405.04941) to show that uncertainty assumptions influence the optimal value and policies for finite horizon reward maximization in RPOMDPs.

The .ggb files can be loaded in the 3D calculator of GeoGebra. The file names consist of three parts seperated by underscores:
- The number of the subappendix where the model is discussed for which this file contains the value function.
- The uncertainty assumption used:
	- full = full stickiness
	- obs = observation-based stickiness
	- zero = zero stickiness
	- af = agent first order of play
	- nf = nature first order of play
- The player for which this file optimizes the policy.

In general, each file consists of **v** and **w** functions with two input parameters and a couple of extra parameters. The **v** function shows the value function with the optimal policy for the player that we are optimizing for. The **w** function shows the same function, but has slider parameters with which one can try out different policy values. In case of independence between parts of the value function, these parts are given as separate functions and either indicated with the history they correspond to, or simply by a numerical indicator to link the parameters.

The parameter names in the agent files are approximately based on the following conventions:
- **l** and **d** represent the probabilities assigned to choice **a** by an history with the light (**l**) or dark (**d**) gray observation.
- **w** represents the probability assigned to choice **a** by an agent policy with a history of only the first state in the first, small order of play example (D3).
- **w1** and **w2** represent the probabilities assigned to choice **a** by an agent policy with a history of only the first (**w1**) or both (**w2**) states in the second, bigger order of play example (D4).
The parameter names in the nature files are approximately based on the following conventions:
- **p** and **q** represent the probabilities assigned to **p** and **q** by a full stickiness nature policy.
- **l** and **d** indicate that the **p** or **q** choice corresponds to a history with the light (l) or dark (d) gray observation.
- **a** and **b** indicate that this choice corresponds to a history with the **a** or **b** action as last-played agent action.
- **r** and **s** represent the same as **p** and **q**, but are used as inputs for the try-out value function w.

In the second stickiness example (D2), we need to consider mixed nature policies. In the nature files for those value function we did not provide a try-out function, but instead used multiple **w** functions for values of different deterministic nature policies. The **v** function forms a probability distribution over the **w** functions, hence forming a mixed nature policy.

Apart form the **v** and **w** functions, each files also has one or more **h** functions which draw a plane at the height of the optimal value. These **h** functions are consistent between the agent and nature files of the same problem and assumption combinations. In an agent file, the agent policy is optimal if the entire **v** function lies above the **h** plane, as this demonstrates that nature cannot reach a value below this value. Vice versa, in a nature file, the nature policy is optimal if the entire **v** function lies below the **h** plane.
In many cases, **v** functions coincide entirely with the **h** planes.

In case of questions, please reach out to eline.bovy@ru.nl.
