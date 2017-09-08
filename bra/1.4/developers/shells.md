# Shells

Croogo now has the ability to install and activate extensions from the command
line. To access the shells `cd` in your `app/` folder and run the commands
using: `./Console/cake [shell]`.

## Install Shell

Most extensions you'll find on Github.com. To install the megamenu plugin
extension from github type:

    ./Console/cake install plugin https://github.com/rchavik/megamenu

Or:

    ./Console/cake install plugin rchavik megamenu

Themes can also be installed the same way:

    ./Console/cake install theme https://github.com/fahad19/themes

If you have a zip file located somewhere else, type:

    ./Console/cake install theme http://example.com/mytheme.zip


## Ext Shell

You can activate/deactivate plugins and themes from the console. To activate the
Megamenu extension previously installed:

    ./Console/cake ext activate plugin Megamenu

To deactivate:

    ./Console/cake ext deactivate plugin Megamenu
