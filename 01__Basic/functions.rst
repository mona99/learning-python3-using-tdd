====================
How to use functions
====================

Description
===========

Functions are a way to organize code, create a scope to isolate variables, ...

They can return a result, return nothing or do nothing.

    If you use Pytest to manage your test suit, tests will be inside functions

How create a function
=====================

This is done with the keyword *def*, a name and optional parameters.
All the content of a function must be indented.

Example 1 - Without parameter
-----------------------------

.. code:: python

    def example():
        """
        This function, called *example*, print the "Foobar" string
        """

        print('Foobar')


Example 2 - With a required parameter
-------------------------------------

.. code:: python

    def example(message):
        """
        This function, called *example*, print the received parameter
        """

        print('Parameter: {}'.format(message))


Example 2 - With an optional parameter
--------------------------------------

.. code:: python

    def example(message='Hello world'):
        """
        This function, called *example*, print the received parameter, or
        "Hello world" if called without parameter
        """

        print('Parameter: {}'.format(message))
