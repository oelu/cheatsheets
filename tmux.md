# TMUX and TMUXP Cheatsheet
Cheatsheet to match my tmux configuration. 

## Settings
C-a is command key.

## Sessions
Create a new session:

    tmux new-session -s code

Attach to a session:

    tmux attach -t code
Detach from session:

    C-a d
Next session:

    C-a )
Previous session:

    C-A (

## Windows
Create window: 

    C-a c
Goto next window: 

    C-a n
Goto previous window:

    C-a p

Split window horizontally: 

    C-a “

Split window vertically:

    C-a %

### Panes
Switching between panes: 

    C-a hjkl (vim movements)

Resize Panes: 

    C-a HJKL (vim movements)

## Copy Mode
Enter copy mode:

    C-a ESC
Copy and Paste: 

    vim bindings



