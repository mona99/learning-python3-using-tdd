=======================
How organize repository
=======================

Description
===========
Your code source must be organized, to be easier to:
- maintain,
- learned from new users,
- test and found problems

This article will help you to work with repositories well organized, and with
some methology to be more efficient.

Minimal structure
=================

::

    |--- my_script.py [1]
    |--- my_module/ [2]
    |    |--- __init__.py [3]
    |--- README.rst
    |--- requirements.txt
    |--- requirements_dev.txt
    |--- tests/
    |    |--- __init__.py

.. [1] Can be used if your project will contains only one code file
.. [2] Must be used instead [1] if your project will contains many code files
.. [3] This file must used to indicate python files in folders and help it to resole structure

Code management
---------------
If your project has a single code file, it can be on the root project folder,
else, create a dedicated folder for your code, commonly named using the project
name.

Dependencies management
-----------------------
These files are only used to manage **Python** dependencies, not system one.

Take a look on the `requirements files format`_ to learn how write them.

requirements.txt
^^^^^^^^^^^^^^^^
This file contains your mandatory dependencies for your project to work.

You can reference Pypi_ [4] dependencies, git repositories, ...

You will install dependencies using **pip** software.

.. code:: bash

    $ pip install -r requirements_dev.txt

.. _`requirements files format`: https://pip.pypa.io/en/stable/reference/pip_install/#requirements-file-format
.. _Pypi: https://pypi.python.org
.. [4] Repository for Python modules

requirements_dev.txt
^^^^^^^^^^^^^^^^^^^^
Same as *requirement.txt* but for development dependencies, which are not
mandatory to run your code but needed during your development step:
- linter (ex: pylint)
- test management (ex: pytest)
- documentation management (ex: sphinx)
- \.\.\.

This file import also the *requirements.txt* to have also mandatory dependencies
installed.

README.rst
----------
This is the file used to describe your project and how used it other users.

Explain:
- project goals,
- how install it,
- how configure it,
- all interesting informations for users
- \.\.\.

You write it using the ReStructuredText_ syntax.
You can find cheatsheets on Internet to help you, `this one`_ is a good start

.. _ReStructuredText: http://docutils.sourceforge.net/rst.html
.. _`this one`: https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst

Tests folder
------------
All your tests will be inside **tests** directory.

Use explicit name and prefix them by *test_*. A good pratice is to have the
same names (plus *test_* prefix for files) than your code.

Example::

    ...
    |--- my_program
    |    |--- _init__.py
    |    |--- foobar
    |    |    |--- __init__.py
    |    |    |--- foo.py
    |    |    |--- bar.py
    |    |--- my_program.py
    ...
    |--- tests
    |    |--- my_program
    |    |    |--- _init__.py
    |    |    |--- foobar
    |    |    |    |--- __init__.py
    |    |    |    |--- test_foo.py
    |    |    |    |--- test_bar.py
    |    |    |--- test_my_program.py
    ...

Exercises
=========

- No code is needed for these exercises
- Use the dev dependencies examples

Easy
-----
Create a repository structure for a single code file project, named
"basic_repo_easy", without dependency. This project will do some strings
formating.

Medium
------
Create a repository structure for a project which will have many code files.
The project name is "basic_repo_medium", with these code subfolders:
- square
- circle

This project will calculate square or circle areas.

Hard
----
Create a repository structure for a project which will have many code files.
The project name is "hard_repo_medium", with these code subfolders:
- git
- git/github
- git/gitlab

This project will be able to get Git repositories informations from Gitlab and
Github.

It'll have a production dependency named "requests"
