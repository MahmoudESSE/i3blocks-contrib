# arch-update

Be always on top of your available updates with this blocklet. Optionally show AUR updates with the help of yaourt. Colorize the outputs for if your system is up to date or you got available updates.

![](screenshot.png)

![](screenshot2.png)
	
# Dependencies

* Arch Linux or another arch based distro
* python3
* [pacman-contrib](https://www.archlinux.org/packages/?name=pacman-contrib) for `checkupdates`

# Optional Dependencies

* yaourt for aur updates
* fontawesome for awesome labels

# Installation

* Copy the arch-update script into your directory of choice, e.g. ~/.i3blocks/
* Give it execution permission (`chmod +x arch-update`)
* Add the following blocket to your i3blocks.conf:

```ini
[arch-update]
command=$SCRIPT_DIR/arch-update 
interval=3600
markup=pango
LABEL=Updates: 
```
Another advanced example with fontawesome label, AUR updates included, watched packages, and custom colors for both messages:
```ini
[pacman-updates]
command=$SCRIPT_DIR/arch-update
markup=pango
interval= 3600
QUIET=true
WATCH=^linux.* ^pacman.*
BASE_COLOR=#5fff5f
UPDATE_COLOR=#FFFF85
# Should only have one AUR method at a time
AUR=true
#AUR_YAY=true
#AUR_PARU=true
LABEL= 
```
# Configuration
_Use the environment variables above instead of these deprecated command line options:_

- `-q`/`--quiet`: do not produce output if system is up to date
- `-w`/`--watch`: Explicitly watch for specified packages. Listed elements are treated as regular expressions for matching.
- `-b`/`--base_color`: set the base color of the output (when your system is up to date)
- `-u`/`--updates_available_color`: set the color of the output when updates are available
- `-a`/`--aur`: activate AUR update support  
- `-y`/`--aur_yay`: activate AUR update support using yay
- `-p`/`--aur_paru`: activate AUR update support using paru
For the latest options call `$SCRIPT_DIR/arch-update -h`.
