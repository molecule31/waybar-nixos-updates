# waybar-nixos-updates
Simpler version of Waybar update checking script for NixOS which shows how many packages need to be updated and, when hovering, shows how many will be downloaded and unpacked.

It is a general script and could work with other bars or just be run in the terminal.

This script assumes your flake is in ~/.dotfiles and that your flake's nixosConfigurations is named the same as your $hostname

Forked [this project](https://github.com/guttermonk/waybar-nixos-updates) for starting point.

## How to use

Download the `update-checker` script, put it in your .dotfiles/ and make it executable (`chmod +x update-checker`).

To configure, add the following to your Waybar config (`~/.config/waybar/config`).


```json
"custom/nix-updates": {
    "exec": "$HOME/.dotfiles/update-checker", // <--- path to script
    "on-click": "$HOME/.dotfiles/update-checker", // refresh on click
    "interval": 3600, // refresh every hour
    "tooltip": true,
    "return-type": "json",
    "format": "{}"
	},

```

To style use the `#custom-nix-updates` ID in your Waybar styles file (`~/.config/waybar/styles.css`).


```css
#custom-nix-updates {
    background-color: white;
    margin: 10px 0px;
    border: 2px outset gray;
    min-width: 32px;
}
```

For more information on styling see the [Waybar wiki](https://github.com/Alexays/Waybar/wiki/Styling).
