.. launcher-menus documentation master file, created by
   sphinx-quickstart on Tue Jan 12 12:55:43 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to launcher-menus' documentation!
=========================================

.. toctree::
   :maxdepth: 2
   :caption: Contents:


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`


Description
===========

Launcher menu wrapper.

Provides an API for launcher menus such as:

  - `dmenu <https://tools.suckless.org/dmenu/>`__
  - `bemenu <https://github.com/Cloudef/bemenu>`__

Can be extended to other menus:

  - Create its <menu>.yml config file from template.yml OR
  - Supply flags through ``**flags`` to ``menu`` function.

Documentation
=============

.. image:: https://readthedocs.org/projects/launcher-menus/badge/?version=latest
   :target: https://launcher-menus.readthedocs.io/?badge=latest
            :alt: Documentation Status

Installation
============

pip
---

Preferred method ``pip install -U launcher-menus``

`pspman <https://github.com/pradyparanjpe/pspman>`__
----------------------------------------------------

For automated management: pre-release updates, etc
``pspman -s -i https://github.com/pradyparanjpe/launcher-menus.git``

Uninstallation
==============

.. _pip-1:

pip
---

``pip uninstall -y launcher-menus``

.. _pspman-1:

pspman
------

Remove installation ``pip uninstall -y launcher-menus``

Remove repository clone ``pspman -s -d launcher-menus``

Usage
=====

Call menu
---------

-  Call menu launchers [dmenu, bemenu, <others>] from python
-  Import in your script

.. code:: python

   from launcher_menus import menu as bemenu
   user_letter = bemenu(command='bemenu', opts=['a', 'b', 'c', 'd'])
   if user_letter is not None:
       # user did not hit <Esc>
       print(user_letter)

Results:

::

   a

What does it do
---------------

-  Runs a subprocess for the selected menu and returns its standard
   output or ``None``

Configuration
=============

-  <menu>.yml files bear flags corresponding to actions for <menu>
-  <menu>.yml files are located in
   ``<installation path>/site-packages/launcher_menus/``\ `menu-cfgs <launcher_menus/menu-cfgs>`__

Configuration format
--------------------

-  Copy `template <launcher_menus/menu-cfgs/template.yml>`__ to
   `menu-cfgs <launcher_menus/menu-cfgs>`__\ ``/<menu.yml>``
-  Edit fields to provide flags:
-  Example:

::

   bottom: -b
   prompt: --prompt

template.yml
~~~~~~~~~~~~

.. code:: yaml

   version:
   bottom:
   grab:
   ignorecase:
   wrap:
   ifne:
   nooverlap:
   lines:
   monitor:
   height:
   prompt:
   prefix:
   index:
   scrollbar:
   font:
   title background:
   title foreground:
   normal background:
   normal foreground:
   filter background:
   filter foreground:
   high background:
   high foreground:
   scroll background:
   scroll foreground:
   selected background:
   selected foreground:
   windowid:

TODO
====

-  Configure rofi
-  Configure wofi (dead project?)
-  Configure others as issues arise



methods
=======

menu
------

.. autofunction:: launcher_menus.menu

check_installations
-------------------

.. autofunction:: launcher_menus.check_installations

Errors
------
.. automodule:: launcher_menus.errors
   :members:
