# Default (OSX).sublime-keymap

```
[
```

## Movement and Selection

Sometimes I move my cursor up and down lines with the arrow keys, but I often
will use `CTRL+P` (up) and `CTRL+N` (down).

The following extends those two commands so that holding `SHIFT` causes you to
expand your selection up or down lines.

```
    {
        "keys": [
            "ctrl+shift+p"
        ],
        "args": {
            "by": "lines",
            "forward": false,
            "extend": true
        },
        "command": "move"
    },
    {
        "keys": [
            "ctrl+shift+n"
        ],
        "args": {
            "by": "lines",
            "forward": true,
            "extend": true
        },
        "command": "move"
    },
```

## Pasting and Indentation

### `SUPER+v` and `SHIFT+SUPER+v`

By default `SUPER+v` pastes code and `SHIFT+SUPER+v` pastes *and* indents code.
The following config reverses that logic because, hey, if you paste, you're
going to indent, eh?

I learned this in this [Wes Bos' post][wes-bos-tips].

[wes-bos-tips]: http://wesbos.com/5-sublime-text-tweaks-tips/

```
    {
        "keys": [
            "super+v"
        ],
        "command": "paste_and_indent"
    },
    {
        "keys": [
            "super+shift+v"
        ],
        "command": "paste"
    },
```

### `SUPER+SHIFT+r`

If you've selected text and press this key combo, Sublime will re-indent your
selection.

```
    {
        "keys": [
            "super+shift+r"
        ],
        "command": "reindent"
    },
```

## Wrapping Lines

```
    {
        "keys": [
            "super+q"
        ],
        "command": "wrap_lines_plus"
    },
```

## GitSavvy

There's a ton of stuff here.

### Core Keybindings

GitSavvy is "activated" in Sublime and then it becomes useful in a new window.
To get going I use the following commands:

* `SUPER+'+s`: Show Git Status
* `SUPER+'+l`: Show Graph of Commits
* `SUPER+'+d+d`: Show a Diff (unstaged)
* `SUPER+'+d+c`, `SUPER+'+d+s`: Show Diff (cached aka staged)
* `SUPER+'+c`: Open up a prompt and commit

#### `SUPER+'+s`

```
    {
        "keys": [
            "super+'",
            "s"
        ],
        "command": "gs_show_status"
    },
```

#### `SUPER+'+l`

```
    {
        "keys": [
            "super+'",
            "l"
        ],
        "command": "gs_log_graph_current_branch"
    },
```

#### `SUPER+'+d+d`

```
    {
        "keys": [
            "super+'",
            "d",
            "d"
        ],
        "command": "gs_diff"
    },
```

#### `SUPER+'+d+c`, `SUPER+'+d+s`

```
    {
        "keys": [
            "super+'",
            "d",
            "c"
        ],
        "args": {
          "in_cached_mode": true
        },
        "command": "gs_diff"
    },
    {
        "keys": [
            "super+'",
            "d",
            "s"
        ],
        "args": {
          "in_cached_mode": true
        },
        "command": "gs_diff"
    },
```

### Git Diff

When looking at a diff, if you use `CTRL+P` or `CTRL+N` you navigate between
sets of changes. I then use arrow keys to navigate within those sets.

```
    {
        "keys": [
            "ctrl+n"
        ],
        "command": "gs_diff_navigate",
        "args": {
            "forward": true
        },
        "context": [
            {
                "key": "setting.command_mode",
                "operator": "equal",
                "operand": false
            },
            {
                "key": "setting.git_savvy.diff_view",
                "operator": "equal",
                "operand": true
            }
         ]
     },
     {
         "keys": [
              "ctrl+p"
          ],
         "command": "gs_diff_navigate",
         "args": {
             "forward": false
         },
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.diff_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
```

And when you're done looking at a diff you can press `q` to leave immediately.

```
     {
         "keys": [
             "q"
         ],
         "command": "close",
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.diff_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
```

### Git Graph

Press `q` to leave immediately.

```
     {
         "keys": [
             "q"
         ],
         "command": "close",
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.log_graph_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
```

### Git Status

Press `q` to leave immediately.

```
     {
         "keys": [
             "q"
         ],
         "command": "close",
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.status_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
```

Use `CTRL+P` or pressing the up arrow or `CTRL+N` or pressing the down arrow
navigates between files within the status.

```
     {
         "keys": [
             "ctrl+n"
         ],
         "command": "gs_status_navigate_file",
         "args": {
             "forward": true
         },
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.status_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
     {
         "keys": [
             "down"
         ],
         "command": "gs_status_navigate_file",
         "args": {
             "forward": true
         },
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.status_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
     {
         "keys": [
            "ctrl+p"
         ],
         "command": "gs_status_navigate_file",
         "args": {
             "forward": false
         },
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.status_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
     {
         "keys": [
            "up"
         ],
         "command": "gs_status_navigate_file",
         "args": {
             "forward": false
         },
         "context": [
             {
                 "key": "setting.command_mode",
                 "operator": "equal",
                 "operand": false
             },
             {
                 "key": "setting.git_savvy.status_view",
                 "operator": "equal",
                 "operand": true
             }
         ]
     },
```

### `SUPER+'+c`

Quickly commit whatever's been staged.

```
     {
        "keys": [
            "super+'",
            "c"
        ],
        "command": "gs_quick_commit"
    },
```

```
]
```
