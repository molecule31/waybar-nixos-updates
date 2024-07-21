# waybar-nixos-updates
Here's how the module looks in Waybar with and without updates:
![Screenshot with updates](screenshot-thumbnail-has-updates.png)
![Screenshot updates](screenshot-thumbnail-updated.png)

Here's how the module's tooltip looks when updates are available:
![Screenshot with updates](screenshot-has-updates.png)

A simple Waybar update checking script for NixOS. It is a general script and could work with other bars or just be run in the terminal.

Credit goes to [this project](https://github.com/J-Carder/waybar-apt-updates) for the idea.

## How to use

Download the `update-checker` script, put it in your [PATH](https://unix.stackexchange.com/a/26059) and make it executable (`chmod +x update-checker`).

To configure, add the following to your Waybar config (`~/.config/waybar/config`).


```json
"custom/nix-updates": {
    "exec": "$HOME/bin/update-checker", // <--- path to script
    "on-click": "$HOME/bin/update-checker && notify-send 'The system has been updated'", // refresh on click
    "interval": 3600, // refresh every hour
    "tooltip": true,
    "return-type": "json",
    "format": "{} {icon}",
    "format-icons": {
        "has-updates": "", // icon when updates needed
        "updated": "" // icon when all packages updated
    },
},
```

To style use the `#custom-nix-updates` ID in your Waybar styles file (`~/.config/waybar/styles.css`).

For more information see the [Waybar wiki](https://github.com/Alexays/Waybar/wiki).



