# RW's GBI Border Pack

A selection of borders for use with [Game Boy Interface](https://www.gc-forever.com/wiki/index.php?title=Game_Boy_Interface), including Super Game Boy, Game Boy Color, and Game Boy Advance borders.

[Border Previews](/PREVIEWS.md)

## Basic Installation & Usage

This guide assumes you've followed Extrems' [installation guide](https://www.gc-forever.com/wiki/index.php?title=Game_Boy_Interface#Installation) for GBI, including the extras folder.

1. Copy the `rw-gbi-borders.tpl.gz` file to the `GBI` folder in the root of your SD card, where the GBI extras are located.<br><br>

2. Ensure you copy the lines found in [RENAME-CLI.cli](/RENAME-CLI.cli) to the `.cli` file for the `.dol` of GBI that you use. If some exist with the same name then overwrite them.<br><br>

3. Ensure you copy the lines found in [RENAME-DCP.dcp](/RENAME-DCP.dcp) to the `.dcp` file for the `.dol` of GBI that you use. If some exist with the same name then overwrite them. These will allow you to select the desired border before GBI launches. Check the [Border Previews](/PREVIEWS.md) to view them.<br><br>**Note: For Swiss versions prior to v0.6r1424, there is a limit of 16 options with 8 choices in the `.dcp` file, so you may need to remove some you do not want.**

## Advanced Installation

Some executables of GBI use a combined `.dol` and `.cli` file. If you use one these you will need to open the file in a text editor and add the lines from [RENAME-CLI.cli](/RENAME-CLI.cli) file to it. With the file open in a text editor like notepad, scroll to the bottom and you should see some CLI options with a URL after them. The below is from the `gbihf-xrgb.dol+cli` file:

```
--format=custom-m,offset=0,scaled-size=0:0
--scan-mode=non-interlace
--
##https://www.gc-forever.com/wiki/index.php?title=Game_Boy_Interface/High-Fidelity_Edition#XRGB-mini_Framemeister
```

Simply copy the lines from [RENAME-CLI.cli](/RENAME-CLI.cli) and paste them after the `--scan-mode=non-interlace` line, but before the `--` line before the URL. Then save the file.

You could also copy the file and rename it something else for ease of use if you prefer. For instance, copy `gbihf-xrgb.dol+cli` and rename it to `gbihf-xrgb-borders.dol+cli`. Then create a `.dcp` file and paste the lines from [RENAME-DCP.dcp](/RENAME-DCP.dcp) into it, and save it as `gbihf-xrgb-borders.dcp`.

## Known Issues

Some GBI CLI options may not play well with borders. If your borders are flickering or strobing it will be caused by one of those options. The `--delay-video` option is one that came up during testing. If you're using the `scaled-size` setting or cropping, this could lead to the border being cut off.

If you use the Speedrunning Edition of GBI to play on a CRT, you may need to add the following to your `.cli` options:

`--vfilter=.5:.5:.0:.5:.0:.5`

For reference these are the `.cli` options I use for the SR edition on a CRT, played on a PAL GameCube connected using RGB:

```
--overlay=rw-gbi-borders.tpl.gz
--overlay-id=-1
--vfilter=.5:.5:.0:.5:.0:.5
--scan-mode=non-interlace
```

## Credits

**BSeraph** - Creating the Game Boy Color and Super Game Boy Color borders used in this pack, some with alterations. https://github.com/BSeraph/MiSTer-Super-GBC-Borders/

**RetroArch** - Super Game Boy Advance borders. https://github.com/libretro/common-shaders/tree/master/borders/sgba/
