# VSCode Jupyter Cheatsheet

Format: `Mac` / `Win,Linux`

## Cell Execution
```
Shift+Enter / Shift+Enter      # run cell and move to next
Ctrl+Enter / Ctrl+Enter        # run cell and stay
Alt+Enter / Alt+Enter          # run cell and insert below
Cmd+Alt+Enter / Ctrl+Alt+Enter # run all cells above
Cmd+Enter / Ctrl+Enter         # run all cells
```

## Cell Navigation
```
Up/Down / Up/Down              # move between cells (edit mode)
Ctrl+Up / Ctrl+Up              # move to previous cell (command mode)
Ctrl+Down / Ctrl+Down          # move to next cell (command mode)
Cmd+Shift+P / Ctrl+Shift+P     # command palette
J / J                          # select next cell (command mode)
K / K                          # select previous cell (command mode)
```

## Cell Editing
```
A / A                          # insert cell above (command mode)
B / B                          # insert cell below (command mode)
DD / DD                        # delete cell (command mode)
Z / Z                          # undo cell deletion (command mode)
X / X                          # cut cell (command mode)
C / C                          # copy cell (command mode)
V / V                          # paste cell below (command mode)
Shift+V / Shift+V              # paste cell above (command mode)
Ctrl+Shift+- / Ctrl+Shift+-    # split cell at cursor
Shift+M / Shift+M              # merge with cell below (command mode)
Enter / Enter                  # enter edit mode
Esc / Esc                      # enter command mode
```

## Cell Types
```
M / M                          # change to markdown (command mode)
Y / Y                          # change to code (command mode)
```

## Kernel Management
```
00 / 00                        # restart kernel (command mode)
Cmd+Alt+. / Ctrl+Alt+.         # interrupt kernel
```

## Quick Tips
```
# Command mode vs Edit mode
- Command mode: for cell-level operations (press Esc)
- Edit mode: for editing cell content (press Enter)

# Common workflow
1. Run cells with Shift+Enter
2. Add cells with A (above) or B (below)
3. Delete with DD, undo with Z
4. Switch to markdown with M, back to code with Y

# Variable Explorer
- Click "Variables" button at top of notebook
- View DataFrames in interactive viewer
```
