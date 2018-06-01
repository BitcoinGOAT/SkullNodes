
Debian
====================
This directory contains files used to package skullnodesd/skullnodes-qt
for Debian-based Linux systems. If you compile skullnodesd/skullnodes-qt yourself, there are some useful files here.

## skullnodes: URI support ##


skullnodes-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install skullnodes-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your sendqt binary to `/usr/bin`
and the `../../share/pixmaps/send128.png` to `/usr/share/pixmaps`

skullnodes-qt.protocol (KDE)

