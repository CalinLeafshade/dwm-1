dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X. This is a heaviliy patched dwm that fits pretty much all the tasks I need from a window manager.


Requirements
------------
In order to build dwm you need the Xlib header files.


Installation
------------
Simply clone it and build. e.g.,

    $ git clone https://github.com/allinurl/dwm.git && cd dwm
    $ make
    # make install

Install bitmap fonts

    $ git clone https://github.com/stark/siji && cd siji
    $ ./install.sh -d ~/.fonts
    
Place your .xinitrc in your home directory. See my [dotfiles](https://github.com/allinurl/dotfiles/blob/master/.xinitrc) repo. 

    $ cd
    $ wget https://github.com/allinurl/dotfiles/blob/master/.xinitrc

And you're good to go at this point.

    $ startx
    
Enjoy!

Custom Configuration
------------
The configuration of dwm is done by creating a custom config.h and (re)compiling the source code. Take a look at the [**config.h**](https://github.com/allinurl/dwm/blob/master/config.h) if you are interested to change some of the key bindings. Though, you should have enough flexibility with the current setup.


Running dwm (custom xinitrc)
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm
