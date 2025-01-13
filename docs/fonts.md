# Fonts for OpenTTD
OpenTTD needs four different fonts:
a _medium_ font (used for most texts in the game),
a _small_ font (used for the smallmap legend etc),
a _large_ font (used for news headlines etc),
and a _monospace_ font (used for text files such as NewGRF readmes).

You can use the following types of fonts with OpenTTD:
- **OpenTTD's default fonts**, namely _OpenTTD Sans_ (small and medium), _OpenTTD Serif_ (large)
  and _OpenTTD Mono_ (monospace). These are distributed as part of OpenTTD since version 14.
  The font files are included in the baseset directory of OpenTTD.
  These fonts are active by default and support the Latin, Greek and Cyrillic scripts at present.
- **Traditional sprite fonts**, which are the classic bitmap fonts included as part of the base graphics.
  They support only the Latin script.
  These fonts can be activated in the Graphics section of the Game options window,
  by enabling the option "Use traditional sprite fonts".
- **System fonts installed on your computer**. OpenTTD tries to automatically detect and activate a suitable
  system font in case you have selected a language not supported by the default fonts.
  However, if this fails, you may have to set a font manually.

## Setting system fonts manually
There are two ways to set system fonts, using the `font` console command or editing the openttd.cfg file.

### Using the console
Open the console. On a normal English keyboard this is done by pressing the \` key (to the left of 1).

The command to change a font is `font [medium|small|large|mono] [<font name>] [<size>]`.
The font name should be enclosed in double quotes if it contains spaces.
Note that the size provided is multiplied by the interface scaling factor.

You can reset the font and size to the defaults by providing the font name "" (a blank font name).
This will result in the OpenTTD default font or sprite font (depending on the setting) if you are
using a supported language, or a default font determined by your OS otherwise.

You can view the current font configuration by running the command `font` without any arguments.
For more information, run the command `help font`.

### Using openttd.cfg
In openttd.cfg, the following settings under the `[misc]` section determine the font (this is just an example):
```
small_font =
medium_font = Arial Bold
large_font = Times New Roman
mono_font =
small_size = 6
medium_size = 10
large_size = 18
mono_size = 10
```

If these settings are not present, you can add them under the `[misc]` section.
Setting fonts via this method works the same as with the console.
If any font names are left blank, the default font and size is used.

If you cannot find the openttd.cfg file, see [the directory structure guide](./directory_structure.md).
