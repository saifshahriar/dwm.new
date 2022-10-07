# DWM - Dynamic Window Manager

My build of dmenu with minimal patches. Go to [patches](https://github.com/saifshahriar/dwm-saif-git/blob/master/README.md#patches) section to know more.

<hr>

dwm is an extremely fast, small, and dynamic window manager for X.

## Requirements
- In order to build dwm you need the Xlib header files.
- For colour emoji support, install `libxft-bgra`. Heres the [repo](https://github.com/uditkarode/libxft-bgra).

## Installation
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

```bash
make clean
make clean install
```

## Running dwm
Add the following line to your .xinitrc to start dwm using startx:

```bash
exec dwm
```

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

```bash
DISPLAY=foo.bar:1 exec dwm
```

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

```bash
while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
do
    sleep 1
done &
exec dwm
```

## Configuration
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.

## Patches
Here are some of the patches that I have applied.

- actualfullscreen    - Actually toggle fullscreen for a window, instead of toggling the status bar and the monocle layout.
- alttagsdecoration   - An alternative text for tags which contain at least one window
- alwayscenter        - Always center floating windows.
- center first window - Center specific window if only one window.
- maximize            - Toggle maximize.
- movestack           - Move stacks in a tag using mod+shift+{j,k}
- noborder            - Noborder when only one window.
- pertag              - dwm pertag patch, which allow different type of window size in different tags and doesn't change if one changed in one tag.
- preserveonrestart   - Don't mashup all windows in a single tag on restarting dmw
- psudogaplessgrid    - Basically `gaplessgrid` layout. Psudo version is modified by me which adds gaps from `vanitygaps` patch.
- selfrestart         - Restart dwm without exiting logging back on.
- status2d            - Allows colors and rectangle drawing in DWM status bar.
- underline tags      - Underline below a tag.
- vanitygaps          - Adds gapps around the windows.
- xrdb                - Read colors from xresources. For this patch to work, run the command `xrdb -load <path-to-xresources>`

