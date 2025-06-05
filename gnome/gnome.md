## Backup at restore gnome

###### For exporting all gnome settings:

    dconf dump / > gnome.dconf

###### For loading all gnome settings:

    dconf load / < gnome.dconf

###### For exporting gnome extensions:

    dconf dump /org/gnome/shell/extensions/ > gnome-extensions.txt

###### For loading gnome extensions:

    dconf load /org/gnome/shell/extensions/ < gnome-extensions.txt
