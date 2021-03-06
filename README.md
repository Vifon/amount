NAME
====

amount - auto mount

SYNOPSIS
========

    amount [OPTIONS] sdb1         (mount /dev/sdb1)
    amount [OPTIONS] /dev/sdb1    (the same)

DESCRIPTION
===========

amount allows to easily mount and unmount devices.

When user mounts a device, a new subshell is started. The device is unmounted
when the subshell is closed. User can check which device is bound to the current
subshell using AMOUNT_DEVICE environmental variable.

EXAMPLE
-------

    $ amount sdb1
    * /dev/sdb1 mounted
    $ echo $AMOUNT_DEVICE
    /dev/sdb1
    $ pwd
    /media/sdb1
    $ exit
    * Unmounting /dev/sdb1...
    * /dev/sdb1 unmounted
    $ echo $AMOUNT_DEVICE

    $

OPTIONS
=======

* -h

    show help

* -n

    do not change directory

* -c <COMMAND>

    after mounting the volume run the specified command instead of the
    shell and then unmount the volume

INSTALLATION
============

Just copy _amount_ file to your PATH (for example /usr/local/bin).

DEPENDENCIES
------------

pmount, bash

CONFIGURATION
=============

_amount_ will use the device label as the mountpoint name if the label
is present. You can use it get consistent/persistent paths.

AUTHOR
======

Wojciech 'vifon' Siewierski < wojciech dot siewierski at gmail dot com >

COPYRIGHT
=========

Copyright (C) 2012-2017  Wojciech Siewierski

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.
