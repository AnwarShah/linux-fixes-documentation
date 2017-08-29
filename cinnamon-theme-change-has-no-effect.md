## Cinnamon theme settings has no effect

Ubuntu 17.04 comes with GTK-3.24 \(not all parts\).

### Issue:

Gnome 3.24 blocks cinnamon such that editing cinnamon settings has no effect. You can change theme's control, icon but it doesn't change anything.

### **Fix:**

Type this command in a terminal to block gnome setting daemon plugins and then re-login again.

```
gsettings set org.cinnamon.SessionManager autostart-blacklist "['gnome-settings-daemon', 'gnome-fallback-mount-helper', 'gnome-screensaver', 'mate-screensaver', 'mate-keyring-daemon', 'indicator-session', 'gnome-initial-setup-copy-worker', 'gnome-initial-setup-first-login', 'gnome-welcome-tour', 'xscreensaver-autostart', 'nautilus-autostart', 'caja', 'xfce4-power-manager', 'org.gnome.SettingsDaemon.A11yKeyboard', 'org.gnome.SettingsDaemon.A11ySettings', 'org.gnome.SettingsDaemon.Clipboard', 'org.gnome.SettingsDaemon.Color', 'org.gnome.SettingsDaemon.Datetime', 'org.gnome.SettingsDaemon.Housekeeping', 'org.gnome.SettingsDaemon.Keyboard', 'org.gnome.SettingsDaemon.MediaKeys', 'org.gnome.SettingsDaemon.Mouse', 'org.gnome.SettingsDaemon.Orientation', 'org.gnome.SettingsDaemon.Power', 'org.gnome.SettingsDaemon.PrintNotifications', 'org.gnome.SettingsDaemon.Rfkill', 'org.gnome.SettingsDaemon.ScreensaverProxy', 'org.gnome.SettingsDaemon.Sharing', 'org.gnome.SettingsDaemon.Smartcard', 'org.gnome.SettingsDaemon.Sound', 'org.gnome.SettingsDaemon.Wacom', 'org.gnome.SettingsDaemon.XRANDR', 'org.gnome.SettingsDaemon.XSettings']"
```



