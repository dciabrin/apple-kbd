===========================================
Linux Support for Apple Aluminium Keyboards
===========================================

Copyright © 2009-2011 Damien Ciabrini - damien.ciabrini@gmail.com


Overview
========
This package enables auto-detection and auto-configuration of several
models of Apple Aluminium Keyboards (US, JIS and International) for
Xorg's X server.

The support relies on udev and XKB to provides the relevant keyboard
settings to the X server, based on the keyboard model and various user
configurations. It works with an hotplug-enabled X server, there is no
need to modify xorg.conf.

In addition, the support provides various customizations of the
Aluminium Keyboard behaviour, such as key remapping (Insert, legacy PC
keys) or selection of Fxx behaviour (multimedia vs function keys).
This is achieved by means of evdev and sysfs.


Build and Install
-----------------
First of all, open the Makefile and have a look at variables RULESDIR
and CONFIGDIR: they specify the installation path of the support and
the user configuration. The default values are pretty standard paths:

   * RULESDIR: default udev installation path (/etc/udev/rules.d)
   * CONFIGDIR: default configuration path (/etc)

If needed, change it according to the specificities of your distro.

Once you are happy with the build configuration, just type::

   > make
   > sudo make install

The support should be installed and ready to be used at the next X
server login.

To uninstall the support, type::

   > sudo make uninstall

Be aware that keyboard settings will be lost.

To clean the build directory, type::

   > make clean


Keyboard Configuration
----------------------
The configuration file apple-kbd contains a detailed description of the
options you can set to customize the behaviour of your keyboard. The
settings currently available are:

   * Emulate PC keys (Print, Scroll Lock, Pause, Num Lock)
   * Make the "fn" key generate an "Insert" scancode
   * Choose the behaviour of keys F1 to F12 (multimedia vs functions)

Those settings can be deactivated by commenting the relevant lines in
the file. Please refer to this file for more information.


Disclaimer
----------
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
