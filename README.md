# picoknife

Commandline tool for manipulating [PICO-8](https://www.lexaloffle.com/pico-8.php) files

[Download for Windows](./picoknife-windows.zip?raw=true) · [Download for Mac](./picoknife-macos.zip?raw=true) · [Changelog](./CHANGELOG.md)

## About

*picoknife* can perform various actions on PICO-8 files (`.p8` source files, `.p8.png` cartridges, exported `.html` players).

This is useful for scripting release builds, customizing cartridges or the HTML player, fixing mistakes (such as restoring a label image overwritten by `Ctrl+7`).

The general syntax is: `picoknife {command} {input file} [optional args ...]`

## Commands

Commands in [the latest version](./CHANGELOG.md):

- **map** – export a map image from a `.p8` file
  - use `--half` or `--cells` to export a subsection of the map
  - use `--palette` or `--alternate` to change the colors
  - use `--transparent` to export one palette color as transparent
  - use `--scale` to upscale the output
- **sheet** – export a spritesheet image from a `.p8` file
  - use `--half` or `--sprites` to export a subsection of the spritesheet
  - `--palette`, `--alternate`, `--transparent`, `--scale` also apply here
- **sprites** – export individual sprite images from a `.p8` file
  - you can specify specific ranges of sprites, such as `1-5,10,20`
  - `--palette`, `--alternate`, `--transparent`, `--scale` also apply here
- **label** – export label image from a `.p8` file
  - `--palette`, `--alternate`, `--transparent`, `--scale` also apply here
- **setlabel** – set the label image of a `.p8` file, `.p8.png` cartridge, or `.html` player
  - use `--fitPalette` to apply PICO-8 colors (otherwise, preserve full color!)
- **sethtml** – modify an exported PICO-8 `.html` player page
  - use `--title` to set the page's title text
  - use `--headers` to include metadata headers from another file
  - use switches such as `--background` or `--dpad` to change page colors
  - use switches such as `--noDpad` or `--noX` to hide unused controls
- **colorimage** – apply 16-color palette to any image file
  - use `--palette` or `--alternate` to change the colors (otherwise, PICO-8 defaults)
  - use `--fit` and `--scale` to pre-shrink then upscale the image
- **copy** – modify or duplicate a `.p8` file with specified changes
  - use `--clear` to clear the contents of a section (such as "sfx")
  - use `--delete` to completely remove a section
- **version** – show the software version
- **help** – show help and usage information
  - use `help [command name]` to see help for a specific command
  - use `--all` to see full help for all commands

For the full output of `picoknife help --all`, see [HELP.txt](./HELP.txt)
