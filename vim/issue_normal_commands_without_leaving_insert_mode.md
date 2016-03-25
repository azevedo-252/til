# Issue normal commands without leaving insert mode

In insert mode, pressing Ctrl-O switches to normal mode for one command, then
switches back to insert mode when the command is finished.

Example:

Insert 6 dashes while in Insert mode:

`<C-o>6i-<Esc>`

You need to press `<Esc>` in order to leave the "inner" Insert mode.
