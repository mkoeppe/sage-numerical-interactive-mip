# sage-numerical-interactive-mip: Interactive mixed integer linear programming solver

Written by Peijun Xiao 2015-2016 at UC Davis for integration into SageMath.

Parts of Peijun's work (improvements to `sage.numerical.interactive_simplex_method`) have been integrated into SageMath in various tickets, see meta-ticket https://trac.sagemath.org/ticket/20302 ("Interactions with `InteractiveLinearProgram` and its dictionaries").

The interactive MILP solver in this repository is based on commit 5a4e3508d95e95e4491efcb2cf16fbe25be60bec, dated August 24, 2016, from the SageMath tree https://github.com/pgxiao/sage.git; this work superseded an earlier effort (adding integer variables in `interactive_simplex_method`) at https://trac.sagemath.org/ticket/18805

It was rebased in January 2020 onto SageMath version 9.1.beta1, and then filtered using `git filter-repo` to the single file `sage_numerical_interactive_mip/interactive_milp_problem.py`.

## How to use

This needs a working SageMath; install, for example, from conda-forge as describede in http://doc.sagemath.org/html/en/installation/conda.html

The code comes with extensive documentation and tests; see the docstrings in the file.

## How to run the testsuite

Install `tox`, make sure that `sage` is accessible in your `PATH` and then run `tox`.
