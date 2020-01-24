# MATLAB tool for multi-objective optimization (genetic or brute-force)

This **MATLAB** tool offers different functionalities for multi-objective optimization:
* Offer a **common interface** for different solvers
    * **Brute force** grid search (exhaustive search)
    * MATLAB **single-objective genetic** algoritm ('ga')
    * MATLAB **multi-objective genetic** algoritm ('gamultiobj')
* Offer an **abstraction layer** to the MATLAB solver
    * Scaling the input variables
    * Generating and filtering initial points
    * Transforming high-level datastructures ('struct') to low-level ('matrix')
    * Generating the low-level inputs required by the solvers
* Allow **vectorized and parallel** evaluation of the functions
    * Divide the number of points to be evaluated into chunks
    * Evaluate the chunks with parallel computing ('parfor')
    * The points inside a chunk are evaluated in a vectorized way

Mathematically, the following optimization problem are solved:
* Multiple variables
* Integer variables
* Upper and lower bounds
* Inequality constraints
* Equality constraints
* Non continuous objective function
* Single-objective or multi-objective goals

Look at the example [run_example.m](run_example.m) which generates the following results:

<p float="middle">
    <img src="readme_img/input.png" width="400">
    <img src="readme_img/output.png" width="400">
</p>

## Adding Solvers

The code is made to take advantage of optimization methods using vectorized evaluation of the objective function.
Therefore, it would be easy to add support for 'patternsearch', 'particleswarm', or 'paretosearch'.
Adding support for non vectorized solvers ('fmincon', 'fminbnd', or 'fminsearch') is possible but less interesting.

## Compatibility

* Tested with MATLAB R2018b.
* Required the gads_toolbox (for contour detection).
* Required the optimization_toolbox (for contour simplification).
* Compatibility with GNU Octave not tested but probably problematic.

## Author

**Thomas Guillod** - [GitHub Profile](https://github.com/otvam)

## License

This project is licensed under the **BSD License**, see [LICENSE.md](LICENSE.md).
