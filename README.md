# Tomato Timer

### [A Pomadoro Timer](http://cirillocompany.de/pages/pomodoro-technique)

This app runs in the system tray. Left click the tray icon and it will sound an alarm after 25 minutes.

* Requires Python 2 and gtk2 bindings (`python-gtk2` package on Debian)
* Short (< 100 lines)
* Only systemd systems will work "out of the box", but that is trivial to fix.

### Status line support (i3bar, dzen2, xmobar, lemonbar etc)

The program outputs the time left to `/run/user/1000`. The `1000` part of that
might be different on your system, check `id -u`. systemd users should have that
directory present, and it will hopefully be a `tmpfs` file system in memory so
will spare your disks.

The format is:

```
1500
750
```

The first line is the time you started with (in seconds), and the last line is
the time left. The idea is that you can use this information to display a
counter or draw a progress bar.
