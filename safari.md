# Safari Cheatsheet

<!-- TOC -->
- [User Shortcuts](#user-shortcuts)
  - [Navigation](#navigation)
  - [Tabs](#tabs)
  - [Windows](#windows)
  - [Scrolling & Zoom](#scrolling-zoom)
  - [Bookmarks & Reading List](#bookmarks-reading-list)
  - [Address Bar](#address-bar)
  - [Reader & Privacy](#reader-privacy)
- [Developer Tools](#developer-tools)
  - [Setup](#setup)
  - [Opening Inspector](#opening-inspector)
  - [Panel Navigation](#panel-navigation)
  - [Elements Panel](#elements-panel)
  - [Console](#console)
  - [Debugger](#debugger)
  - [Network](#network)
  - [Responsive Design](#responsive-design)
  - [Console API](#console-api)
  - [Tips](#tips)
<!-- /TOC -->


## User Shortcuts

### Navigation
```
Cmd+[                      # back
Cmd+]                      # forward
Cmd+R                      # reload page
Cmd+Shift+R                # reload without cache
Cmd+.                      # stop loading
Cmd+Shift+H                # go to homepage
Cmd+L                      # focus address bar
```

### Tabs
```
Cmd+T                      # new tab
Cmd+W                      # close tab
Cmd+Shift+T                # reopen last closed tab
Cmd+Z                      # undo close tab (immediately after)
Cmd+Option+W               # close all tabs except current
Ctrl+Tab                   # next tab
Ctrl+Shift+Tab             # previous tab
Cmd+1-9                    # go to tab 1-9
Cmd+Shift+\                # show all tabs (tab overview)
Cmd+Shift+Click            # open link in new tab, stay on current
Cmd+Click                  # open link in new tab, switch to it
```

### Windows
```
Cmd+N                      # new window
Cmd+Shift+N                # new private window
Cmd+M                      # minimize window
Cmd+Shift+M                # minimize all windows
Cmd+W                      # close window (when no tabs)
Cmd+Q                      # quit Safari
Cmd+`                      # cycle between windows
Ctrl+Cmd+F                 # toggle full screen
```

### Scrolling & Zoom
```
Space                      # scroll down one page
Shift+Space                # scroll up one page
Cmd+Up                     # scroll to top
Cmd+Down                   # scroll to bottom
Cmd++                      # zoom in
Cmd+-                      # zoom out
Cmd+0                      # reset zoom to 100%
```

### Bookmarks & Reading List
```
Cmd+D                      # add bookmark
Cmd+Shift+D                # add to Reading List
Cmd+Option+B               # show bookmarks sidebar
Cmd+Shift+L                # show Reading List sidebar
Cmd+Option+1               # show bookmarks bar
```

### Address Bar
```
Cmd+L                      # select address bar
Cmd+Return                 # open URL in new tab
Option+Return              # download linked file
Cmd+Shift+Return           # open in new window
```

### Reader & Privacy
```
Cmd+Shift+R                # toggle Reader mode (when available)
Cmd+Shift+N                # new private window
Cmd+Option+E               # empty caches
Cmd+Y                      # show history
```


## Developer Tools

### Setup
Enable Web Inspector (first time only):
```
Safari > Settings > Advanced > "Show features for web developers"
```

### Opening Inspector
```
Cmd+Option+I               # open/close Web Inspector
Cmd+Option+C               # open Inspector, jump to Console
Cmd+Option+U               # view page source
Cmd+Option+A               # open Web Inspector, select element
Right-click > Inspect      # inspect specific element
```

### Panel Navigation
```
Cmd+Shift+E                # Elements panel
Cmd+Shift+C                # Console panel
Cmd+Shift+N                # Network panel
Cmd+Shift+S                # Sources panel
Cmd+Shift+T                # Timelines panel
Cmd+Shift+G                # Graphics panel
Cmd+Shift+L                # Layers panel
Cmd+Shift+A                # Audit panel
Cmd+[                      # previous panel
Cmd+]                      # next panel
```

### Elements Panel
```
Cmd+Option+A               # enable element selection mode
Up/Down                    # navigate DOM tree
Left/Right                 # collapse/expand node
Enter                      # edit attribute
Tab                        # next attribute
Option+Click               # expand all children
Delete                     # delete node
Cmd+Z                      # undo DOM change
H                          # hide/show element (visibility)
```

### Console
```
Cmd+K                      # clear console
Ctrl+L                     # clear console (alt)
Up/Down                    # previous/next command history
Tab                        # autocomplete
Shift+Return               # multiline input
Cmd+/                      # toggle comment (multiline mode)
Cmd+Option+C               # jump to console from any panel
```

### Debugger
```
Cmd+\                      # toggle breakpoint on current line
Cmd+Y                      # toggle breakpoint enabled/disabled
Cmd+Shift+Y                # toggle all breakpoints
F8 / Cmd+\                 # pause/resume execution
F10 / Cmd+'                # step over
F11 / Cmd+;                # step into
Shift+F11 / Cmd+Shift+;    # step out
Cmd+G                      # go to line
Cmd+P                      # open file quickly
Cmd+Shift+O                # go to symbol
```

### Network
```
Cmd+K                      # clear network log
Cmd+F                      # filter requests
Cmd+Shift+N                # jump to Network panel
Click request              # view details
Option+Click               # copy as cURL
```

### Responsive Design
```
Cmd+Ctrl+R                 # enter Responsive Design Mode
Cmd+Ctrl+R (again)         # exit Responsive Design Mode
```
In Responsive Design Mode:
- Click device dropdown to select device preset
- Drag edges to resize viewport
- Rotate button to switch orientation


## Console API

Useful console commands:
```javascript
console.log()              // basic output
console.table()            // display as table
console.dir()              // interactive object
console.trace()            // stack trace
console.time('label')      // start timer
console.timeEnd('label')   // end timer
console.count('label')     // count occurrences
console.group('name')      // group output
console.groupEnd()         // end group
console.assert(cond, msg)  // conditional log
console.clear()            // clear console
$0                         // last selected element
$_                         // last evaluated result
$$('selector')             // querySelectorAll shortcut
```


## Tips

**Quick element inspection:**
- Right-click any element > Inspect Element
- Or enable selection mode: `Cmd+Option+A` then click

**Dock position:**
- Click dock icon in top-right of Inspector to change position (bottom, right, detached)

**Preserve log:**
- Click settings gear in Console > "Preserve Log" to keep logs across page loads

**Breakpoint on DOM change:**
- Right-click element in DOM tree > Break on > Subtree modifications

**Local overrides:**
- In Sources panel, create local file overrides to test changes without modifying server

**Network throttling:**
- In Network panel, use dropdown to simulate slow connections

**Copy as cURL:**
- Right-click any network request > Copy > Copy as cURL
