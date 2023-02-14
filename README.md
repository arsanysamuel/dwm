# **dwm** - dynamic window manager

This is my build of the [suckless dwm](https://dwm.suckless.org/), including extra configuration and applied patches.

**dwm** is an extremely fast, small, and dynamic window manager for X.


## Requirements

In order to build dwm you need the Xlib header files.

Make sure you've installed a C compiler and `make` utility, for Arch Linux install `base-devel`.


## Installation

Edit `config.mk` to match your local setup (dwm is installed into
the `/usr/local` namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

```
# make clean install
```

See the [dwm](https://dwm.suckless.org/) official webpage or the [dwm archwiki page](https://wiki.archlinux.org/title/Dwm).


## Running dwm

Add the following line to your `.xinitrc` to start dwm using startx:

```
exec dwm
```

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

```
DISPLAY=foo.bar:1 exec dwm
```

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your `.xinitrc`:

```
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
    sleep 1
done &
exec dwm
```


## Configuration

The configuration of dwm is done by creating a custom `config.h` (a copy of `config.def.h`) and (re)compiling the source code.


## Patches

These are the [patches](https://dwm.suckless.org/patches/) that I've applied to my build:
- [centerewindowname](https://dwm.suckless.org/patches/centeredwindowname/dwm-centeredwindowname-20200723-f035e1e.diff)
- [hide vacant tags](https://dwm.suckless.org/patches/hide_vacant_tags/dwm-hide_vacant_tags-6.3.diff)
- [removeborder](https://dwm.suckless.org/patches/removeborder/dwm-removeborder-20220626-d3f93c7.diff)

