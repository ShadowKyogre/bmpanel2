## Alternative way of killing tasks ##
  1. I don't like the way it works now. Dragging task out of the panel isn't really an intuitive action.
  1. I don't like the idea of a popup menu. The idea is too old and I'm sure there are better ways.
  1. There is another conventional way of doing this kind of action and you can observe it in your web browser. Tabs have the "Close Tab" button on the right side (in firefox for example).
    * There is only one downside of the "tabs" method. User may accidentally press this button. It is possible to avoid this by asking user to press the right mouse button, but it's less intuitive.
    * This method requires theme updates (cross icon).
  1. One more idea is an icon menu. User holds down the right mouse button and the task button itself turns into an icon menu with icons representing different actions.
    * It's possible to make more actions (two, three, maybe four).
    * Requires a lot of new theme code and theme updates.
    * I don't actually see what actions should be there. Maximize/minimize? IMHO the panel isn't the place for that.
  1. Simple as hell - kill task with middle mouse button (btw browsers have this too).

## Visual improvement ##
  1. Animation.
    * It will require a lot of changes in rendering code, but even more changes in "themeing" area.
    * How this feature will be represented in themes? Probably only simple variants like alpha interpolation are realistic.
    * Will load a CPU more. To overcome this effect it is required to move a lot of rendering stuff on the GPU side. I'm not sure it will be easy to do with plain X11 code and Cairo.
    * Other interesting things are possible: shaders? blurry transparency?
    * I really like to see this kind of stuff, but current underlying architecture (X11) will not allow this. Because even the Composite is still a pain in the ass.

## Interaction improvement ##
  1. Currently bmpanel2cfg asks bmpanel2 to reload the whole config each time it changes anything. It's a big unnecessary overhead. There should be some kind of a remote interface.
    * The KDE systray protocol is using the DBus IPC system. It is possible to "kill two rabbits with one shot" here.

## Alternative widgets ##
  1. The support for that will be ready sooner or later. What the alternatives are, besides the fluxbox-like desktop switcher?

## Support for multiple launch bars ##
  1. The idea is simple though, but it is facing a "theme vs. config" conceptual problem. Bmpanel2 has clear concept statement: "Everything that changes the look of the panel is defined by theme". And obviously the widgets and the order of widgets are defined by theme.
  1. Having multiple launch bars means that user wants something here and something there and one actually chooses the location. But themes are not skins! It is intended that user can only change the look of the panel by choosing different theme.
  1. Currently I have no idea how is it possible to resolve this dilemma without breaking the concept of a consistent theme look. And it basicly means that theme will became a "skin" (a set of widget elements). But hey, there are things like decor and empty.. As I said.. no idea..