SublimeREPL for SublimeText (2 and 3)
=====================================

**Note:** This fork of SublimeREPL is customized to my own needs and differs from the original SublimeREPL.

Features
--------

#### Common
 * Run an interpreter (REPL) inside SublimeText2 view/tab.
 * Per-language persistent REPL history.
 * Easily evaluate code in the running REPL
 * Replace your current build system, and use stdin in your programs.
 * Rich configuration with platform specific settings, project/file dependent environment variables and sane defaults.

#### Python
 * Launch python in local or remote(1) virtualenv.
 * Quickly run selected script or launch PDB.
 * Use SublimeText2 Python console with history and multiline input.

(1) - (ssh, linux/osx only)

Screenshots
-----------
#### Running python code in SublimeREPL
![Running python code in SublimeREPL](http://i.imgur.com/mmYQ6.png)
#### R on Windows
![R on Windows](http://i.imgur.com/jjsDn.png)

Videos
------
 * ![Python & virtualenv over SSH](http://img.youtube.com/vi/zodAqBvKQm0/2.jpg)  [Python & virtualenv over SSH](http://youtu.be/zodAqBvKQm0)
 * ![SBT integration demo](http://img.youtube.com/vi/1Y7Mr_RJpmU/3.jpg) [SBT integration demo](http://youtu.be/1Y7Mr_RJpmU)


Installation
============

1. Install Package Control. [http://wbond.net/sublime_packages/package_control](http://wbond.net/sublime_packages/package_control)
2. Install SublimeREPL
 1. `Preferences | Package Control | Package Control: Install Package`
 2. Choose `SublimeREPL`
3. Restart SublimeText2
4. Configure `SublimeREPL` (default settings in `Preferences | Package Settings | SublimeREPL | Settings - Default` should be modified in `Preferences | Package Settings | SublimeREPL | Settings - User`, this way they will survive package upgrades!

Documentation
=============

Very basic documentation will soon be available on RTD: [http://sublimerepl.readthedocs.org/](http://sublimerepl.readthedocs.org/)

#### Getting started

* Create or open your file with code.
* Menu / Tools / Command Palette (OS X: `⇧⌘P`) 
then type "SublimeREPL" and select the approperiate language.
* Menu / View / Layout / Rows: 2 (OS X: `⌥⇧⌘2`).
* Menu / View / Move File to Group / Group 2 (`⌃⇧2`).

#### Keybindings

* Evaluate in REPL:
 * <kbd>ctrl+,</kbd>, <kbd>s</kbd> Selection
 * <kbd>ctrl+,</kbd>, <kbd>f</kbd> File  
 * <kbd>ctrl+,</kbd>, <kbd>l</kbd> Lines
 * <kbd>ctrl+,</kbd>, <kbd>b</kbd> Block
* Transfer in REPL (just copy, without evaluating it):
 * <kbd>ctrl+shift+,</kbd>, <kbd>s</kbd> Selection
 * <kbd>ctrl+shift+,</kbd>, <kbd>f</kbd> File  
 * <kbd>ctrl+shift+,</kbd>, <kbd>l</kbd> Lines
 * <kbd>ctrl+shift+,</kbd>, <kbd>b</kbd> Block

Note: <kbd>ctrl+,</kbd>, <kbd>f</kbd> means: press Ctrl and Comma, release all, press F.

#### Project build systems

In the following an example for a custom project-based build system is shown:
```json
{
    "build_system":
    [
        {
            "name": "Run Project in REPL",
            "view_id": "My Python Script",
            "cmd": ["python", "-u", "$project_path/Main.py"],
            "cmd_args": false,
            "cwd": "$project_path",
            "target": "repl_open",
            "type": "subprocess",
            "encoding": "utf8",
            "external_id": "python",
            "extend_env": {"PYTHONIOENCODING": "utf-8"}
        }
    ]
}
```

License and Price
=================

Since version 1.2.0 SublimeREPL is licensed under GPL. Previous versions were licensed under BSD.

Compatibility
================

SublimeREPL is developed against the latest dev build of SublimeText3.
Ubuntu 13.04 is main
