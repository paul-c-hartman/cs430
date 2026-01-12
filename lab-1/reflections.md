# Names: Paul, Jenessy
# Lab: lab1 (Intelligent Agents)
# Date: 1/12/26

1 - 12

13. Having an explicit goal allows the agent to make different choices in response to alternative scenarios such as the one given in the question. Where a reflex agent would only keep trying to follow a blocked path, a goal-based agent can try to move around it.

14. The goal is what the agent intends to do, and the plan is how the agent intends to do it. On a different grid, a rational agent with the same goal would have a different plan. The same goal--different implementation.

15. The agent couldn't adapt, since it would need to update its plan to fit the new goal.

16. The utility function encodes the agent's preferences as a number. Higher number, more preferred. In this case that's 10 * clean tiles - number of moves made. If the values were changed, the agent's preferences would change. For example, in the current configuration the agent values a clean tile as worth at least 9 moves made; if you changed the penalty for movement to 4, the agent would value a clean tiles as worth only 2 moves made.

17. A utility-based agent is generally better than a goal-based one when the agent has to weigh different objectives/measurements of the environment. The numbers in its utility function encode its weight of these objectives.

18. The utility function could have a penalty for time elapsed. The simplest version of this would be to subtract 1 from its value per time step: (10 * clean tiles) - number of moves - time elapsed in steps.

19. Almost all of them did except for the goal-based agent. It sometimes achieves the same performance and sometimes has worse performance. This is because the goal-based agent takes random actions sometimes, which can cause suboptimal actions.

20. The highest-performing agent is only the best choice when the measure of performance accurately describes what you want. If it isn't the best choice for a certain situation, the performance measure is inaccurate.

21. It isn't justified, as evidenced by the fact that almost all of the agents--including the reflex agent--achieve maximum performance. It would be justified in a more complex environment--large, non-deterministic, and/or partially observable.