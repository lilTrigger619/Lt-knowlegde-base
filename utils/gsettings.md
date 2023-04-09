

# GSETTINGS
gsettings is just like the use of the gui settings except it is
used in the terminal

### Get all the available values for a key schema
	gsettings range org.gnome.system.proxy mode
the above should return all the available values to the key `mode` on the `proxy` schema

### Get the existing value of key of a schema
	gsettings get org.gnome.system.proxy mode
this will return the current value of the proxy mode.

### Set manual proxy
	gsettings set org.gnome.system.proxy mode "manual"
the above command will set the proxy mode to manual 

### Set laptop lid close action when charging
	gsettings set org.gnome.settings-daemon.plugins.power lid-close-ac-action "suspend"
The above will set the action of a close lid on charge to suspend

### Set laptop lid close action when on battery
	gsettings set org.gnome.settings-daemon.plugins.power lid-close-battery-action "nothing"
The above will make the laptop do nothing when the lid
is closed on battery.