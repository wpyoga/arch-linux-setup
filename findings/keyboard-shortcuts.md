by default,
- tile_up_key is <Super>KP_Down
- tile_down_key is <Super>KP_Up
- tile_left_key is <Super>KP_Left
- tile_right_key is <Super>KP_Right

it seems that the up and down keys are inverted

on xfce 4.18, sometimes pressing the tile_right_key does not do anything
how to reproduce:
1. reset <Super>Right
1. re-assign <Super>Right to tile_right_key
1. try out Win+Right, it works
1. press Win key to open the xfce menu, and then Win again to close the xfce menu
1. try Win+Right, it doesn't work

