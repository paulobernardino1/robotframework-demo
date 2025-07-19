====================================================
Web testing with Robot Framework and SeleniumLibrary
====================================================

`Robot Framework`_ is a generic open source test automation framework and
SeleniumLibrary_ is one of the many test libraries that can be utilized with
it. Besides demonstrating how they can be employed together for web testing,
this demo presents the basic Robot Framework test data syntax, how tests
are executed, and how logs and reports appear.

.. contents:: **Table of Contents:**
   :depth: 1
   :local:

Obtaining demo package
======================

To acquire the demo, you can either `download`_ the repository from GitHub or checkout
the `source code`_ directly. As a result you get ``WebDemo`` directory with
``demoapp`` and ``login_tests`` sub directories.

Sample `test cases`_ and `generated results`_ are available also online.
There is thus no need to obtain the demo if you are not interested in
`executing it`__ yourself.

__ `executing demo`_

Demo application
================

The demo application is a very simple login page displayed below. With
user name ``demo`` and password ``mode`` you reach a welcome page, and
otherwise you end up at an error page. How to launch and terminate the
application yourself is explained in the `Launching demo application`_
section.

.. figure:: demoapp.png

Test cases
==========

Test case files as well as a resource file utilized by them are situated in
the ``login_tests`` directory. Click file names below to view the latest versions
online.

`valid_login.robot`_
    A test suite with a single test for valid login.

    This test has a workflow that is constructed using keywords in
    the imported resource file.

`invalid_login.robot`_
    A test suite containing tests related to invalid login.

    These tests are data-driven by their nature. They employ a single
    keyword, specified with the ``Test Template`` setting, that is invoked
    with different arguments to cover different scenarios.

    This suite also demonstrates utilizing setups and teardowns in
    different levels.

`gherkin_login.robot`_
    A test suite with a single Gherkin style test.

    This test is functionally identical to the example in the
    `valid_login.robot`_ file.

`resource.robot`_
    A resource file with reusable keywords and variables.

    The system specific keywords created here form our own
    domain specific language. They utilize keywords provided
    by the imported SeleniumLibrary_.

See `Robot Framework User Guide`_ for more details about the test data syntax.

Generated results
=================

After `executing tests`_ you will obtain report and log in HTML format. Sample
files are also visible online in case you are not interested in executing
the demo yourself:

- `report.html`_
- `log.html`_

Executing demo
==============

Prerequisites
-------------

A prerequisite for executing the tests is having `Robot Framework`_ and
SeleniumLibrary_ installed, and they in turn require
Python_. Robot Framework `installation instructions`__ cover both
Robot and Python installations, and SeleniumLibrary has its own
`installation instructions`__.

In practice it is easiest to install Robot Framework and
SeleniumLibrary along with its dependencies utilizing `pip`_ package
manager. Once you have pip installed, all you need to do is executing
these commands::

    pip install -r requirements.txt

__ https://github.com/robotframework/robotframework/blob/master/INSTALL.rst
__ https://github.com/robotframework/SeleniumLibrary#installation

Launching demo application
--------------------------

Executing tests requires the `demo application`_ situated under ``demoapp``
directory to be active.  It can be launched either by double clicking
``demoapp/server.py`` file in a file manager or by executing it from the
command line::

    python demoapp/server.py

After the demo application is launched, it will be available at URL
http://localhost:7272. You can test it manually, valid credentials are
``demo/mode``, and it needs to be active while executing the automated
tests.

If the application was launched by double-clicking ``demoapp/server.py``
file, it can be terminated by closing the opened window. If it was
executed from the command line, utilizing ``Ctrl-C`` is sufficient.

Executing tests
---------------

The `test cases`_ are situated in the ``login_tests`` directory. They can be
executed utilizing the ``robot`` command::

    robot login_tests

.. note:: If you are utilizing Robot Framework 2.9 or earlier, you need to
          employ the ``pybot`` command instead.

You can also execute an individual test case file and employ various command line
options supported by Robot Framework::

    robot login_tests/valid_login.robot
    robot --test InvalidUserName --loglevel DEBUG login_tests

Execute ``robot --help`` for more information about the command line usage and see
`Robot Framework User Guide`_ for more details about test execution in general.

Employing different browsers
----------------------------

The browser that is utilized is controlled by ``${BROWSER}`` variable defined in
`resource.robot`_ resource file. Firefox browser is employed by default, but that
can be easily overridden from the command line::

    robot --variable BROWSER:Chrome login_tests
    robot --variable BROWSER:IE login_tests

Consult SeleniumLibrary_ documentation about supported browsers.

.. _Robot Framework: http://robotframework.org
.. _SeleniumLibrary: https://github.com/robotframework/SeleniumLibrary
.. _Python: http://python.org
.. _pip: http://pip-installer.org
.. _download: https://github.com/robotframework/WebDemo/archive/master.zip
.. _source code: https://github.com/robotframework/WebDemo.git
.. _valid_login.robot: https://github.com/robotframework/WebDemo/blob/master/login_tests/valid_login.robot
.. _invalid_login.robot: https://github.com/robotframework/WebDemo/blob/master/login_tests/invalid_login.robot
.. _gherkin_login.robot: https://github.com/robotframework/WebDemo/blob/master/login_tests/gherkin_login.robot
.. _resource.robot: https://github.com/robotframework/WebDemo/blob/master/login_tests/resource.robot
.. _report.html: http://robotframework.org/WebDemo/report.html
.. _log.html: http://robotframework.org/WebDemo/log.html
.. _Robot Framework User Guide: http://robotframework.org/robotframework/#user-guide