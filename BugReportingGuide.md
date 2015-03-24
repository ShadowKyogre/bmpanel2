# Bug Reporting Guide #

  * Make sure you're using the latest git version. Often I fix bugs and doesn't mention this anywhere. Because a lot of bugs appear in very uncommon cases (otherwise they're being noticed quickly) and normally you just shouldn't know about them.
  * It's really good if the bug is easily reproducable, try to describe exact steps to reproduce the bug. Because if I can reproduce it, I can investigate the problem which causes the bug. Something like: "Oh, there was a glitch, but I haven't seen it since" is really a waste of time. Useless information.
  * There is a special bug source - the system tray. Because it's the place where two applications are communicating extensively (the icon in the system tray is actually a different window owned by another app). So.. Please, make sure that the bug is in the panel. It's easy to do if you check the app with other panels (like gnome-panel or xfce4-panel). And if they didn't fix the bug, there is a big chance that I won't fix it too.
  * I like screenshots, send more of them. If it helps describing the bug - great!
  * You can report the bug via [mail](mailto:no.smile.face@gmail.com) or [issue tracker](http://code.google.com/p/bmpanel2/issues/list).
  * I like patches! If you can solve the problem by yourself - it's just really amazing! DO IT!
  * Don't afraid to contact me, I'm not an evil person. The worst case - I will ignore you.

