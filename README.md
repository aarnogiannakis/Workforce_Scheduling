## Problem Description

*This problem is inspired by the 2023 exam for the course 42112 Mathematical Programming Modelling, taught by Professors Thomas Jacob Riis Stidsen and Richard Martin Lusby in DTU.*

You are responsible for organizing the staff schedule at a busy call center that operates 24/7. The demand for operators varies throughout the day, with certain hours being busier than others. Your task is to assign operators to shifts in a way that ensures sufficient coverage at all times while minimizing the associated costs. The shifts can be either long (8 hours) or short (3 hours).

Multiple operators can be assigned to each shift, and according to the union rules, shifts can only start at the beginning of an hour (e.g., midnight, 1 AM, 2 AM, etc.). For the 8-hour shifts, a one-hour meal break is mandatory, which must occur either after four hours or five hours of work. The 3-hour shifts do not require a break.

Your goal is to determine the optimal set of shifts and the number of operators for each shift, including the specific timing of meal breaks for the 8-hour shifts. It is not necessary for all 8-hour shifts to follow the same break schedule. The company has a limit of 165 employees that can be scheduled over a 24-hour period. The shifts you schedule must meet the known hourly demand throughout the day, which is denoted as `d_t` for hour `t` where `t ∈ {1, 2, 3, ..., 24}`. Shifts that extend past midnight should also cover early morning hours. For example, an 8-hour shift starting at 11 PM will meet the demand until 7 AM. To keep the schedule manageable, the company prefers to use no more than 12 shifts.

Each shift `s` incurs a cost of `c_s` DKK per operator, along with a fixed administrative fee of `f` DKK for initiating any shift, regardless of the number of shifts or operators. The parameter `Cover_st` can be used in your model, where `Cover_st = 1` if shift `s` covers hour `t`, and `Cover_st = 0` otherwise. The details of this parameter are provided in "question9-parameter.jl".
