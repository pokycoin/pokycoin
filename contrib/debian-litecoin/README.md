
Debian
====================
This directory contains files used to package pokycoind/pokycoin-qt
for Debian-based Linux systems. If you compile pokycoind/pokycoin-qt yourself, there are some useful files here.

## pokycoin: URI support ##


pokycoin-qt.desktop  (Gnome / Open Desktop)
To install:

	sudo desktop-file-install pokycoin-qt.desktop
	sudo update-desktop-database

If you build yourself, you will either need to modify the paths in
the .desktop file or copy or symlink your pokycoin-qt binary to `/usr/bin`
and the `../../share/pixmaps/bitcoin128.png` to `/usr/share/pixmaps`

pokycoin-qt.protocol (KDE)

