# bvpTune
Machine learning based library for tuning the numerical settings of bvp4c solver from MATLAB.

This library can be used to find the optimal numerical settings of the
bv4c, a boundary value problem solver from MATLAB based on the type of the problem.
The library uses machine learning regression model that maps the numerical settings to
solver performance criteria for faster predictions. This model s then used to optimize the settings 
using the optuna library.

The functions provide by the library are listed as folows:

 ### 1)  getOptimalGridPoints(test_case_type):
      returns the optimal number of grid points for the specified test_case_type of the boundary value problem.
      
 ### 2)  getOptimalODEevals(test_case_type)
      returns the optimal number of ode evaluations for the specified test_case_type of the boundary value problem.
      
 ### 3)  getOptimalResiduum(test_case_type)
      returns the optimal residuum for the specified test_case_type of the boundary value problem.
 
 ### 4)  getOptimalODEevalsAndGridPoints(test_case_type)
      returns parato front numerical settings as a dataframe that optimizes the ode evaluations and the grid points 
      for the specified test_case_type of the boundary value problem.
 
 ### 5)  getOptimalGridPointsAndResiduum(test_case_type)
      returns parato front numerical settings as a dataframe that optimizes the grid points and the residuum
      for the specified test_case_type of the boundary value problem.
   
 ### 6)  getOptimalResiduumAndODEevals(test_case_type)
      returns parato front numerical settings as a dataframe that optimizes the residuun and the ode evaluations 
      for the specified test_case_type of the boundary value problem.
   
 ### 7)  getOptimizedSettings(test_case_type)
      returns parato front numerical settings as a dataframe that optimizes the ode evaluations, grid points, and the residuum
      for the specified test_case_type of the boundary value problem
   
 ### 8)  getSolvabiltyStatus(test_case_type, max_grid_points, newton_critical_tolerance, newton_armijo_probes, newton_max_iterations, newton_tolerance,                          add_factor, remove_factor, use_collocation_scaling)
       returns whether the specified numerical setting is solvable or not for the specified test_case_type of 
       the boundary value problem.
   
 ### 9)  getSolverPerformance(test_case_type, max_grid_points, newton_critical_tolerance, newton_armijo_probes, newton_max_iterations, newton_tolerance,                        add_factor,remove_factor, use_collocation_scaling)
       returns the solver statistics of specified numerical setting for the specified test_case_type of the boundary value problem.
       
### 10)  visualize(dataframe)
        visualize the 2d/3d pareto front plots for the provided dataframe returned by the optimization functions.
        
        
**Reference Boundary Value Problems**

| test_case_type | Refrence Problem Number | Problem Type
| ----------- | ----------- |----------- |
|1|1|Linear|
|2|3|Linear|
|3|4|Linear|
|4|7|Linear|
|5|19|Non-linear|
|6|20|Non-linear|
|7|22|Non-linear|
|8|23|Non-linear|
|9|24|Non-linear|
|10|33|Non-linear|

The reference problems are selected from [[1]](#1).

## References
<a id="1">[1]</a> 
Soetaert, Karline and Cash, Jeff and Mazzia, Francesca. (2010). 
Package bvpSolve, solving testproblems.
