# VSCodium

Install VSCodium with the following commands in terminal:

```
sudo rpmkeys --import https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg
printf "[gitlab.com_paulcarroty_vscodium_repo]\nname=download.vscodium.com\nbaseurl=https://download.vscodium.com/rpms/\nenabled=1\ngpgcheck=1\nrepo_gpgcheck=1\ngpgkey=https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/-/raw/master/pub.gpg\nmetadata_expire=1h" | sudo tee -a /etc/yum.repos.d/vscodium.repo
sudo dnf install codium -y
```

Click "Mark as done", then disable "Show welcome page on startup" on the new page.

Change the following settings:

- Text Editor
  - Line Numbers: relative
  - Scrollbar: Horizontal: hidden
  - Scrollbar: Vertical: hidden
  - Detect Indentation: Off
  - Inlay Hints: Off
  - Sticky Scroll: Off
  - Tab Size: 2
  - Word Wrap: On
  - Wrapping Indent: indent
  - HTML > Format: Wrap Line Length: 0
  - Font
    - Font Family: Insert `'SF Mono', ` at the beginning after following the instructions in `sf-font.md`
    - Font Size: 12
  - Formatting
    - Format On Paste: On
    - Format On Save: On
  - Minimap
    - Max Column: 30
    - Render Characters: Off
    - Show Slider: always
    - Side: left
    - Size: fit
- Workbench
  - Breadcrumbs
    - Enabled: Off
  - Zen
    - Hide Line Numbers: Off
    - Show tabs: none
- Window
  - Auto Detect Color Scheme: On
  - Zoom Level: 1
- Features
  - Source Control
    - Diff Decorations Gutter Width: 1
  - Terminal
    - Integrated: Font Family: 'SF Mono'
    - Integrated: Font Size: 13

Install the Fedora GNOME light & dark themes extension by olifink, and change the following settings:

- Workbench
  - Appearance
    - Color Theme: Gnome Light (GitHub)
    - Preferred Dark Color Theme: Gnome Dark (GitHub)
    - Preferred Light Color Theme: Gnome Light (GitHub)

Install the following extensions:
- VSCode Neovim extension by asvetliakov
- Error Lens by usernamehw
- Python by ms-python
- clangd by llvm-vs-code-extensions (install clangd when propted; you may have to open a .cpp file first in which case also press `Ctrl+Shift+P` and enter "clangd: Toggle inlay hints")
- Bash IDE by mads-hartmann
- ShellCheck by timonwong.
- Active File In StatusBar by RoscoP
- statusbar-commands by anweber
- Dart by Dart-Code

Also install shfmt by mkhl. Then, run `go install mvdan.cc/sh/v3/cmd/gosh@latest` to install the dependency. The directory `~/go/bin/` may need to be added to your PATH if it is not already.

Select View from the top bar, and under Appearance, disable the Menu Bar.

Press `Ctrl+Shift+P` and enter "Open User Settings (JSON)." Then, add a comma to the last entry before the closing curly brace, and add the following after:

```
    "workbench.colorCustomizations": {
        "editorOverviewRuler.addedForeground": "#0000",
        "editorOverviewRuler.bracketMatchForeground": "#0000",
        "editorOverviewRuler.commentForeground": "#0000",
        "editorOverviewRuler.commentUnresolvedForeground": "#0000",
        "editorOverviewRuler.commonContentForeground": "#0000",
        "editorOverviewRuler.currentContentForeground": "#0000",
        "editorOverviewRuler.deletedForeground": "#0000",
        "editorOverviewRuler.errorForeground": "#0000",
        "editorOverviewRuler.findMatchForeground": "#0000",
        "editorOverviewRuler.incomingContentForeground": "#0000",
        "editorOverviewRuler.infoForeground": "#0000",
        "editorOverviewRuler.inlineChatInserted": "#0000",
        "editorOverviewRuler.inlineChatRemoved": "#0000",
        "editorOverviewRuler.modifiedForeground": "#0000",
        "editorOverviewRuler.rangeHighlightForeground": "#0000",
        "editorOverviewRuler.selectionHighlightForeground": "#0000",
        "editorOverviewRuler.warningForeground": "#0000",
        "editorOverviewRuler.wordHighlightForeground": "#0000",
        "editorOverviewRuler.wordHighlightStrongForeground": "#0000",
        "editorOverviewRuler.wordHighlightTextForeground": "#0000"
    },
    "statusbar_command.commands": [
        {
            "text": "$(folder)",
            "tooltip": "Open Containing Folder",
            "id": "sbc_folder",
            "name": "sbc_folder",
            "priority": 1,
            "alignment": "left",
            "command": "revealFileInOS"
        },
        {
            "text": "$(gear)",
            "tooltip": "Open User Settings",
            "id": "sbc_settings",
            "name": "sbc_settings",
            "priority": 1,
            "alignment": "right",
            "command": "workbench.action.openWorkspaceSettings"
        },
        {
            "text": "$(book)",
            "tooltip": "Toggle Zen Mode",
            "id": "sbc_zen",
            "name": "sbc_zen",
            "priority": 1,
            "alignment": "right",
            "command": "workbench.action.openWorkspaceSettings"
        }
    ]
```

Right click the bottom status bar, and disable the following items:

- Remote Host
- Source Control Checkout
- Source Control Publish
- Forwarded Ports
- VSCode Neovim (Extension)
- Editor Indentation
- Editor Encoding
- Editor End of Line
- Editor Language

Change `-1` to `1` in `~/.vscode-oss/extensions/roscop.activefileinstatusbar-1.0.3-universal/extension.js` at this line:

```
var sb = vscode.window.createStatusBarItem(vscode.StatusBarAlignment.Left, 1);
```

Restart VSCodium for some changes to take effect.

Remove the following keybind by rightclicking it in Keyboard Shortcuts (open it by searching it through `Ctrl+Shift+P`)

- workbench.action.quit

Open VSCode Neovim's settings, and add `q` to "Ctrl Keys For Insert Mode" and "Ctrl Keys For Normal Mode"
