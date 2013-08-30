STM32DiscoveryVCP
=================

This is a minimalistic project for the CooCox IDE which sets up a Virtual COM Port project for the STM32F4xx Discovery Board.  All files not necessary for the STM32F4xx board or virtual com port have been removed, and as many of the standard CooCox library files are used as possible.  The only non-standard directories are usb_conf and usb_lib.


IDE and Compiler Setup
======================

This project builds with the CooCox IDE (http://www.coocox.org/index.html) - A great IDE for embedded ARM development - and the GNU Tools for Arm (https://launchpad.net/gcc-arm-embedded).  Install the IDE and the GNU Tools, point the IDE to the tools, and start working on your ARMs!


Tools for the STM32F4xx
=======================

The STM32F4xx Discovery board has a built in ST-LINK/V2 in-circuit debugger/programmer, just like the one here: http://www.st.com/web/catalog/tools/FM146/CL1984/SC724/SS1677/PF251168.  You can get drivers and utilities from that page.

You might also want the Virtual Com Port driver so you can talk to your STM32F4 once you load this project.  You can get that driver here: http://www.st.com/web/en/catalog/tools/PF257938.


Building and Running the Code
=============================

* Build: Load the project in CooCox IDE, click Build
* Program: Click the "Program" button in the CooCox IDE
* Test: Hook a USB Micro cable to the STM32 Discovery board.  The device should show up as a virtual com port.  If you connect to this port, the data you send will be echo'ed back and the green LED will flash with every character sent.


Debugging
=========

One of the coolest things about CooCox is the in-circuit debugger via the ST-LINK works out of the box.  That means you just click the little bug icon, wait a few seconds, and you've got breakpoints in a live embedded device!  You can step through the code, see variables, change things, etc.  Way Awesome!

If that doesn't cut it for you, you can also look at the blinky LED's.  If you load this project on the board and everything's running correctly, the orange LED should be blinking at close to 1Hz.  If something went wrong with the initialization, or if there was a USB exception, you'll see the four LED's blinking in a rapid clockwise order (it's fun to watch!).  If there's no LED's blinking, something went really wrong and the code didn't even get to the GPIO Init section...


Future Improvements
===================

I'm trying to keep this repo as clean and to-the-point as possible so I have a nice base to build my cooler projects from.  But making this easier for others to use would be nice too, so maybe I'll setup a Makefile build setup.


Special Thanks to the folks who wrote these Useful Pages
========================================================

http://vedder.se/2012/07/usb-serial-on-stm32f4/
http://blog.mark-stevens.co.uk/category/stm32/
