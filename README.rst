=====================================================================================
 sage-numerical-interactive-mip: Interactive mixed integer linear programming solver
=====================================================================================

.. image:: https://github.com/passagemath/sage-numerical-interactive-mip/workflows/Build%20and%20test%20Python%20package/badge.svg
   :alt: [Build and test Python package]
   :target: https://github.com/passagemath/sage-numerical-interactive-mip/actions/

.. image:: https://readthedocs.org/projects/sage-numerical-interactive-mip/badge/?version=latest
   :alt: [Documentation]
   :target: https://sage-numerical-interactive-mip.readthedocs.io/en/latest/

.. image:: https://zenodo.org/badge/DOI/10.5281/zenodo.3627400.svg
   :target: https://doi.org/10.5281/zenodo.3627400

.. intro

This package is an extension of SageMath's mixed integer linear programming
facilities described at
http://doc.sagemath.org/html/en/reference/numerical/index.html

It was written by Peijun Xiao, Zeyi Wang, and Yuan Zhou in 2015-2016 at UC Davis
for integration into SageMath.

Parts of their work (improvements to
``sage.numerical.interactive_simplex_method`` and MIP backend methods)
that required changes to existing SageMath modules have already been
integrated into SageMath in various tickets, see meta-ticket
https://trac.sagemath.org/ticket/20302 (“Interactions with
``InteractiveLinearProgram`` and its dictionaries”).

The module ``sage_numerical_interactive_mip.interactive_milp_problem``,
written by Peijun Xiao, provides the interactive MILP problem classes,
MILP tableau classes, and the cutting plane method. It is based on
commit 5a4e3508d95e95e4491efcb2cf16fbe25be60bec, dated August 24, 2016,
from the SageMath tree https://github.com/pgxiao/cutting-plane-method; 
this work superseded an earlier effort (adding integer variables in
``interactive_simplex_method``) at
https://trac.sagemath.org/ticket/18805

The modules ``sage_numerical_interactive_mip.clean_dictionary`` and
``sage_numerical_interactive_mip.backends.*_backend_dictionary``,
written by Zeyi (Aedi) Wang, provide a textbook view on a simplex basis
in a numerical solver. They are based on
https://trac.sagemath.org/ticket/18804

The branches were rebased by Matthias Koeppe in January 2020 onto
SageMath version 9.1.beta1, then filtered using ``git filter-repo`` and
merged.

How to use
==========

This package uses the modularized distributions of portions of the Sage library
provided by the `passagemath <https://github.com/passagemath/>`_ project.
No installation of SageMath is required.
Just install the package with ``pip`` and start using it::

  $ pip install sage-numerical-interactive-mip

  $ ipython

  In [1]: from sage_numerical_interactive_mip import *

  In [2]: A = ([1, 1], [3, 1])

  In [3]: b = (1000, 1500)

  In [4]: c = (10, 5)

  In [5]: P = InteractiveMILPProblem(A, b, c, ["C", "B"], variable_type=">=", integer_variables=True)

  In [6]: P

The code comes with extensive
`documentation <https://sage-numerical-interactive-mip.readthedocs.io/en/latest/>`_
and tests; see the docstrings in the modules.

How to run the testsuite and build the HTML documentation
=========================================================

Install ``tox`` with ``pip``, then run ``tox``.

This also builds the documentation in ``.tox/docs/tmp/html/index.html``.
