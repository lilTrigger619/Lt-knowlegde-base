# xmodap -- keyboard characters remapping.

This utitliy is used to remap a keyboard character with another.
Some times you may want to remap some keys in replacement for others
for convinience. Example, you may want to replace the **Esc** key with the **Caps_Lock**

## Usage
- You can simply use the command on the terminal to remap characters.
xmodmap -e "keycode 116 = Esc"
The above will change the keycode 116 (whatever that key is)  to the Esc key.
So now whenever the 116 is press the Esc key will run.

- But there is a better way to do this. We put all the bindings and modifications into
one file and run it like so; `xmodmap ./xconfigs`

- The key mappings should be in this format.
														regular | on_shift | on_mode_switch | on_mode_switch&shift
keycode <the code eg. 11y> = Keysym keysym keysm keysm

1. The key in the first column after the equals sign will output on regular inpu
1. The key in the second column after the equals sign will output on shitf+key
1. The key in the third column after the equals sign will output on_mode_switch+key
1. The key in the fourth column after the equals sign will output on_mode_switch+shift+key

### clear
We can **clear** all entries from a Modifier map: **Shift** **Lock** **Control** **Mod1** **Mod2** **Mod3** **Mod4**
example 
`clear Lock ! will remove all caps-log bindings`

### add
We can **add** keys to  a Modfier map: example 
`add Shift = a ! adds a to the keys that can be used to implement the shift input.

### remove
We can **remove** a keysym from a Modifier map: example.
`remove Shift = a ! removes the a binding to Shift`

**Note** the *!* is for commenting in the config file.

### Real example.
Below is an example of a config or script for xmodmap.

```
clear Lock ! remove all caplock binding on keys
keycode 66 = Mode_switch ! make the caps key be the mode switch
keycode 45 =  k K Up ! regular k, shift K, Mod k
keycode 44 = j J Down 
keycode 43 = h H Left
keycode 46 = l L Right
keycode 32 = o O Return
keycode 108 = Caps_Lock
keysym BackSpace = BackSpace Delete Delete ! shift Backspace will delete
```
