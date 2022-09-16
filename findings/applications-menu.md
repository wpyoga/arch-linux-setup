when the shortcut key is first pressed (default alt+f1, but other keys work the same),
the applications button on the panel becomes "depressed", but nothing else happens.

when the shortcut key is pressed again, the applications menu appears at the mouse
pointer position.

at this point, the applications button stays depressed until we click on it using the
mouse pointer (to open it) and then click on it again to close it.


if the applications button is clicked using a mouse, the applications menu is shown correctly.

sometimes (very rarely) i can press the shortcut key and the applications menu will be shown,
but it is a very rare occurence and i cannot reliably reproduce this behaviour


if the command xfce4-popup-applicationsmenu is run (either from the command line, or
from the application finder), the applications menu is shown on the cursor position


the desired behaviour: the applications menu appears as intended
and when the mouse clicks somewhere else, the applications menu is closed


this does not happen with the whiskermenu
the shortcut key always works as intended

