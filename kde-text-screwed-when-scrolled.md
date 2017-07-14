## KDE text get screwed when scrolled

When scrolled through a long menu \(for example in Desktop Effects page or the alternate start menu\), the text become kind of screwed and the scroll speed is very slow. 

#### Solution

I found the solution from a [Manjaro Linux KDE community forum post](https://forum.manjaro.org/t/kde-menu-text-screwed-up-when-scrolling/21918/17). The solution needs an extra step which is to install `xserver-xorg-input-evdev` package.

1. Install `xserver-xorg-input-evdev` package
   `sudo apt-get install xserver-xorg-input-evdev`

2. Symlink a file

   `sudo ln -s /usr/share/X11/xorg.conf.d/10-evdev.conf /etc/X11/xorg.conf.d/10-evdev.conf`

3. Now reboot the pc

That's it. The problem is gone for good and KDE becomes awesome again!





