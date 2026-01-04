# VSCode Cheatsheet

<!-- TOC -->
- [Keyboard Shortcuts](#keyboard-shortcuts)
  - [General](#general)
  - [Editing](#editing)
  - [Navigation](#navigation)
  - [Search & Replace](#search-replace)
  - [Multi-cursor](#multi-cursor)
  - [Code Intelligence](#code-intelligence)
  - [Terminal](#terminal)
- [Command Palette](#command-palette)
- [Settings](#settings)
- [Integrated Terminal](#integrated-terminal)
- [Tips & Tricks](#tips-tricks)
<!-- /TOC -->


## Keyboard Shortcuts

Format: `Mac` / `Win,Linux`

### General
```
Cmd+Shift+P / Ctrl+Shift+P     # command palette
Cmd+P / Ctrl+P                 # quick open file
Cmd+, / Ctrl+,                 # open settings
Cmd+Shift+N / Ctrl+Shift+N     # new window
Cmd+W / Ctrl+W                 # close tab
Cmd+Shift+W / Ctrl+Shift+W     # close window
Cmd+K Z / Ctrl+K Z             # zen mode (Esc Esc to exit)
Cmd+B / Ctrl+B                 # toggle sidebar
Cmd+J / Ctrl+J                 # toggle panel (terminal/output)
Cmd+K Cmd+S / Ctrl+K Ctrl+S    # keyboard shortcuts
```

### Editing
```
Cmd+X / Ctrl+X                 # cut line (empty selection)
Cmd+C / Ctrl+C                 # copy line (empty selection)
Cmd+Shift+K / Ctrl+Shift+K     # delete line
Alt+Up / Alt+Up                # move line up
Alt+Down / Alt+Down            # move line down
Shift+Alt+Up / Shift+Alt+Up    # copy line up
Shift+Alt+Down / Shift+Alt+Down # copy line down
Cmd+] / Ctrl+]                 # indent line
Cmd+[ / Ctrl+[                 # outdent line
Cmd+/ / Ctrl+/                 # toggle line comment
Shift+Alt+A / Shift+Alt+A      # toggle block comment
Shift+Alt+F / Shift+Alt+F      # format document
Cmd+K Cmd+F / Ctrl+K Ctrl+F    # format selection
Cmd+Z / Ctrl+Z                 # undo
Cmd+Shift+Z / Ctrl+Y           # redo
Cmd+Enter / Ctrl+Enter         # insert line below
Cmd+Shift+Enter / Ctrl+Shift+Enter # insert line above
```

### Navigation
```
Cmd+P / Ctrl+P                 # go to file
Cmd+G / Ctrl+G                 # go to line
Cmd+Shift+O / Ctrl+Shift+O     # go to symbol in file
Cmd+T / Ctrl+T                 # go to symbol in workspace
Ctrl+Tab / Ctrl+Tab            # switch to next tab
Ctrl+Shift+Tab / Ctrl+Shift+Tab # switch to prev tab
Cmd+\ / Ctrl+\                 # split editor
Cmd+1/2/3 / Ctrl+1/2/3         # focus editor group 1/2/3
Cmd+K Cmd+Left / Ctrl+K Ctrl+Left # focus prev group
Cmd+K Cmd+Right / Ctrl+K Ctrl+Right # focus next group
Cmd+Shift+E / Ctrl+Shift+E     # focus file explorer
Ctrl+- / Alt+Left              # go back
Ctrl+Shift+- / Alt+Right       # go forward
Cmd+Shift+. / Ctrl+Shift+.     # breadcrumb focus
```

### Search & Replace
```
Cmd+F / Ctrl+F                 # find
Cmd+H / Ctrl+H                 # replace
Cmd+Shift+F / Ctrl+Shift+F     # find in files
Cmd+Shift+H / Ctrl+Shift+H     # replace in files
F3 / F3                        # find next
Shift+F3 / Shift+F3            # find previous
Cmd+G / F3                     # find next (alt)
Cmd+D / Ctrl+D                 # add selection to next find match
Cmd+K Cmd+D / Ctrl+K Ctrl+D    # skip to next find match
Alt+Enter / Alt+Enter          # select all matches (in find)
```

### Multi-cursor
```
Alt+Click / Alt+Click          # add cursor
Cmd+Alt+Up / Ctrl+Alt+Up       # add cursor above
Cmd+Alt+Down / Ctrl+Alt+Down   # add cursor below
Cmd+D / Ctrl+D                 # select next occurrence
Cmd+Shift+L / Ctrl+Shift+L     # select all occurrences
Cmd+U / Ctrl+U                 # undo last cursor
Shift+Alt+I / Shift+Alt+I      # cursor at end of each selected line
Shift+Alt+Drag / Shift+Alt+Drag # column (box) selection
Cmd+Shift+K / Ctrl+Shift+K     # delete all selected lines
```

### Code Intelligence
```
F12 / F12                      # go to definition
Alt+F12 / Alt+F12              # peek definition
Cmd+K F12 / Ctrl+K F12         # open definition to side
Shift+F12 / Shift+F12          # find all references
F2 / F2                        # rename symbol
Cmd+. / Ctrl+.                 # quick fix / code actions
Cmd+K Cmd+I / Ctrl+K Ctrl+I    # show hover
Ctrl+Space / Ctrl+Space        # trigger suggestions
Cmd+Shift+Space / Ctrl+Shift+Space # trigger parameter hints
Cmd+K Cmd+X / Ctrl+K Ctrl+X    # trim trailing whitespace
```

### Terminal
```
Ctrl+` / Ctrl+`                # toggle terminal
Cmd+Shift+` / Ctrl+Shift+`     # new terminal
Cmd+\ / Ctrl+Shift+5           # split terminal
Cmd+Alt+Left / Alt+Left        # focus prev terminal
Cmd+Alt+Right / Alt+Right      # focus next terminal
Cmd+K / Ctrl+K (in terminal)   # clear terminal
```


## Command Palette

Open with `Cmd+Shift+P` / `Ctrl+Shift+P`. Prefix commands:
```
>              # run command (default)
@              # go to symbol in file
@:             # go to symbol by category
#              # go to symbol in workspace
:              # go to line number
?              # show help
```

Useful commands:
```
Reload Window                  # restart vscode
Toggle Word Wrap               # wrap long lines
Change Language Mode           # set syntax highlighting
Transform to Uppercase/Lowercase
Sort Lines Ascending/Descending
Join Lines
Trim Trailing Whitespace
Convert Indentation to Spaces/Tabs
Open Keyboard Shortcuts (JSON)
Preferences: Open Settings (JSON)
```


## Settings

### Locations
```
User settings:
  Mac:   ~/Library/Application Support/Code/User/settings.json
  Linux: ~/.config/Code/User/settings.json
  Win:   %APPDATA%\Code\User\settings.json

Workspace settings:
  .vscode/settings.json (in project root)
```

### Common Settings
```json
{
  "editor.fontSize": 14,
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  "editor.formatOnSave": true,
  "editor.minimap.enabled": false,
  "editor.renderWhitespace": "boundary",
  "editor.bracketPairColorization.enabled": true,
  "files.autoSave": "afterDelay",
  "files.trimTrailingWhitespace": true,
  "workbench.colorTheme": "Default Dark+",
  "terminal.integrated.fontSize": 13
}
```


## Integrated Terminal

### Basics
```
Ctrl+` / Ctrl+`                # toggle terminal
Cmd+Shift+` / Ctrl+Shift+`     # new terminal instance
Cmd+\ / Ctrl+Shift+5           # split terminal
```

### Profiles
Configure in settings:
```json
{
  "terminal.integrated.profiles.osx": {
    "zsh": { "path": "/bin/zsh" },
    "bash": { "path": "/bin/bash" }
  },
  "terminal.integrated.defaultProfile.osx": "zsh"
}
```


## Tips & Tricks

### Emmet
Type abbreviations and press `Tab`:
```
div.container>ul>li*3          # nested elements
p.intro#main                   # class + id
a[href="#"]                    # attributes
lorem                          # lorem ipsum text
```

### Quick Actions
```
Cmd+K M / Ctrl+K M             # change language mode
Cmd+K V / Ctrl+K V             # open markdown preview to side
Cmd+K Z / Ctrl+K Z             # zen mode
Cmd+K Cmd+T / Ctrl+K Ctrl+T    # select color theme
```

### Selection Tricks
```
Cmd+L / Ctrl+L                 # select entire line
Cmd+Shift+L / Ctrl+Shift+L     # cursors on all selected lines
Shift+Alt+Right / Shift+Alt+Right # expand selection
Shift+Alt+Left / Shift+Alt+Left   # shrink selection
Cmd+Shift+[ / Ctrl+Shift+[     # fold region
Cmd+Shift+] / Ctrl+Shift+]     # unfold region
Cmd+K Cmd+0 / Ctrl+K Ctrl+0    # fold all
Cmd+K Cmd+J / Ctrl+K Ctrl+J    # unfold all
```

### File Explorer
```
Cmd+Shift+E / Ctrl+Shift+E     # focus explorer
a (in explorer)                # new file
Shift+a (in explorer)          # new folder
Enter                          # rename
Delete / Delete                # delete
```
