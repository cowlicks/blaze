====================
Adding a New Backend
====================

This is document is for developers who want to add a new "backend" to blaze.


The workhorse of blaze computations on a given backend are the ``compute_up``
functions. At each node of the expression tree, ``compute_up(expr, data)``
where ``expr`` is the expression and ``data`` is the data.

Internally blaze uses "multipledispatch" to find the ``compute_up`` for given
data. Your job in adding a new backend is to register enough ``compute_up``
functions with the right signatures to make your backend useful.
