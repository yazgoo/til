# link opening

slack being a good linux citizen, it uses xdg-open to open links

to check your config, just run

xdg-mime query default x-scheme-handler/https

it uses `~/.config/mimeapps.list`

example with quetbrowser:

```
[Added Associations]
application/zip=org.qutebrowser.qutebrowser.desktop;
application/pdf=org.gnome.Evince.desktop;

[Default Applications]
x-scheme-handler/lbry=lbry.desktop
x-scheme-handler/jetbrains=jetbrains-toolbox.desktop
text/html=lbry.desktop
x-scheme-handler/aucapture=aucapture-opener.desktop
x-scheme-handler/http=org.qutebrowser.qutebrowser.desktop
scheme-handler/http=org.qutebrowser.qutebrowser.desktop
x-scheme-handler/https=org.qutebrowser.qutebrowser.desktop
scheme-handler/https=org.qutebrowser.qutebrowser.desktop
x-scheme-handler/msteams=teams.desktop
```
