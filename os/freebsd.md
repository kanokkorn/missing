FreeBSD with bspwm
==================

This file will help go through start from fresh install to usable system for FreeBSD 13.2
(as current writing)

Get start
---------

Get a copy of .iso file from -> [https://www.freebsd.org/where/](https://www.freebsd.org/where/) and look for architecture to install.
In this case, will be choosing `amd64` . after that page will re-direct to `ISO-images/{version}.x`.

select file that end with `.iso` to start downloading.
after finished downloading, write `.iso` file to bootable media like USB-drive or DVD-disk

First setup
----------

FreeBSD handbook will walkthrough this step -> [https://docs.freebsd.org/en/books/handbook/bsdinstall/](https://docs.freebsd.org/en/books/handbook/bsdinstall/)

Prerequiste
-----------

After done setup user and logging in for first time. switch to `su` and update `pkg` with

```sh
user@local:~ % su # switch to root
password:
root@local:~ % pkg update
 ```

This may take a while to fetch and update all packages. When update is done, it's time to start install require packages.

 There will be:

 -  xserver     -> for rendering screen 
 -  alacritty   -> terminal emulator
 -  doas        -> root access
 -  sndio       -> audio daemon
 -  bspwm       -> window manager
 -  sxhkd       -> hotkey daemon
 -  tmux        -> terminal multiplexer
 -  vim/neovim  -> text editor
 -  rofi        -> laucher menu
 -  dunst       -> notification


permission manager -> doas
--------------------------

More secure `sudo` replacement for BSD systems. To get `doas` working, switch to `su` and install packages `doas`

```sh
user@local:~ % su # switch to root
password:
root@local:~ % pkg install doas
 ```

 config file will locate in `/usr/local/etc/doas.conf`, open and edit with `vi` or `vim`

```sh
root@local:~ % vi /usr/local/etc/doas.conf
```

to config permission for user/group to leverage super-user

```
permit persist :{user/group}
```

save and quit. after `doas` read new config, will be able to use it like `sudo`

login screen -> ly
------------------

Ly is recommended for login screen since you will be able to select DE before login

after install `ly` with `pkg install ly` you need to edit 2 config files:

  - /etc/gettytab
  - /etc/ttys

for `/etc/gettytab`, recommmend use `tab` instead of `space` for guarantee execution

```
Ly:\
      :lo=/usr/local/bin/ly:\
      :al=root:
```

for `/etc/tty`, recommmend use `tab` instead of `space` for guarantee execution

```
ttyv0   "/usr/libexec/getty Ly"         xterm   on secure
```
