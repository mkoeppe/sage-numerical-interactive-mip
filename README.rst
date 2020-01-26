=====================================================================================
 sage-numerical-interactive-mip: Interactive mixed integer linear programming solver
=====================================================================================

.. image:: https://github.com/mkoeppe/sage-numerical-interactive-mip/workflows/Build%20and%20test%20Python%20package/badge.svg
   :alt: [Build and test Python package]
   :target: https://github.com/mkoeppe/sage-numerical-interactive-mip/actions/

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
``InteractiveLinearProgram`` and its dictionaries”).  The present
package should run on any recent release of SageMath.

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

This needs a working SageMath; install, for example, from conda-forge as
described in http://doc.sagemath.org/html/en/installation/conda.html

The code comes with extensive documentation and tests; see the
docstrings in the modules.

How to run the testsuite and build the HTML documentation
=========================================================

Install ``tox``, make sure that ``sage`` is accessible in your ``PATH``
and then run ``tox``.

This also builds the documentation in ``.tox/docs/tmp/html/index.html``.
