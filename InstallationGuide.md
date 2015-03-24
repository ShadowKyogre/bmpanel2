# Installation Guide for git version #

## Dependencies ##
  * git (build dep)
  * cmake (build dep)
  * make (build dep)
  * gcc (build dep)
  * asciidoc + docbook-xsl stylesheets (optional build dep, for man pages)
  * glib2 (with threading enabled, it should be enabled in the most popular distributions)
  * pango
  * cairo
  * libX11
  * python + pygtk (optional, for bmpanel2cfg)
  * DejaVu fonts (they are not necessary, but a lot of themes use them)


---


## Compiling ##
```
git clone --depth=1 git://github.com/nsf/bmpanel2.git
cd bmpanel2
cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=RELEASE .
make
sudo make install
```

### Comments ###
You can set CMAKE\_INSTALL\_PREFIX to whatever you want, like /usr/local or anywhere. Build type isn't necessary, but it's better to use RELEASE type if you aren't the developer.

I'm using `git clone --depth=1` because obviously it is an installation guide and you don't need all sources history of the project on your computer. But this command does downloads faster and requires less traffic.


---


## Using ##
```
echo "theme xsocam_dark" > ~/.config/bmpanel2/bmpanel2rc
bmpanel2
```

### Comments ###
Bmpanel2 uses [XDG](http://standards.freedesktop.org/basedir-spec/basedir-spec-0.6.html) spec for locating its files. By default the config file is: ~/.config/bmpanel2/bmpanel2rc. Themes should be placed in this dir (by default): ~/.local/share/bmpanel2/themes/.

There is also a short help: `bmpanel2 --help` and a man page: `man bmpanel2`

Use this command to see available themes: `bmpanel2 --list`


---


## Installing theme ##
```
cd ~/.local/share/bmpanel2/themes
wget "http://bmpanel2.googlecode.com/files/Auriel%20-%20BMPanel2.tar.gz"
tar -xvf "Auriel - BMPanel2.tar.gz"
rm "Auriel - BMPanel2.tar.gz"
```

### Comments ###
And after that you can edit the config file (~/.config/bmpanel2/bmpanel2rc) or start bmpanel2 using "--theme" parameter:

```
bmpanel2 --theme=Auriel-blue-smooth
```