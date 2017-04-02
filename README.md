# st - simple terminal

This is a clone of [suckless.org](http://suckless.org) the coolest terminal client **st**.
Light, stable, simple and fast. **tmux** brings in all other needed features.

## Customizations

- **Inconsolata** font usage.
- **solarized** dark color scheme.
- **transparency** support added.

## Screen

![Screenshot](https://raw.github.com/l3pp4rd/st/master/screen.png)

## Requirements

In order to build st you need:

- Xlib header files - location of these might differ, edit config.mk
- xft lib headers.
- Inconsolata.ttf fonts, unless you change it in config.h

## Installation

Edit config.mk to match your local setup (**st** is installed into the
**/usr/local** namespace by default).

**NOTE:** to have unicode character support, install **freetype2** library
headers.

**NOTE:** **ranger** file manager may not preview images well, when having
transparency enabled.

## Transparency

You need to run **compton** or **xcompmgr** in order to have transparent
terminal.

### Ubuntu required libraries

    apt-get install libx11-dev libxext-dev libxft-dev fonts-inconsolata

Afterwards enter the following command to build and install st (if
necessary as root):

    make clean install

**NOTE** concerning [inconsolata font
changes](https://bbs.archlinux.org/viewtopic.php?id=206805), recently it
got bold font support and if you had hinstyle set to **none** it should
not make any impact. Otherwise you may need to set it to none.

## Running st

If you did not install st with make clean install, you must compile
the st terminfo entry with the following command:

    tic -s st.info

Run it with tmux:

    st -e tmux

See the man page for additional details.

## Credits

Based on Aurélien APTEL <aurelien dot aptel at gmail dot com> bt source code.

