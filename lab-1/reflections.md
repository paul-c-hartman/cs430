# Names: Paul, Jenessy
# Lab: lab1 (Intelligent Agents)
# Date: 1/12/26

1. The difference between the agent's percept and the environment is that the agent doesn’t actually store information on whether the location is clean. The environment stores the state of the location. 

2. There is a performance variable that will go up by ten points every time the agent cleans a location (moving to another location costs a point). Ideally, the agent would want to get as many points with taking as little steps as possible but there is no actual incentive for the agent to get points (ex. nothing happens if there is 0 points for performance). 

3. No the agent does not need memory in this environment. In this example, the agent only acts according to the current location it is on. It does not need to know the statuses of other locations. 

4. It is rational in the way that if the agent senses that the location is clean already, it won’t suck but there is not much rational regarding where the agent will move. It is just left or right depending on its current location. The environment is so small that the agent is able to maximize its performance every time. 

5. Due to the rule structure, the agent would not be able to move beyond two locations since the rules basically tell it to go right and left. If we were to add more locations, we would have to rework how the agent decides where to move next. 

6. The instructions seem to force the agent to take one left and one right. If there are more locations besides A and B, the agent will never be able to visit them and the program will never be able to determine the environment as all clean. 

7. The agent behaves rationally, as it just keeps retrying suck until the location is clean. This can be done easily as there is no penalty for retrying. 

8. Perhaps if there was a penalty for retrying, limit the amount of retries per square before moving on to the next square. This would prevent the agent from wasting resources on a problem that cannot be solved by retrying. For this, we would have to add a counter mechanism. 

9. The performance scores were the same for both environments. However, the number of steps the agent took varied within the stochastic environment; sometimes it took more due to the retries. 

10. This agent is different from the reflex agent because it maintains info regarding the state of the environment, like location and cleanliness status. These statuses are updated and checked as the agent performs its tasks. 

11. The agent needs to know the status of the other location in order to move left or right, otherwise it will not be able to move. However, the agent will perform one suck at most on its default starting area before considering all locations clean. It will probably not get the task done right, but the agent will not get stuck infinitely. 

12. As long as the model hasn’t run Action.NOOP already, finishing its program, the model will have to check the other locations’ statuses first and therefore, the agent will react accordingly. 

13. Having an explicit goal allows the agent to make different choices in response to alternative scenarios such as the one given in the question. Where a reflex agent would only keep trying to follow a blocked path, a goal-based agent can try to move around it.

14. The goal is what the agent intends to do, and the plan is how the agent intends to do it. On a different grid, a rational agent with the same goal would have a different plan. The same goal--different implementation.

15. The agent couldn't adapt, since it would need to update its plan to fit the new goal.

16. The utility function encodes the agent's preferences as a number. Higher number, more preferred. In this case that's 10 * clean tiles - number of moves made. If the values were changed, the agent's preferences would change. For example, in the current configuration the agent values a clean tile as worth at least 9 moves made; if you changed the penalty for movement to 4, the agent would value a clean tiles as worth only 2 moves made.

17. A utility-based agent is generally better than a goal-based one when the agent has to weigh different objectives/measurements of the environment. The numbers in its utility function encode its weight of these objectives.

18. The utility function could have a penalty for time elapsed. The simplest version of this would be to subtract 1 from its value per time step: (10 * clean tiles) - number of moves - time elapsed in steps.

19. Almost all of them did except for the goal-based agent. It sometimes achieves the same performance and sometimes has worse performance. This is because the goal-based agent takes random actions sometimes, which can cause suboptimal actions.

20. The highest-performing agent is only the best choice when the measure of performance accurately describes what you want. If it isn't the best choice for a certain situation, the performance measure is inaccurate.

21. It isn't justified, as evidenced by the fact that almost all of the agents--including the reflex agent--achieve maximum performance. It would be justified in a more complex environment--large, non-deterministic, and/or partially observable.