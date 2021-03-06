.. NodePy documentation master file, created by
   sphinx-quickstart on Mon Mar  9 20:46:17 2009.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

.. contents::

================
Overview
================
NodePy (Numerical ODEs in Python) is a Python package for designing,
analyzing, and testing numerical methods for initial value ODEs.
Its development was motivated by my own research in time integration
methods for PDEs.  I found that I was frequently repeating tasks that
could be automated and integrated.  Initially I developed a collection
of MATLAB scripts, but this became unwieldy due to the large number
of files that were necessary and the more limited capability for
code reuse.  

NodePy represents an object-oriented approach, in which the basic
object is a numerical ODE solver.  The idea is to design a laboratory for
such methods in the same sense that MATLAB is a laboratory for matrices.
Some distinctive design goals are:

  * **Plug-and-play**: any method can be applied to any problem using the
    same syntax.  Also, properties of different kinds of methods are 
    available through the same syntax.  This makes it easy to compare 
    different methods.
  * **Abstract representations**: Generally, the most abstract
    (hence powerful) representaton of an object is used whenever
    possible.  Thus, order conditions are generated using products
    on rooted trees (or other recursions) rather than being hard-coded.
  * **Floating-point representation**: Most quantities, such as coefficients
    of integration methods, are represented with double-precision numbers.
    This means also that, for the most part, properties of methods that
    are in truth exact (discretely-valued) are determined by numerical
    calculations, using appropriate tolerances.  Thus the "order" of
    a method is determined by checking whether the order conditions are
    satisfied to within a small value (near machine-epsilon).
    Of course, for some purposes an exact representation of rational
    coefficients and exact computation of method properties would
    be preferable.  However, since such an approach would be less
    generally applicable, this is planned as future work.

In general, user-friendliness of the interface and readability of
the code are prioritized over performance.

NodePy includes capabilities for applying the methods to solve
systems of ODEs.  This is mainly intended for testing and comparison;
for realistic problems of interest in most fields, time-stepping in
Python will be too slow.  One way around this is to wrap Fortran or
C functions representing the right-hand-side of the ODE, and we are
looking into this.

.. note:: The user guide is currently quite incomplete,
          and in general is not expected to keep pace with
          all NodePy development.  However, NodePy includes
          substantial inline documentation within the various
          modules, and you are encouraged to look there.

Dependencies
================================
NodePy has recently begun to support exact computation of
some properties, for which it relies on the sympy package.
Due to some recent changes in sympy, it is necessary to use version
0.6.7 (rather than the latest sympy version).

Classes of Numerical ODE Solvers
================================

NodePy includes classes for the following types of methods:
    - :ref:`Runge-Kutta Methods <create_rkm>`
    - :ref:`Linear Multistep Methods <create_lmm>`
    - :ref:`Two-step Runge-Kutta Methods <create_tsrkm>`


Analysis of Methods
===================

NodePy includes functions for analyzing many properties, including:
    - Stability:
        - Absolute stability (e.g., plot the region of absolute stability)
        - Strong stability preservation
    - Accuracy
        - Order of accuracy
        - Error coefficients
        - Generation of Python and MATLAB code for checking order conditions


Testing Methods
======================

NodePy includes implementation of the actual time-stepping algorithms
for the various classes of methods.  A wide range of 
:ref:`initial value ODEs <ivp>` can be loaded, including the DETEST suite of problems.
Arbitrary initial value problems
can be instantiated and solved simply by calling a method with the
initial value problem as argument.  For methods with error estimates,
adaptive time-stepping can be used based on a specified error tolerance.
NodePy also includes automated functions for convergence testing.

In the future, NodePy will also support solving semi-discretizations
of initial boundary value PDEs.


NodePy Manual
==================================

.. toctree::
   :maxdepth: 2

   quickstart
   methods
   solving
   stability
   rooted_trees
   future
   about
   bib

Modules Reference
===================

.. toctree::

    modules/runge_kutta_method
    modules/rooted_trees
    modules/linear_multistep_method
    modules/low_storage_rk

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
