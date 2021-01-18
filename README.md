Documentation
=============

[![Documentation Status](https://readthedocs.org/projects/launcher-menus/badge/?version=latest)](https://launcher-menus.readthedocs.io/?badge=latest)

Installation
============

pip
---

Preferred method `pip install launcher-menus`

[pspman](https://github.com/pradyparanjpe/pspman)
-------------------------------------------------

For automated management: pre-release updates, etc
`pspman -s -i https://github.com/pradyparanjpe/launcher-menus.git`

Uninstallation
==============

pip
---

`pip uninstall -y launcher-menus`

pspman
------

Remove installation `pip uninstall -y launcher-menus`

Remove repository clone `pspman -s -d launcher-menus`

Usage
=====

Call menu
---------

-   Call menu launchers \[dmenu, bemenu, \<others\>\] from python
-   Import in your script

``` {.python tangle="no"}
from launcher_menus import menu as bemenu
user_letter = bemenu(command='bemenu', opts=['a', 'b', 'c', 'd'])
if user_letter is not None:
    # user did not hit <Esc>
    print(user_letter)
```

Results:

``` {.example}
a
```

What does it do
---------------

-   Runs a subprocess for the selected menu and returns its standard
    output or None

Configuration
=============

-   \<menu\>.yml files bear flags corresponding to actions for \<menu\>
-   \<menu\>.yml files are located in
    `<installation path>/site-packages/launcher_menus/menu-cfgs/`

Configuration format
--------------------

-   Copy *template* to `menu-cfgs/<your-menu>.yml`
-   edit fields

TODO
====

-   Configure rofi
-   Configure wofi (dead project?)
-   Configure others as issues arise
