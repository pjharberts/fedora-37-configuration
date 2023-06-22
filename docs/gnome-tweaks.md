# GNOME Tweaks

Run the following to install GNOME Tweaks:

```
sudo dnf install gnome-tweaks -y
```

- General
  - Suspend when laptop lid is closed: Off
- Window Titlebars
  - Titlebar Actions
    - Double-Click: Menu
    - Middle-Click: Menu
- Windows
  - Attach Modal Dialogs: Off
  - Resize with Secondary-Click: On
  - Window Action Key: Alt
  - Window Focus: Focus on Hover
  - Raise Windows When Focused: On

Move all the contents of `conf/tweaks/` to `.themes/` after following the instructions in `sf-font.md`, and change the following setting:

- Appearance
  - Themes
    - Shell: Choose light-top-bar, dark-top-bar, or invisible-top-bar
    - Legacy Applications: Adwaita-dark (only if you want dark theme)    
