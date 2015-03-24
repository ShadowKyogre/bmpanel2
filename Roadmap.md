# Version 2.1 #

  * ~~Reload bmpanel2rc on the fly (using the unix signal similar to openbox).~~
  * ~~@ React on "demands attention" NETWM event (`_`NET\_WM\_STATE\_DEMANDS\_ATTENTION). Make this feature as an option (turned off by default).~~ (parameter: task\_urgency\_hint, just put it into the config file and the feature is turned on).
  * Bug fixes and ~~theme engine improvements.~~
  * ~~@ Customizable clock click action.~~
  * ~~Theme gallery. Clickable theme previews (link points to download).~~

Version 2.1 is preparing for the release. Few features were postponed to 2.x (2.2 or later).

# Version 2.x #
  * ~~Alternative widgets system.~~
    * ~~Alternative desktop switcher (like fluxbox). One label, two arrows.~~ (pager was implemented)
  * Reformat "--list" output. Looks ugly IMHO.
  * Theme pack format and installer script (like openbox's obt).
    * ThemeGallery update.
  * ~~Customizable position (hack for multimonitor systems). Or maybe even full Xinerama/TwinView/XRandr/Whatever support.~~
  * Bmpanel2cfg improvements.
    * Better icon selection (preview the whole directory?).
    * Icon pre-resizing (using "~/.cache").
    * Autocompletion for command.
  * Try to implement a theme generator (GTK+ integration).

## Alternative desktop switcher doubts ##

Why this feature was marked as "?"? The reason for that is the lack of ability to choose widgets in a theme among alternatives. Because I don't want this kind of themes: themeX\_normal, themeX\_alt, themeX\_dark\_normal, themeX\_dark\_alt, etc. If there are two desktop switchers (widgets which do the same funtion), then the user have to choose the one he likes, but he can't do that.

First I thought it would be nice to have something like:

```
preferred_widgets desktop_switcher taskbar systray clock
```

When doing parsing I will match this list simply. And if theme has two desktop switchers only one will be choosen. But there are certain types of widgets, like 'decor' or 'empty', that should be in a theme in any case (as well as taskbar, simply because you can't have a theme without the taskbar). Should I write this?:

```
preferred_widgets desktop_switcher taskbar systray clock decor empty
```

I'm not sure.. Maybe I should add kind of alternatives specification for widgets. If there are two widgets that can be an alternative for each other, just mark them inside and parse smartly with hint like this:

```
preferred_alternatives desktop_switcher
#preferred_alternatives desktop_switcher_alt
```

I don't know.. any thoughts?