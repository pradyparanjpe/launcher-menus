Call ``<menu>``
---------------

A slim option to selection popups.

Call menu launchers [``dmenu``, ``bemenu``, ``<others>``] from python

Import in your script:

.. code:: python


   # import
   from launcher_menus import menu as bemenu

   user_letter = bemenu(command='bemenu', opts=['a', 'b', 'c', 'd'], fail=False)
   if user_letter is not None:
       # user did not hit <Esc>
       print(user_letter)
   else:
       print("Aborted...")

Results:

::

   a
